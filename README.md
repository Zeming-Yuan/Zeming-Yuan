# 袁仕杰 Zeming

Python 后端 · AI 应用开发｜RAG / Agent / MCP｜广东

做能跑在真实环境里的 AI 系统：数字员工总台、知识库问答、编程助手，以及社媒与客服链路。偏好可评测、可私有化、带审批与审计边界的工程实现。

## 当前在做

与团队推进多条产品线（仓库多为私有，此处只写产品定位）：

**AI 数字员工**
- 总台 + 子节点：在浏览器里创建数字员工、派到多台电脑执行任务，看屏 / 远程管理 / 审批闸门；Hub（FastAPI）· Node · Web（React 19 + TypeScript）
- 对接飞书等消息渠道、团队资料库、技能录制与安装

**编程助手**
- Web 工作台：浏览器对话、预览、下载与发布；DeepSeek + 本机编码智能体
- 桌面端：多 Agent 会话 GUI（Claude Code / Codex / Cursor / Grok 等），按项目组织会话与 worktree

**知识库与评测**
- 工厂场景私有化 AI 知识库：SOP / 手册入库、检索问答、金标评测与部署证据；数据不出厂
- 与直播 / 客服侧的有据回答衔接

**社媒 · 直播 · 客服**
- 社媒一分多发：一份成片经审核后发到多个已授权账号（Facebook / Instagram / YouTube / X / TikTok 等）
- AI 语音直播：单房间评论接收 → 知识库 / 通用回答 → 克隆音色播报（抖音 / 视频号方向）
- 渠道客服：WhatsApp ↔ Chatwoot 坐席闭环；微信桌面 Assist；阿里国际站 BMS 工厂咨询（知识库 + 人工接管）

**企业系统与运营后台**
- OPC 类企业管理系统（入驻主体 / 物业资源 / 政府·运营·物业多方协作）
- 多项目只读运营控制台（聚合编程助手与数字员工等产品的指标与审计）
- 本地双机视频批量生产（LTX 竖屏短片无人值守流水线）

## 开源项目（独立开发）

- [capstone-ai-kb](https://github.com/Zeming-Yuan/capstone-ai-kb) — RAG 知识库问答 + NL2SQL ReAct Agent：手写 ReAct（不调 LangChain）· FastAPI · ChromaDB · Redis · Docker；含评测与线上 Demo
- [claude-code-memory-system](https://github.com/Zeming-Yuan/claude-code-memory-system) — Claude Code 记忆网关（基于腾讯开源引擎二次开发）：FastMCP · L0–L3 分层记忆 · Hooks 全自动化 · 本地 BM25 + 向量双路检索
- [english-coach](https://github.com/Zeming-Yuan/english-coach) — **进行中** · 零基础英语 AI 学习：FSRS 间隔复习 · DeepSeek 词卡 · React 19 + FastAPI · 学习科学脚手架（意群切分 / 提取练习等）

## 开源协作

**已合并**

- [wandb/rai-toolkit](https://github.com/wandb/rai-toolkit) — RAG 检索质量评测：[#37](https://github.com/wandb/rai-toolkit/pull/37) `RetrievalRelevanceScorer`、[#58](https://github.com/wandb/rai-toolkit/pull/58) `ContextPrecisionScorer` / `ContextRecallScorer`
- [redis/redis-py](https://github.com/redis/redis-py) — [#4294](https://github.com/redis/redis-py/pull/4294)、[#4295](https://github.com/redis/redis-py/pull/4295) 示例 notebook 文档修正
- [longsizhuo/BossZhiPin_Job_Search](https://github.com/longsizhuo/BossZhiPin_Job_Search) — [#40](https://github.com/longsizhuo/BossZhiPin_Job_Search/pull/40) 关键词提取失败不再写入空列表毒化粗筛缓存

**协作中**

- [TencentCloud/TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory) — [#1365](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/1365)（closed，未合并）、[#1366](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/1366)（open）记忆提炼 / 向量写入相关修复

## 技术栈

**后端** · Python · FastAPI · Pydantic v2 · SQLAlchemy · Redis · SQLite / PostgreSQL · pytest · Docker

**检索与 Agent** · ChromaDB · bge-m3 · BM25 + RRF · MCP / FastMCP · ReAct 手写编排

**前端与桌面** · TypeScript · React 19 · Vite · Node.js

**工程** · 私有化 / Compose 交付 · 评测金标与证据门禁 · 审批与审计边界
