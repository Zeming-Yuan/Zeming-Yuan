<div align="center">

# Hi, I'm Zeming

<!-- Typing SVG: https://github.com/DenverCoder1/readme-typing-svg -->
[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&pause=1200&color=79C0FF&center=true&vCenter=true&width=520&lines=Python+%C2%B7+AI+%E5%BA%94%E7%94%A8+%C2%B7+RAG+%2F+Agent+%2F+MCP;FastAPI+%C2%B7+Redis+%C2%B7+Docker+%C2%B7+%E7%A7%81%E6%9C%89%E5%8C%96%E8%90%BD%E5%9C%B0;%E5%B9%BF%E4%B8%9C+%C2%B7+%E6%8A%8A%E6%A8%A1%E5%9E%8B%E6%8E%A5%E8%BF%9B%E7%9C%9F%E5%AE%9E%E4%B8%9A%E5%8A%A1)](https://git.io/typing-svg)

**写作** · [掘金 · Python 上下文管理器深度剖析](https://juejin.cn/post/7676404079284469796)

把大模型接到能跑在真实环境里的系统上：多机数字员工、可评测的私有化知识库、能对话 / 预览 / 发布的编程助手。  
合入前先过金标和 hit@k；对话与嵌入按 OpenAI 兼容协议留在本机，部署时改指向客户算力，语料默认不出厂。  
Agent 只有白名单里的能力，写操作过审批，执行落在内核沙箱里。公开仓库把这些选择做成可复跑的实现和数字。

<!-- 顶栏技能图标：https://skillicons.dev -->
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=python,fastapi,redis,postgres,sqlite,docker,react,ts,nodejs,vite,linux,githubactions" alt="skills" />
  </a>
</p>

</div>

---

## 🔭 当前在做

与团队推进的产品线仓库多为私有，这里只写架构和约束，不放地址。

### 数字员工总台

浏览器里创建数字员工，派到多台电脑执行；机器留在内网，不开放入站端口。

- 节点只主动 WSS 出站连 Hub；能力白名单 read / write / browser / execute，write 必须过审批闸门
- 内核沙箱 macOS Seatbelt / Linux bubblewrap。Hub：Python 3.12 · FastAPI · SQLAlchemy 2.0 async · SQLite / PostgreSQL（asyncpg）· MCP · BM25s + jieba

Web 控制面是 React 19 · TypeScript · Vite · Tailwind；飞书、看屏 / 远程终端、网页录制 → Skill 都走同一套白名单，没有审批记录的写操作不执行。

### 编程助手

浏览器里对话、预览、下载、发布；桌面端按项目挂多个编码 Agent，会话和 Git 工作区分开。

- Web：DeepSeek 调度本机编码智能体；PDF 文字由 poppler 守卫进程提取；执行环境 Docker 隔离
- 桌面：Tauri + Rust + Vite + CodeMirror；GUI 接入 Claude Code / Codex / Cursor / Grok；按项目会话 + Git worktree；Node.js 22

PDF 解析不进主进程；多 Agent 各写各的 worktree，不共用一个工作目录。

### 知识库与有据回答

厂内 SOP / 设备手册做私有化问答；回答必须标出处，语料不出厂。

- 载体 DocsGPT；本机 OpenAI 兼容的 chat / embed 端点，部署时改指向客户算力
- 直播和客服共用同一套检索 Adapter；证据薄则转人工

改检索或提示先跑金标集和 runner，部署证据要能复测；没有引用的回答不算完成。

社媒 / 直播 / 客服 / 企业后台：官方 OAuth 一分多发（Postiz · NestJS · Prisma · Docker Compose）· 单房间评论 → 有据回答 → 克隆音色（DeepSeek · 百炼）· WhatsApp ↔ Chatwoot 与微信 Assist 人工接管 · 企业后台 NestJS · Prisma · PostgreSQL · React 19 · Playwright，只读控制台聚合指标 / 健康 / 审计。

---

## 🧱 工程能力

- **评测与证据** — 中文 BM25 按字切开是死重，所以中文走纯向量、英文才 BM25 + RRF；同一金标上变差的检索（含 rerank）直接下线。证据：[capstone-ai-kb/evaluation](https://github.com/Zeming-Yuan/capstone-ai-kb/tree/main/evaluation)
- **私有化交付** — chat / embed 可改指向客户算力，导出备份把密钥挡在文件外。证据：[english-coach 备份测试](https://github.com/Zeming-Yuan/english-coach/blob/dev/tests/test_backup_v2.py#L275)（V3 导出断言不含 `llm_api_key`）
- **Agent 安全边界** — 提示词拦不住写盘和拉起进程，执行面用 Seatbelt / bubblewrap 收内核权限，write 再过审批；记忆网关只听 `127.0.0.1:8420`。证据：[claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system)
- **全栈落地** — FastAPI / NestJS / MCP · React / Tauri · Redis / PostgreSQL · CI + Compose。注入用结构压缩：骨架必留、按行截留，不按字符把文末规则切掉（完整画像约 5700 字符 → 每轮约 630 字符）。证据：[渐进式披露](https://github.com/Zeming-Yuan/claude-code-memory-system#设计说明)

---

## 📦 开源

<!-- pin 卡片：https://github.com/anuraghazra/github-readme-stats -->
<p>
  <a href="https://github.com/Zeming-Yuan/capstone-ai-kb">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=Zeming-Yuan&repo=capstone-ai-kb&theme=tokyonight&hide_border=true" alt="capstone-ai-kb" />
  </a>
  <a href="https://github.com/Zeming-Yuan/claude-code-memory-system">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=Zeming-Yuan&repo=claude-code-memory-system&theme=tokyonight&hide_border=true" alt="claude-code-memory-system" />
  </a>
  <a href="https://github.com/Zeming-Yuan/english-coach">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=Zeming-Yuan&repo=english-coach&theme=tokyonight&hide_border=true" alt="english-coach" />
  </a>
</p>

- **[capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb)** — NL2SQL + RAG 双引擎。ReAct 手写：`tool_map` → `call_tool` → `run`，循环在自己的代码里，便于对 SQL 和 tool 逐步打断点
  - CJK 路由：中文 query 纯向量（BM25 字符级切分对中文是死重）；英文 query 走 BM25 + RRF
  - 语料：Python 3.14 官方文档 3,341 chunks（PyMuPDF 提取，300/30 切片）；硅基流动 BGE-M3 · ChromaDB · JWT · Docker Compose
  - 42 条中文金标：hit@3 = 0.79 / hit@5 = 0.83 / hit@10 = 0.90 · pytest 22/22 · [线上 Demo](https://capstone-ai-kb.onrender.com/docs)
  - rerank：`bge-reranker-v2-m3` 在同一基线（RRF hit@3 = 0.74）上五连负优化，降到 0.55，生产已下线，判决留在评测记录里
  - 设计文：[掘金 · 手写 RAG 管线的 5 个设计决策](https://juejin.cn/post/7665944296248442906)
- **[claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system)** — 独立 Memory Gateway，只听 `127.0.0.1:8420`。基于 [TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory)（MIT）的 Gateway 模式，绕过 OpenClaw / Hermes 宿主，用 Claude Code hooks + MCP 接入
  - 分层 L0 对话 → L1 原子事实 → L2 场景 → L3 用户画像。Hooks：`SessionStart` / `UserPromptSubmit` / `Stop`；FastMCP 工具供模型主动检索
  - 存储：SQLite + sqlite-vec + FTS5 / jieba 混合；embedding 可选（BGE-M3，1024 维），不配则降为纯关键词
  - 注入用结构压缩：标题骨架必留、内容按行截留、场景压成文件名，细节再用 MCP 查全文。完整画像约 5700 字符 → 每轮约 630 字符（约 11%）；会话开始注入一次完整版，平时按需下钻
- **[english-coach](https://github.com/Zeming-Yuan/english-coach)** — **进行中** · 零基础英语。FSRS（py-fsrs）排期；提取练习、渐褪提示（首字母 → 长度 → 独立回忆）、i+1 意群切分（3–6 词一块）。React 19 + FastAPI
  - 课程 20 级递进（音标启蒙 → 高频词 → 简单句 → 场景对话）
  - 验收门禁：Playwright 双视口逐分支核对 T01–T21；缺场景、跳过或失败都返回非零。`--ticket` 只用于开发定位，不算总门禁
  - 备份当前导出为 V3；测试断言序列化结果里没有 `llm_api_key` / `LLM_API_KEY`，密钥、环境和语音缓存不进文件

---

## 🤝 开源协作

**已合并**
- [wandb/rai-toolkit](https://github.com/wandb/rai-toolkit) — RAG 检索质量评测：[#37](https://github.com/wandb/rai-toolkit/pull/37) `RetrievalRelevanceScorer`、[#58](https://github.com/wandb/rai-toolkit/pull/58) `ContextPrecisionScorer` / `ContextRecallScorer`
- [redis/redis-py](https://github.com/redis/redis-py) — [#4294](https://github.com/redis/redis-py/pull/4294)、[#4295](https://github.com/redis/redis-py/pull/4295) 示例 notebook 文档修正
- [BossZhiPin_Job_Search](https://github.com/longsizhuo/BossZhiPin_Job_Search) — [#40](https://github.com/longsizhuo/BossZhiPin_Job_Search/pull/40) 关键词提取失败不再写入空列表，避免粗筛缓存被毒化

**正在修**
- [TencentDB-Agent-Memory #1366](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/1366) — `POST /session/end` 只把 flush 重新入队，到不了 L1 提炼；这个 PR 让 flush 落到 `executeL1`

> 已关闭、未合并：[#1365](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/1365)（store-pool 的 embedding 没有把 `sendDimensions` 传下去）。

---

## 🛠️ 技术栈

**Backend**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=for-the-badge&logo=pydantic&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=for-the-badge&logo=sqlalchemy&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white)

**AI / RAG / Agent**

![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6F61?style=for-the-badge)
![bge-m3](https://img.shields.io/badge/bge--m3-Embedding-5B21B6?style=for-the-badge)
![BM25](https://img.shields.io/badge/BM25%20%2B%20RRF-Hybrid%20Search-111827?style=for-the-badge)
![MCP](https://img.shields.io/badge/MCP%20%2F%20FastMCP-Protocol-0EA5E9?style=for-the-badge)
![ReAct](https://img.shields.io/badge/ReAct-Hand--written-F59E0B?style=for-the-badge)
![DeepSeek](https://img.shields.io/badge/DeepSeek-LLM-4F46E5?style=for-the-badge)

**Frontend / Desktop**

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Tauri](https://img.shields.io/badge/Tauri-24C8DB?style=for-the-badge&logo=tauri&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)

**DevOps / Delivery / Channels**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Compose](https://img.shields.io/badge/Docker%20Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Feishu](https://img.shields.io/badge/Feishu-00D6B9?style=for-the-badge)

---

## 📊 GitHub Stats

<!--
隐私提示：默认只统计公开仓。若要把私有仓贡献算进卡片，
在 URL 加 &count_private=true（会暴露私有活动量级，自行权衡）。
-->

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=Zeming-Yuan&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true" alt="GitHub stats" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Zeming-Yuan&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" alt="Top languages" />

</div>
