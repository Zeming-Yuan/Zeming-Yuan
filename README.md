<div align="center">

# Hi, I'm Zeming

<!-- Typing SVG: https://github.com/DenverCoder1/readme-typing-svg -->
[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&pause=1200&color=79C0FF&center=true&vCenter=true&width=520&lines=Python+%C2%B7+%E5%90%8E%E7%AB%AF+%2F+AI+%E5%BA%94%E7%94%A8+%C2%B7+RAG+%2F+Agent+%2F+MCP;FastAPI+%C2%B7+Redis+%C2%B7+Docker+%C2%B7+%E6%A3%80%E7%B4%A2%E8%AF%84%E6%B5%8B+%26+%E8%87%AA%E5%8A%A8%E5%8C%96%E6%B5%8B%E8%AF%95;%E5%B9%BF%E4%B8%9C+%C2%B7+%E5%85%AC%E5%BC%80%E9%A1%B9%E7%9B%AE+%26+%E5%B7%B2%E5%90%88%E5%B9%B6%E5%BC%80%E6%BA%90%E8%B4%A1%E7%8C%AE)](https://git.io/typing-svg)

**写作** · [掘金 · Python 上下文管理器深度剖析](https://juejin.cn/post/7676404079284469796)

**Python 后端 / AI 应用开发** · 广东

目前从事 AI 应用开发，关注文档检索、Agent 工具接入与自动化验证。  
这里展示公开项目与已合并的开源贡献，并附源码、运行说明与实验记录入口。

<!-- 顶栏技能图标：https://skillicons.dev -->
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=python,fastapi,redis,postgres,sqlite,docker,react,nodejs,vite,linux,githubactions" alt="skills" />
  </a>
</p>

</div>

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

文档检索与 NL2SQL 两条查询路径：文档问答走向量检索与混合查询，数据库问答走项目内的 ReAct 工具调用循环（只读 SQL）。  
仓库内有 42 条评测问题、检索策略对比脚本，以及 FastAPI、JWT 认证、流式返回与 Docker Compose 部署相关实现。

- 实现入口：[app/agent.py](https://github.com/Zeming-Yuan/capstone-ai-kb/blob/main/app/agent.py) · [app/vector_store.py](https://github.com/Zeming-Yuan/capstone-ai-kb/blob/main/app/vector_store.py)
- 评测与实验：[evaluation/](https://github.com/Zeming-Yuan/capstone-ai-kb/tree/main/evaluation)
- 设计文：[掘金 · 手写 RAG 管线的 5 个设计决策](https://juejin.cn/post/7665944296248442906)

### 2. [english-coach](https://github.com/Zeming-Yuan/english-coach/tree/dev) — 持续开发的英语学习应用

FastAPI + React 19（Vite）：FSRS 复习调度，以及提取练习、听写/测验等多种练习形式。  
包含课程进度、异常重试与刷新、V3 备份恢复等行为；默认分支为 `dev`。

- 后端调度与备份：[scheduler.py](https://github.com/Zeming-Yuan/english-coach/blob/dev/app/services/scheduler.py) · [backup.py](https://github.com/Zeming-Yuan/english-coach/blob/dev/app/services/backup.py)
- 测试与验收记录：[tests/](https://github.com/Zeming-Yuan/english-coach/tree/dev/tests) · [docs/release-evidence.md](https://github.com/Zeming-Yuan/english-coach/blob/dev/docs/release-evidence.md)

### 3. [claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system) — Claude Code 记忆接入示例

Gateway 本体基于 [TencentCloud/TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory)。  
本仓库提供 hooks、FastMCP 接入、上下文摘要注入与本地部署示例。

- hooks / MCP：[hooks/](https://github.com/Zeming-Yuan/claude-code-memory-system/tree/main/hooks) · [mcp-server/](https://github.com/Zeming-Yuan/claude-code-memory-system/tree/main/mcp-server)

---

## 🤝 已合并的开源贡献

| 仓库 | PR | 实际改动 |
|---|---|---|
| [wandb/rai-toolkit](https://github.com/wandb/rai-toolkit) | [#37](https://github.com/wandb/rai-toolkit/pull/37) · [#58](https://github.com/wandb/rai-toolkit/pull/58) | 检索相关性 / Context Precision·Recall 评分器，含测试与文档 |
| [BossZhiPin_Job_Search](https://github.com/longsizhuo/BossZhiPin_Job_Search) | [#40](https://github.com/longsizhuo/BossZhiPin_Job_Search/pull/40) | 关键词提取失败时不再缓存空列表，并补回归测试 |
| [redis/redis-py](https://github.com/redis/redis-py) | [#4294](https://github.com/redis/redis-py/pull/4294) · [#4295](https://github.com/redis/redis-py/pull/4295) | 示例 notebook 拼写与失效链接修正（文档贡献） |

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
