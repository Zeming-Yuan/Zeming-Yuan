<div align="center">

# Hi, I'm Zeming

<!-- Typing SVG: https://github.com/DenverCoder1/readme-typing-svg -->
[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&pause=1200&color=79C0FF&center=true&vCenter=true&width=520&lines=Python+%C2%B7+%E5%90%8E%E7%AB%AF+%2F+AI+%E5%BA%94%E7%94%A8+%C2%B7+RAG+%2F+Agent+%2F+MCP;FastAPI+%C2%B7+Redis+%C2%B7+Docker+%C2%B7+%E6%A3%80%E7%B4%A2%E8%AF%84%E6%B5%8B+%26+%E8%87%AA%E5%8A%A8%E5%8C%96%E6%B5%8B%E8%AF%95;%E5%B9%BF%E4%B8%9C+%C2%B7+%E5%85%AC%E5%BC%80%E9%A1%B9%E7%9B%AE+%26+%E5%B7%B2%E5%90%88%E5%B9%B6%E5%BC%80%E6%BA%90%E8%B4%A1%E7%8C%AE)](https://git.io/typing-svg)

**写作** · [掘金 · Python 上下文管理器深度剖析](https://juejin.cn/post/7676404079284469796)

**Python 后端 / AI 应用开发** · 广东

目前在做 AI 应用开发，主要方向是文档检索、Agent 工具接入和自动化验证。  
公开项目和已合并的开源贡献都附了源码、运行说明和实验记录入口。

<!-- 顶栏技能图标：https://skillicons.dev -->
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=python,fastapi,redis,postgres,sqlite,docker,react,nodejs,vite,linux,githubactions" alt="skills" />
  </a>
</p>

</div>

---

## 🔭 当前在做

与团队推进的产品线仓库多为私有，这里只写架构和约束，不放地址。

### 数字员工总台

浏览器里创建数字员工，派到多台电脑执行；机器留在内网，不开放入站端口。

- 节点只主动经 WSS 出站连接 Hub；能力白名单为 read / write / browser / execute，写操作必须经过审批
- 内核沙箱：macOS Seatbelt / Linux bubblewrap。Hub 使用 Python 3.12 · FastAPI · SQLAlchemy 2.0 async · SQLite / PostgreSQL（asyncpg）· MCP · BM25s + jieba

Web 控制面为 React 19 · TypeScript · Vite · Tailwind。飞书、看屏 / 远程终端、网页录制生成 Skill，都走同一套白名单；没有审批记录的写操作不会执行。

### 编程助手

浏览器里完成对话、预览、下载和发布；桌面端按项目挂多个编码 Agent，会话与 Git 工作区相互隔离。

- Web：由 DeepSeek 调度本机编码智能体；PDF 文字由 poppler 守卫进程提取；执行环境用 Docker 隔离
- 桌面：Tauri + Rust + Vite + CodeMirror；可接入 Claude Code / Codex / Cursor / Grok；按项目维护会话，并使用 Git worktree；Node.js 22

PDF 解析不进入主进程；多个 Agent 各自写入独立 worktree，不共用同一工作目录。

### 知识库与有据回答

用厂内 SOP 和设备手册做私有化问答：回答必须标明出处，语料不出厂。

- 载体为 DocsGPT；本机提供 OpenAI 兼容的 chat / embed 端点，部署时改指向客户算力
- 直播和客服共用同一套检索 Adapter；证据不足时转人工

改检索或提示前，先跑金标集和 runner；部署结果要能复测。没有引用的回答不算完成。

社媒、直播、客服和企业后台也在推进：

- 社媒：官方 OAuth 一分多发（Postiz · NestJS · Prisma · Docker Compose）
- 直播 / 客服：单房间评论 → 有据回答 → 克隆音色（DeepSeek · 百炼）；WhatsApp ↔ Chatwoot，微信 Assist 支持人工接管
- 企业后台：NestJS · Prisma · PostgreSQL · React 19 · Playwright；只读控制台聚合指标、健康与审计

---

## 📦 三个代表项目

<!-- pin 卡片：https://github.com/anuraghazra/github-readme-stats -->
<p>
  <a href="https://github.com/Zeming-Yuan/capstone-ai-kb">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=Zeming-Yuan&repo=capstone-ai-kb&theme=tokyonight&hide_border=true" alt="capstone-ai-kb" />
  </a>
  <a href="https://github.com/Zeming-Yuan/english-coach">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=Zeming-Yuan&repo=english-coach&theme=tokyonight&hide_border=true" alt="english-coach" />
  </a>
  <a href="https://github.com/Zeming-Yuan/claude-code-memory-system">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=Zeming-Yuan&repo=claude-code-memory-system&theme=tokyonight&hide_border=true" alt="claude-code-memory-system" />
  </a>
</p>

### 1. [capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb) — RAG 与数据库问答

可本地部署的问答服务：文档问答走向量检索与混合查询，数据库问答走项目内的 ReAct 工具调用循环（只读 SQL）。  
仓库里有 42 条评测问题、检索策略对比脚本，以及 FastAPI、JWT 认证、流式返回和 Docker Compose 部署实现。

- 实现入口：[app/agent.py](https://github.com/Zeming-Yuan/capstone-ai-kb/blob/main/app/agent.py) · [app/vector_store.py](https://github.com/Zeming-Yuan/capstone-ai-kb/blob/main/app/vector_store.py)
- 评测与实验：[evaluation/](https://github.com/Zeming-Yuan/capstone-ai-kb/tree/main/evaluation)
- 设计文：[掘金 · 手写 RAG 管线的 5 个设计决策](https://juejin.cn/post/7665944296248442906)

### 2. [english-coach](https://github.com/Zeming-Yuan/english-coach/tree/dev) — 持续开发的英语学习应用

用 FastAPI 和 React 19（Vite）做的英语学习应用，支持 FSRS 复习调度，以及提取练习、听写和测验等练习形式。  
也包含课程进度、异常重试与刷新、V3 备份恢复；默认分支是 `dev`。

- 后端调度与备份：[scheduler.py](https://github.com/Zeming-Yuan/english-coach/blob/dev/app/services/scheduler.py) · [backup.py](https://github.com/Zeming-Yuan/english-coach/blob/dev/app/services/backup.py)
- 测试与验收记录：[tests/](https://github.com/Zeming-Yuan/english-coach/tree/dev/tests) · [docs/release-evidence.md](https://github.com/Zeming-Yuan/english-coach/blob/dev/docs/release-evidence.md)

### 3. [claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system) — Claude Code 记忆接入示例

Gateway 本体基于 [TencentCloud/TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory)。  
本仓库在此之上补充了 hooks、FastMCP 接入、上下文摘要注入和本地部署示例。

- hooks / MCP：[hooks/](https://github.com/Zeming-Yuan/claude-code-memory-system/tree/main/hooks) · [mcp-server/](https://github.com/Zeming-Yuan/claude-code-memory-system/tree/main/mcp-server)

---

## 🤝 已合并的开源贡献

| 仓库 | PR | 实际改动 |
|---|---|---|
| [wandb/rai-toolkit](https://github.com/wandb/rai-toolkit) | [#37](https://github.com/wandb/rai-toolkit/pull/37) · [#58](https://github.com/wandb/rai-toolkit/pull/58) | 为检索相关性、Context Precision 和 Context Recall 补了评分器，并加上测试与文档 |
| [BossZhiPin_Job_Search](https://github.com/longsizhuo/BossZhiPin_Job_Search) | [#40](https://github.com/longsizhuo/BossZhiPin_Job_Search/pull/40) | 关键词提取失败时不再把空列表写入缓存，并补了回归测试 |
| [redis/redis-py](https://github.com/redis/redis-py) | [#4294](https://github.com/redis/redis-py/pull/4294) · [#4295](https://github.com/redis/redis-py/pull/4295) | 修正示例 notebook 的拼写和失效链接（文档贡献） |

---

## 🛠️ 项目中使用的技术

**Backend**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=for-the-badge&logo=sqlalchemy&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white)

**AI / RAG / Agent**

![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6F61?style=for-the-badge)
![MCP](https://img.shields.io/badge/MCP%20%2F%20FastMCP-Protocol-0EA5E9?style=for-the-badge)
![ReAct](https://img.shields.io/badge/ReAct-Agent%20loop-F59E0B?style=for-the-badge)
![FSRS](https://img.shields.io/badge/FSRS-Scheduler-5B21B6?style=for-the-badge)

**Frontend / DevOps**

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)

---

## 📝 技术笔记

- [手写 RAG 管线的 5 个设计决策](https://juejin.cn/post/7665944296248442906)
- [Python 上下文管理器深度剖析](https://juejin.cn/post/7676404079284469796)

---

## 📊 GitHub Stats

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=Zeming-Yuan&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true" alt="GitHub stats" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Zeming-Yuan&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" alt="Top languages" />

</div>
