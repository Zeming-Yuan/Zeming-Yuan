<div align="center">

# Hi, I'm Zeming

<!-- Typing SVG: https://github.com/DenverCoder1/readme-typing-svg -->
[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&pause=1200&color=79C0FF&center=true&vCenter=true&width=520&lines=Python+%C2%B7+AI+%E5%BA%94%E7%94%A8+%C2%B7+RAG+%2F+Agent+%2F+MCP;FastAPI+%C2%B7+Redis+%C2%B7+Docker+%C2%B7+%E7%A7%81%E6%9C%89%E5%8C%96%E8%90%BD%E5%9C%B0;%E5%B9%BF%E4%B8%9C+%C2%B7+%E6%8A%8A%E6%A8%A1%E5%9E%8B%E6%8E%A5%E8%BF%9B%E7%9C%9F%E5%AE%9E%E4%B8%9A%E5%8A%A1)](https://git.io/typing-svg)

把模型接到真实业务里：能派活的数字员工、可评测的知识库、能对话预览发布的编程助手。  
关心边界、证据，和能不能私有化落地。

<!-- 顶栏技能图标：https://skillicons.dev -->
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=python,fastapi,redis,postgres,sqlite,docker,react,ts,nodejs,vite,linux,githubactions" alt="skills" />
  </a>
</p>

</div>

---

## 🔭 当前在做

与团队推进多条产品线（仓库多为私有，此处只写产品定位与能力）：

### 数字员工总台
- 浏览器创建数字员工并派到多台电脑执行；节点主动 WSS 外连，无需公网入站
- 能力模式白名单（只读 / 读写 / 浏览器 / 执行）+ 写操作审批闸门；内核级沙箱（macOS Seatbelt / Linux bubblewrap）
- Hub：Python · FastAPI · SQLAlchemy async · SQLite / PostgreSQL · MCP · BM25s + jieba；Web：React 19 · TypeScript · Vite · Tailwind；飞书渠道、团队 Markdown 资料库、网页录制 → Skill、看屏 / 远程终端

### 编程助手
- Web 工作台：浏览器对话、预览、下载与发布；DeepSeek 调本机编码智能体；PDF 文字提取（poppler 守卫进程）· Docker 运行时隔离
- 桌面端：多 Agent 会话 GUI（Claude Code / Codex / Cursor / Grok 等）；按项目组织会话与 Git worktree；Tauri + Rust + Vite + CodeMirror

### 知识库与有据回答
- 工厂场景私有化 AI 知识库：SOP / 设备手册入库、检索问答、金标评测与部署证据；数据不出厂
- 本机对话 / 嵌入端点（OpenAI 兼容）可指向客户算力；公开基准手册 + runner 复测
- 与直播 / 客服侧「有据回答」HTTP Adapter 衔接，同一套检索与引用约束复用

### 社媒 · 直播 · 客服
- 社媒一分多发：中文母稿 → 英文成片 → 两道审核 → 分发确认；仅官方 OAuth 授权账号可发（Facebook / Instagram / YouTube / X / TikTok 等）
- AI 语音直播：单房间评论接收 → 知识库 / 通用模型回答 → 克隆音色播报（抖音 / 视频号方向）；SQLite 会话账本 · DeepSeek
- 渠道客服：WhatsApp ↔ Chatwoot 坐席闭环 + AI Gateway；微信桌面 Assist（FAQ + DeepSeek，人工接管）；工厂外贸咨询场景的知识库问答 + 人工接管

---

## 🧱 工程能力

- **评测与证据** — 金标集、hit@k / 回归 runner、部署证据链；问答与 Agent 链路可复现对比
- **私有化交付** — Docker Compose / on-prem、本机或客户侧推理端点；数据默认不出厂
- **Agent 安全边界** — 能力白名单、写操作审批闸门、操作审计；默认最小权限
- **全栈落地** — FastAPI / MCP 后端 · React / Tauri 前端桌面 · Redis / PostgreSQL · CI 与 Compose 发布

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

- **[capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb)** — RAG 知识库问答 + NL2SQL ReAct Agent（手写 ReAct，不调 LangChain）
  - FastAPI · ChromaDB · Redis · Docker；手标 42 条中文真值（hit@3 = 0.79 / hit@10 = 0.90）· 22/22 测试 · [线上 Demo](https://capstone-ai-kb.onrender.com/docs)
- **[claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system)** — Claude Code 记忆网关（基于腾讯开源引擎二次开发）
  - FastMCP · L0–L3 分层记忆 · Hooks 全自动化 · 本地 BM25（jieba）+ 向量双路检索
- **[english-coach](https://github.com/Zeming-Yuan/english-coach)** — **进行中** · 零基础英语 AI 学习
  - FSRS 间隔复习 · DeepSeek 词卡 · React 19 + FastAPI · 学习科学脚手架（意群切分 / 提取练习等）· 108 测试全绿

---

## 🤝 开源协作

**已合并**
- [wandb/rai-toolkit](https://github.com/wandb/rai-toolkit) — RAG 检索质量评测：[#37](https://github.com/wandb/rai-toolkit/pull/37) `RetrievalRelevanceScorer`、[#58](https://github.com/wandb/rai-toolkit/pull/58) `ContextPrecisionScorer` / `ContextRecallScorer`
- [redis/redis-py](https://github.com/redis/redis-py) — [#4294](https://github.com/redis/redis-py/pull/4294)、[#4295](https://github.com/redis/redis-py/pull/4295) 示例 notebook 文档修正
- [BossZhiPin_Job_Search](https://github.com/longsizhuo/BossZhiPin_Job_Search) — [#40](https://github.com/longsizhuo/BossZhiPin_Job_Search/pull/40) 关键词提取失败不再写入空列表毒化粗筛缓存

**协作中**
- [TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory) — [#1365](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/1365)（closed，未合并）、[#1366](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/1366)（open）记忆提炼 / 向量写入相关修复

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
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white)

**AI / RAG / Agent**

![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6F61?style=for-the-badge&logo=databricks&logoColor=white)
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
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)

**DevOps / Delivery / Channels**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Compose](https://img.shields.io/badge/Compose-%E7%A7%81%E6%9C%89%E5%8C%96-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Feishu](https://img.shields.io/badge/Feishu-%E9%A3%9E%E4%B9%A6-00D6B9?style=for-the-badge)
![Eval](https://img.shields.io/badge/%E8%AF%84%E6%B5%8B%E9%87%91%E6%A0%87-Evidence-Gate-10B981?style=for-the-badge)
![Audit](https://img.shields.io/badge/%E5%AE%A1%E6%89%B9%20%26%20%E5%AE%A1%E8%AE%A1-Boundary-EF4444?style=for-the-badge)

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
