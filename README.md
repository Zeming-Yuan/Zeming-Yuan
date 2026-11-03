# Zeming

**Python 后端 / AI 应用开发** · 广东

目前从事 AI 应用开发，关注文档检索、Agent 工具接入与自动化验证。  
这里展示公开项目与已合并的开源贡献，并附源码、运行说明与实验记录入口。

## 三个代表项目

### 1. [capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb) — RAG 与数据库问答

文档检索与 NL2SQL 两条查询路径：文档问答走向量检索与混合查询，数据库问答走项目内的 ReAct 工具调用循环（只读 SQL）。  
仓库内有 42 条评测问题、检索策略对比脚本，以及 FastAPI、JWT 认证、流式返回与 Docker Compose 部署相关实现。

- 实现入口：[app/agent.py](https://github.com/Zeming-Yuan/capstone-ai-kb/blob/main/app/agent.py) · [app/vector_store.py](https://github.com/Zeming-Yuan/capstone-ai-kb/blob/main/app/vector_store.py)
- 评测与实验：[evaluation/](https://github.com/Zeming-Yuan/capstone-ai-kb/tree/main/evaluation)

### 2. [english-coach](https://github.com/Zeming-Yuan/english-coach/tree/dev) — 持续开发的英语学习应用

FastAPI + React 19（Vite）前后端：FSRS 复习调度，以及提取练习、听写/测验等多种练习形式。  
包含课程进度、异常重试与刷新、V3 备份恢复等行为；默认分支为 `dev`。

- 后端调度与备份：[app/services/scheduler.py](https://github.com/Zeming-Yuan/english-coach/blob/dev/app/services/scheduler.py) · [app/services/backup.py](https://github.com/Zeming-Yuan/english-coach/blob/dev/app/services/backup.py)
- 测试与验收记录：[tests/](https://github.com/Zeming-Yuan/english-coach/tree/dev/tests) · [docs/release-evidence.md](https://github.com/Zeming-Yuan/english-coach/blob/dev/docs/release-evidence.md)

### 3. [claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system) — Claude Code 记忆接入示例

Gateway 本体基于 [TencentCloud/TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory)。  
本仓库提供 hooks、FastMCP 接入、上下文摘要注入与本地部署示例。

- hooks / MCP：[hooks/](https://github.com/Zeming-Yuan/claude-code-memory-system/tree/main/hooks) · [mcp-server/](https://github.com/Zeming-Yuan/claude-code-memory-system/tree/main/mcp-server)

## 已合并的开源贡献

| 仓库 | PR | 实际改动 |
|---|---|---|
| [wandb/rai-toolkit](https://github.com/wandb/rai-toolkit) | [#37](https://github.com/wandb/rai-toolkit/pull/37) · [#58](https://github.com/wandb/rai-toolkit/pull/58) | 检索相关性 / Context Precision·Recall 评分器，含测试与文档 |
| [BossZhiPin_Job_Search](https://github.com/longsizhuo/BossZhiPin_Job_Search) | [#40](https://github.com/longsizhuo/BossZhiPin_Job_Search/pull/40) | 关键词提取失败时不再缓存空列表，并补回归测试 |
| [redis/redis-py](https://github.com/redis/redis-py) | [#4294](https://github.com/redis/redis-py/pull/4294) · [#4295](https://github.com/redis/redis-py/pull/4295) | 示例 notebook 拼写与失效链接修正（文档贡献） |

## 项目中使用的技术

Python · FastAPI · SQLAlchemy · ChromaDB · React · Vite · pytest · Playwright · Docker · FastMCP / MCP · FSRS · JWT

## 技术笔记

- [手写 RAG 管线的 5 个设计决策](https://juejin.cn/post/7665944296248442906)
- [Python 上下文管理器深度剖析](https://juejin.cn/post/7676404079284469796)
