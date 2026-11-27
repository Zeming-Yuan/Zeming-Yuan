<div align="center">

# Hi, I'm Zeming

<!-- Typing SVG: https://github.com/DenverCoder1/readme-typing-svg -->
[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&pause=1200&color=79C0FF&center=true&vCenter=true&width=520&lines=Python+%C2%B7+%E5%90%8E%E7%AB%AF+%2F+AI+%E5%BA%94%E7%94%A8+%C2%B7+RAG+%2F+Agent+%2F+MCP;FastAPI+%C2%B7+Redis+%C2%B7+Docker+%C2%B7+%E6%A3%80%E7%B4%A2%E8%AF%84%E6%B5%8B+%26+%E8%87%AA%E5%8A%A8%E5%8C%96%E6%B5%8B%E8%AF%95;%E5%B9%BF%E4%B8%9C+%C2%B7+%E5%85%AC%E5%BC%80%E9%A1%B9%E7%9B%AE+%26+%E5%B7%B2%E5%90%88%E5%B9%B6%E5%BC%80%E6%BA%90%E8%B4%A1%E7%8C%AE)](https://git.io/typing-svg)

**写作** · [掘金 · Python 上下文管理器深度剖析](https://juejin.cn/post/7676404079284469796)

**Python 后端 / AI 应用开发** · 广东

**把检索、Agent 和验证，做成能部署、能复查的应用。**  
公开项目和已合并贡献都附了源码与实验记录。

<!-- 顶栏技能图标：https://skillicons.dev -->
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=python,fastapi,redis,postgres,sqlite,docker,react,nodejs,vite,linux,githubactions" alt="skills" />
  </a>
</p>

</div>

---

## 🔭 当前在做

与团队推进的产品线仓库多为私有，这里只写能公开说的设计约束，不放地址。

### 数字员工总台

**内网执行、不对外开放端口：节点只主动经 WSS 连接 Hub。**

- 能力白名单为 read / write / browser / execute；写操作必须带审批记录，否则不执行
- 内核沙箱用 macOS Seatbelt / Linux bubblewrap，限制节点进程权限
- Hub：Python 3.12 · FastAPI · SQLAlchemy 2.0 async · SQLite / PostgreSQL（asyncpg）· MCP · BM25s + jieba
- Web 控制面：React 19 · TypeScript · Vite · Tailwind；飞书、看屏 / 远程终端、网页录制生成 Skill，都走同一套白名单

### 编程助手

**编码 Agent 按项目隔离：会话分开，Git worktree 分开，PDF 解析不进主进程。**

- Web：由 DeepSeek 调度本机编码智能体；PDF 文字由 poppler 守卫进程提取；执行环境用 Docker 隔离
- 桌面：Tauri + Rust + Vite + CodeMirror，可接入 Claude Code / Codex / Cursor / Grok；按项目维护会话与 worktree；Node.js 22

多个 Agent 各自写入独立 worktree，不共用同一工作目录，避免改到别人的文件。

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

### 1. [capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb) — 同时查文档和数据库

**一个能同时「问文档」和「问数据库」的问答服务。**  
文档走向量与混合检索，数据库走项目内 ReAct 工具循环（只读 SQL）。仓库含 42 条评测问题、检索策略对比脚本，以及 FastAPI、JWT 认证、流式返回和 Docker Compose 部署实现。

- 实现入口：[app/agent.py](https://github.com/Zeming-Yuan/capstone-ai-kb/blob/main/app/agent.py) · [app/vector_store.py](https://github.com/Zeming-Yuan/capstone-ai-kb/blob/main/app/vector_store.py)
- 评测与实验：[evaluation/](https://github.com/Zeming-Yuan/capstone-ai-kb/tree/main/evaluation)
- 设计文：[掘金 · 手写 RAG 管线的 5 个设计决策](https://juejin.cn/post/7665944296248442906)

### 2. [english-coach](https://github.com/Zeming-Yuan/english-coach/tree/dev) — 按复习规律学英语

**按遗忘曲线安排复习的英语学习应用。**  
用 FastAPI 和 React 19（Vite）做成，支持提取练习、听写和测验，并覆盖课程进度、异常重试、刷新和 V3 备份恢复。默认分支是 `dev`。

- 后端调度与备份：[scheduler.py](https://github.com/Zeming-Yuan/english-coach/blob/dev/app/services/scheduler.py) · [backup.py](https://github.com/Zeming-Yuan/english-coach/blob/dev/app/services/backup.py)
- 测试与验收记录：[tests/](https://github.com/Zeming-Yuan/english-coach/tree/dev/tests) · [docs/release-evidence.md](https://github.com/Zeming-Yuan/english-coach/blob/dev/docs/release-evidence.md)

### 3. [claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system) — 给 Claude Code 接上记忆

**给 Claude Code 接上记忆能力。**  
Gateway 本体基于 [TencentCloud/TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory)。本仓库补充 hooks、FastMCP 接入、上下文摘要注入和本地部署示例。

- hooks / MCP：[hooks/](https://github.com/Zeming-Yuan/claude-code-memory-system/tree/main/hooks) · [mcp-server/](https://github.com/Zeming-Yuan/claude-code-memory-system/tree/main/mcp-server)

---

## 🤝 已合并的开源贡献

| 仓库 | PR | 实际改动 |
|---|---|---|
| [wandb/rai-toolkit](https://github.com/wandb/rai-toolkit) | [#37](https://github.com/wandb/rai-toolkit/pull/37) · [#58](https://github.com/wandb/rai-toolkit/pull/58) | 补上检索相关性与 Context Precision / Recall 评分器，并加上测试和文档 |
| [BossZhiPin_Job_Search](https://github.com/longsizhuo/BossZhiPin_Job_Search) | [#40](https://github.com/longsizhuo/BossZhiPin_Job_Search/pull/40) | 修掉关键词提取失败后缓存空列表的问题，并补回归测试 |
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
