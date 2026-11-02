# 袁仕杰 Zeming

Python 后端 · AI 应用开发｜RAG / Agent / MCP｜广东

做能跑在真实环境里的 AI 系统：数字员工总台、知识库问答、编程助手，以及社媒与客服链路。偏好可评测、可私有化、带审批与审计边界的工程实现。

## 当前在做

与团队推进多条产品线（仓库多为私有，此处只写产品定位与能力）：

**AI 数字员工**
- 总台 + 子节点：浏览器创建数字员工并派到多台电脑执行任务；节点主动 WSS 外连，无需公网入站；能力模式白名单（只读 / 读写 / 浏览器 / 执行）+ 写操作审批闸门；内核级沙箱（macOS Seatbelt / Linux bubblewrap）
- Hub：Python 3.12 · FastAPI · SQLAlchemy 2.0 async · SQLite / PostgreSQL（asyncpg）· MCP · BM25s + jieba；Web：React 19 · TypeScript · Vite 7 · Tailwind 4
- 飞书等消息渠道、团队 Markdown 资料库、网页录制 → 可安装 Skill、看屏 / 远程终端 / 集中同屏

**编程助手**
- Web 工作台：浏览器对话、预览、下载与发布；DeepSeek 调本机编码智能体；附件 PDF 文字提取（poppler 守卫进程）· Docker 运行时隔离 · 支付宝可选支付通道 · Node.js 22
- 桌面端：多 Agent 会话 GUI（Claude Code / Codex / Cursor / Grok Build 等）；按项目组织会话与 Git worktree；Tauri + Rust + Vite + CodeMirror

**知识库与评测**
- 工厂场景私有化 AI 知识库：SOP / 设备手册入库、检索问答、金标评测与部署证据；数据不出厂；载体 DocsGPT，本机对话 / 嵌入端点（OpenAI 兼容）可配置指向客户算力
- 公开基准手册 + runner 复测；与直播 / 客服侧「有据回答」HTTP Adapter 衔接

**社媒 · 直播 · 客服**
- 社媒一分多发：中文母稿 → 英文成片 → 两道审核 → 分发确认；仅官方 OAuth 授权账号可一键发（Facebook / Instagram / YouTube / X / TikTok 等）；发布器基于 Postiz（NestJS · Prisma · pnpm · Docker Compose）二次品牌化
- AI 语音直播：单房间评论接收 → 知识库 / 通用模型回答 → 克隆音色播报（抖音 / 视频号择一）；SQLite 会话账本 · DeepSeek · 百炼云端音色；完整自动开播仍在验收
- 渠道客服：WhatsApp ↔ Chatwoot 坐席真实往返；中间层 AI Gateway；微信桌面 Assist（FAQ + DeepSeek，人工接管）；阿里国际站 BMS 工厂咨询（知识库问答 + 人工接管，业务编码进行中）

**企业系统与运营后台**
- OPC 企业管理系统：入驻主体 / 物业资源 / 政府·运营·物业多方协作；NestJS · Prisma · PostgreSQL · React 19 · Vite · Playwright
- 多项目只读运营控制台：聚合编程助手与数字员工的指标 / 健康 / 审计；规划 Go 后端 + React · TypeScript · PostgreSQL
- 本地双 Spark 无人值守视频流水线：LTX 5 秒竖屏（720×1280 · 30fps）批量生产，热停与片段拼接固定规格

## 开源项目（独立开发）

- [capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb) — RAG 知识库问答 + NL2SQL ReAct Agent：手写 ReAct（不调 LangChain）· FastAPI · ChromaDB · Redis · Docker；手标 42 条中文真值（hit@3 = 0.79 / hit@10 = 0.90）· 22/22 测试 · [线上 Demo](https://capstone-ai-kb.onrender.com/docs)
- [claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system) — Claude Code 记忆网关（基于腾讯开源引擎二次开发）：FastMCP · L0–L3 分层记忆 · Hooks 全自动化 · 本地 BM25（jieba）+ 向量双路检索
- [english-coach](https://github.com/Zeming-Yuan/english-coach) — **进行中** · 零基础英语 AI 学习：FSRS 间隔复习 · DeepSeek 词卡 · React 19 + FastAPI · 学习科学脚手架（意群切分 / 提取练习等）· 108 测试全绿

## 开源协作

**已合并**

- [wandb/rai-toolkit](https://github.com/wandb/rai-toolkit) — RAG 检索质量评测：[#37](https://github.com/wandb/rai-toolkit/pull/37) `RetrievalRelevanceScorer`、[#58](https://github.com/wandb/rai-toolkit/pull/58) `ContextPrecisionScorer` / `ContextRecallScorer`
- [redis/redis-py](https://github.com/redis/redis-py) — [#4294](https://github.com/redis/redis-py/pull/4294)、[#4295](https://github.com/redis/redis-py/pull/4295) 示例 notebook 文档修正
- [longsizhuo/BossZhiPin_Job_Search](https://github.com/longsizhuo/BossZhiPin_Job_Search) — [#40](https://github.com/longsizhuo/BossZhiPin_Job_Search/pull/40) 关键词提取失败不再写入空列表毒化粗筛缓存

**协作中**

- [TencentCloud/TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory) — [#1365](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/1365)（closed，未合并）、[#1366](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/1366)（open）记忆提炼 / 向量写入相关修复

## 技术栈

**后端** · Python 3.12 · FastAPI · Uvicorn · Pydantic v2 · SQLAlchemy 2.0（async）· NestJS · Prisma · Go（规划中）· Redis · SQLite / PostgreSQL（asyncpg）· WebSocket · pytest · Vitest

**检索与 Agent** · ChromaDB · DocsGPT · bge-m3 / 本地嵌入端点 · BM25s + jieba · BM25 + RRF · MCP / FastMCP · ReAct 手写编排 · DeepSeek · 百炼（音色等）

**前端与桌面** · TypeScript · React 19 · Vite 6/7 · Tailwind 4 · CodeMirror · Tauri · Rust · Node.js 22 · Playwright

**集成与渠道** · 飞书 · Chatwoot · WhatsApp Cloud API · Postiz（社媒 OAuth 代发）· 支付宝（可选）

**工程与交付** · Docker / Compose · 私有化 on-prem · 金标评测与证据门禁 · 审批闸门与操作审计 · 内核沙箱（Seatbelt / bubblewrap）
