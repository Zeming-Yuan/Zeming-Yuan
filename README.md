### Hi, I'm Zeming

AI 应用工程师，习惯以**单人端到端**的方式推动产品从 0 到上线。技术上以 **Python 后端、RAG 评测与 Agent 工程**为核心，覆盖全栈开发、安全隔离、私有化推理部署与自动化回归验证。

---

### 核心产品实践（商业项目，代码不公开）

> 以下核心系统均由我独立负责从架构设计、前后端 / 客户端研发到部署上线的完整闭环，这里仅记录脱敏后的关键工程设计与取舍：

#### 1. 跨端内网 Agent 调度与执行平台（Web + 桌面端 + Android）
面向企业多机任务自动化场景，在 Web 与移动端创建并编排任务，分发至客户内网多台受管终端执行，支持客户端安装包分发与 CI/CD 自动发布回滚。
- **零入站暴露**：受管节点仅通过 WSS 主动出站连接中心 Hub，客户内网无需开放任何入站端口。
- **Fail-Closed 三层安全边界**：总台侧按 `read / write / browser / execute` 白名单鉴权，高风险写操作强制过审批闸门，远程命令参数统一经 `shlex` / base64 防注入；节点侧以内核沙箱（macOS Seatbelt / Linux `bubblewrap` / Windows 受限令牌）屏蔽宿主家目录、`/etc` 与 `/tmp`，由内核直接拦截越界读写——**探测不到可靠沙箱时拒绝执行，绝不降级回退静态正则检查**。
- **分布式可靠交办与人工接管**：围绕会话 / 请求 / 任务三层状态机设计幂等提交回执，断网重试不重复派发；原生 Android 客户端（Kotlin + Jetpack Compose，Android Keystore AES-GCM 保护本地凭据与待确认意图）支持实时看屏、暂停 Agent、人类临时接管输入（如处理验证码）并明确交还继续执行，断线或退后台自动撤销控制租约。
- **工程化沉淀**：维护 120+ 份架构决策记录（ADR），配备独立 HTTPS 隔离联调夹具与端到端真机/桌面回归验收。

#### 2. Web AI 编程工作台（对话生成 → 预览 → 隔离发布）
面向浏览器场景的一站式编码工作台，支持对话生成、实时预览与一键发布静态站点或带数据库的全栈应用。
- **同站隔离与零停机发布**：预览与线上应用分属独立子域名源，隔离访客登录 Cookie 与工作台账号；静态站点发布采用独立版本目录 + 原子清单切换，失败或进程异常退出自动保留旧版；后台应用的线上源码、运行实例与 SQLite 业务数据与预览环境完全解耦。
- **受限子进程安全隔离**：用 C 编写专用启动器（`-Wall -Wextra -Werror`）隔离 `poppler` PDF 文本提取，硬限制页数、10 秒超时与 256 MiB 地址空间，防止畸形文档拖垮主服务；执行环境通过 Docker 隔离，并具备细粒度功能熔断开关与公网部署默认口令防呆校验。

#### 3. 私有化多模态推理集群与企业知识库交付
- **双节点私有算力推理网关**：双机 ARM64 算力节点间通过 SSH 加密隧道回环互联，统一经 OpenAI 兼容网关与内部 CA HTTPS 鉴权对外提供服务（模型端口不暴露局域网）。跑通 vLLM 200K 长上下文（含流式断连槽位清理）、图像生成/编辑串行轮换（配 20 GiB 内存保护与过载 503 拒单），以及跨节点交替调度的批量视频生成流水线（9 帧尾部重叠拼接 + 85°C 温控硬停）。
- **工厂私有化知识库与离线评测**：面向厂内 SOP / 设备手册实现语料不出厂问答与原文引用溯源，搭建可复现离线金标评测 Runner，通过量化归因定位“检索桥挤占 top-k 引发召回回归”与“本地推理端点 `reasoning_content` 挤占输出预算致空答”等真实线上问题。
- **工程取舍（Build vs. Integrate）**：对于知识库底座、多平台社媒分发、微信桌面客服与语音直播等交付型业务，优先基于 DocsGPT / Postiz / Chatwoot 等成熟开源底座做二开集成与可控性加固，将自研精力聚焦在调度、沙箱隔离、推理网关与评测门禁上。

---

### 公开项目（可查看源码与评测记录）

- **[capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb)** — **手写 ReAct 的 RAG 与只读 NL2SQL 双路径问答**  
  不依赖 LangChain 黑盒封装，手写 ReAct 工具调用循环区分文档检索与只读 SQL 查询。基于 Python 官方文档（3,341 chunks）构建 42 题评测集，达 `hit@3=0.79`、`hit@5=0.83`、`hit@10=0.90`；实测发现跨语言场景下字符级 BM25 对中文查询为负优化，因此设计 CJK 检索路由；连续 5 轮实验确认 `bge-reranker-v2-m3` 掉点（`0.74 → 0.55`）后按数据下线重排。  
  [agent.py](https://github.com/Zeming-Yuan/capstone-ai-kb/blob/main/app/agent.py) · [vector_store.py](https://github.com/Zeming-Yuan/capstone-ai-kb/blob/main/app/vector_store.py) · [evaluation/](https://github.com/Zeming-Yuan/capstone-ai-kb/tree/main/evaluation) · [设计复盘](https://juejin.cn/post/7665944296248442906)

- **[english-coach](https://github.com/Zeming-Yuan/english-coach/tree/dev)** — **基于 FSRS 的英语学习应用（FastAPI + React）**  
  围绕间隔重复（`py-fsrs`）与主动回忆练习搭建完整学习闭环，按近 7 个学习日首答通过率动态调节每日词量，区分独立回忆与带提示作答的排期规则；覆盖数据备份恢复、后端单测与 21 条 Playwright 端到端回归测试。  
  [scheduler.py](https://github.com/Zeming-Yuan/english-coach/blob/dev/app/services/scheduler.py) · [backup.py](https://github.com/Zeming-Yuan/english-coach/blob/dev/app/services/backup.py) · [tests/](https://github.com/Zeming-Yuan/english-coach/tree/dev/tests)

- **[claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system)** — **Claude Code 本地分层记忆接入**  
  基于 [TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory) 独立 Gateway 封装 Hooks 与 FastMCP 工具层，通过渐进式披露摘要注入（章节骨架 + 按需下钻检索）在控制每轮 Token 开销的同时保留原始事实溯源。  
  [hooks/](https://github.com/Zeming-Yuan/claude-code-memory-system/tree/main/hooks) · [mcp-server/](https://github.com/Zeming-Yuan/claude-code-memory-system/tree/main/mcp-server)

---

### 开源贡献

- **[wandb/rai-toolkit](https://github.com/wandb/rai-toolkit)**（[#37](https://github.com/wandb/rai-toolkit/pull/37) · [#58](https://github.com/wandb/rai-toolkit/pull/58)）：贡献 RAG 检索相关性与 Context Precision / Recall 评分器，包含单元测试与使用文档。

---

### 写作

- [手写 RAG 管线的 5 个设计决策](https://juejin.cn/post/7665944296248442906)
- [Python 上下文管理器深度剖析](https://juejin.cn/post/7676404079284469796)

---

**核心技术栈**：Python · FastAPI · SQLAlchemy · PostgreSQL · Redis · SQLite · RAG / Eval · MCP · vLLM · Docker · Linux · React / TypeScript · Kotlin (Compose) · Playwright
