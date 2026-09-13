# 袁仕杰 Zeming

Python 后端开发（AI 应用方向）· 深圳

## 开源项目（独立开发）

- 🔎 [capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb) — RAG 知识库问答系统 + NL2SQL ReAct Agent：FastAPI · ChromaDB · Redis · Docker，手标 42 条真值评测集（中文问答 hit@10 = 0.90）
- 🧠 [claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system) — Claude Code 记忆网关（基于腾讯开源引擎二次开发）：FastMCP 封装 · L0-L3 分层记忆 · Hooks 全自动化
- 📚 [english-coach](https://github.com/Zeming-Yuan/english-coach) — 零基础英语 AI 学习工具：FSRS 间隔复习 · DeepSeek 词卡生成 · React 19 + FastAPI · 108 条测试全绿

## 开源协作

**已合并**

- [wandb/rai-toolkit](https://github.com/wandb/rai-toolkit) — RAG 检索质量评测：[#37](https://github.com/wandb/rai-toolkit/pull/37) 新增 `RetrievalRelevanceScorer`（LLM-as-a-Judge 逐 chunk 相关性评分）、[#58](https://github.com/wandb/rai-toolkit/pull/58) 新增 `ContextPrecisionScorer` / `ContextRecallScorer`
- [redis/redis-py](https://github.com/redis/redis-py) — [#4294](https://github.com/redis/redis-py/pull/4294)、[#4295](https://github.com/redis/redis-py/pull/4295) 示例 notebook 文档修正

**协作中**

- [TencentCloud/TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory) — [#1365](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/1365)、[#1366](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/1366) 修复记忆提炼链路上游缺陷（向量写入静默失败 / 会话结束不触发提炼）
- [longsizhuo/BossZhiPin_Job_Search](https://github.com/longsizhuo/BossZhiPin_Job_Search) — [#40](https://github.com/longsizhuo/BossZhiPin_Job_Search/pull/40) 毒缓存 bug 双侧修复

## 技术栈

Python · FastAPI · Pydantic v2 · SQLAlchemy · Redis · ChromaDB · bge-m3 · BM25+RRF · pytest · Locust · Docker
