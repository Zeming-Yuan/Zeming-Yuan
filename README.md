<div align="center">

# Hi, I'm Zeming

<!-- Typing SVG: https://github.com/DenverCoder1/readme-typing-svg -->
[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&pause=1200&color=79C0FF&center=true&vCenter=true&width=520&lines=Python+%C2%B7+AI+%E5%BA%94%E7%94%A8+%C2%B7+RAG+%2F+Agent+%2F+MCP;FastAPI+%C2%B7+Redis+%C2%B7+Docker+%C2%B7+%E7%A7%81%E6%9C%89%E5%8C%96%E8%90%BD%E5%9C%B0;%E5%B9%BF%E4%B8%9C+%C2%B7+%E6%8A%8A%E6%A8%A1%E5%9E%8B%E6%8E%A5%E8%BF%9B%E7%9C%9F%E5%AE%9E%E4%B8%9A%E5%8A%A1)](https://git.io/typing-svg)

把大模型接到能上线的系统里：派得出去的数字员工、能预览和发布的编程助手、回答带出处的知识库。

<!-- 顶栏技能图标：https://skillicons.dev -->
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=python,fastapi,redis,postgres,sqlite,docker,react,ts,nodejs,vite,linux,githubactions" alt="skills" />
  </a>
</p>

</div>

---

## 🔭 当前在做

### 数字员工总台
- 在浏览器里创建数字员工，派到多台电脑上干活；电脑自己连出来，不用在公网开端口
- 能力只开四档：只读、读写、浏览器、执行。要改东西或要执行，先过审批；进程关在 macOS Seatbelt 或 Linux bubblewrap 里
- 可以从飞书派活，也能看屏、开远程终端，把一次网页操作录成 Skill

### 编程助手
- 网页上对话、看预览、直接发布；DeepSeek 调本机编码智能体，运行时用 Docker 隔开
- 桌面端把 Claude Code、Codex、Cursor、Grok 按项目分开，各自一个 Git worktree（Tauri）

### 知识库与有据回答
- 工厂 SOP 和设备手册留在现场，回答必须带原文出处
- 直播评论和客服提问共用这套检索；出处不够就交给人

另有社媒一分多发 / 直播客服 / 企业与运营后台在推进（多为私有）。

---

## 🧱 工程能力

- **评测与证据** — [capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb) 金标 42 条中文真值，hit@3 = 0.79 / hit@10 = 0.90
- **私有化交付** — [claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system) 记忆网关只听 127.0.0.1，用本地 SQLite 检索，不配向量也能跑
- **密钥不进备份** — [english-coach 的备份测试](https://github.com/Zeming-Yuan/english-coach/blob/dev/tests/test_backup_v2.py) 断言导出 JSON 里没有 `llm_api_key`
- **全栈落地** — [english-coach](https://github.com/Zeming-Yuan/english-coach) 同一个仓库里交付 React 19 和 FastAPI

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

- **[capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb)** — 手写 ReAct 的 RAG + NL2SQL，不套 LangChain
  - 42 条中文真值 hit@3 = 0.79 / hit@10 = 0.90 · 22/22 测试 · [线上 Demo](https://capstone-ai-kb.onrender.com/docs)
- **[claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system)** — 给 Claude Code 加分层记忆：从 L0 对话提炼到 L3 画像，Hooks 自动写入和召回
  - 完整画像约 5700 字符，压到每轮注入约 630 字符（约 11%）
- **[english-coach](https://github.com/Zeming-Yuan/english-coach)** — 进行中 · 零基础英语：FSRS 排复习，DeepSeek 出词卡
  - 课程 20 级递进 · 浏览器门禁 T01–T21（双视口，缺一则验收失败）

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

![Tauri](https://img.shields.io/badge/Tauri-24C8DB?style=for-the-badge&logo=tauri&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6F61?style=for-the-badge)
![DeepSeek](https://img.shields.io/badge/DeepSeek-4F46E5?style=for-the-badge)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)

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
