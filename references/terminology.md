# 专业术语对齐

原则只有三条：

1. 系统、库、模型、基准、协议缩写、API / 类名：保持英文原名（含大小写、连字符、希腊字母）。
2. 课程概念：用该系列已固定的中文，并与课件一致。
3. 拿不准时对照该讲官方 PDF / notebook，不要意译。

后续新讲若出现未收录术语：专有名词保持原文；概念词先查课件与已发布各讲是否已有固定译法，再沿用。

## 系列通用

| 英文 | 中文处理 |
| --- | --- |
| agent / agents | 智能体 |
| agentic | 智能体 / 智能体式 / 智能体系统工程（按上下文） |
| LLM / large language model | 大语言模型；后文可写「大模型」。单独出现的 LLM 也可保留 |
| tool use | 工具使用 |
| tool call / tool calling | 工具调用 |
| API | API |
| evaluation | 评估（讲评测体系时）；evals 作工程环节时用「评测」 |
| dataset | 数据集 |
| metric | 指标 |
| prompt | 提示；system prompt 译为「系统提示」，像 `dspy.SystemPrompt` 这样的标识符保持原样 |

## 工具使用 / 函数调用 / MCP

| 英文 | 中文处理 | 说明 |
| --- | --- | --- |
| RAG | RAG | 不译 |
| retrieval | 检索 | |
| reader | 阅读器 | RAG 的 reader 侧 |
| permission leak | 权限泄露 | |
| lost in the middle | 中间丢失 | 首次加英文对照 |
| hallucination | 幻觉 | |
| citation hallucination | 引用幻觉 | |
| function calling / function call | 函数调用 | |
| REST | REST | 不译 |
| MCP | MCP | 不译 |
| Model Context Protocol | 模型上下文协议 | 首次可写「模型上下文协议（Model Context Protocol）」 |
| standard interface | 标准接口 | |
| Toolformer / ToolkenGPT / ToolLLM / Gorilla | 保持原名 | 不译 |
| ToolLLaMA | ToolLLaMA | 与 LLaMA 写法一致 |
| LLaMA | LLaMA | 不写成 Llama（除非原文如此） |
| AST | AST | 「基于 AST 的设定」这类说法即可 |
| BFCL / Berkeley Function-Calling Leaderboard | Berkeley 函数调用排行榜（BFCL） | 首次给全称，后文可用 BFCL |
| ToolBench | ToolBench | 不译 |
| τ-bench / τ²-bench / τ-knowledge / τ-voice | 保持希腊字母原文 | 不要写成 tau-bench |
| pass^k / pass@k | 保持原符号 | 二者趋势不同，不可混用 |
| FastMCP | FastMCP | 不译 |
| SFT | SFT | 不译 |
| distillation | 蒸馏 | |
| reasoning traces | 推理轨迹 | 蒸馏语境；与可观测性里的 trace 区分 |

## 框架与编排 / DSPy / LangGraph

| 英文 | 中文处理 | 说明 |
| --- | --- | --- |
| frameworks & orchestration | 框架与编排 | |
| framework | 框架 | |
| abstraction | 抽象 | |
| orchestration | 编排 | |
| telemetry | 遥测 | |
| observability | 可观测性 | |
| workflow | 工作流 | |
| compound AI system | 复合 AI 系统 | |
| spectrum of agency | 自主性谱系 | |
| control flow | 控制流 | |
| DSPy / LangGraph / LangChain | 保持原名 | 不译 |
| signature | 签名 | DSPy 的 signature |
| module | 模块 | DSPy 的 module |
| optimizer | 优化器 | |
| Predict / dspy.Prediction / dspy.ReAct / dspy.LM / dspy.SystemPrompt | 保持原标识符 | |
| chain of thought（口头策略） | 思维链 | 作为推理策略时译出；模块名若写作 ChainOfThought 则保持原名 |
| ReAct | ReAct | 架构名不译 |
| GEPA | GEPA | 可写「GEPA 优化器」 |
| state | 状态 | LangGraph 的共享工作空间 |
| node | 节点 | 含起始节点、终止节点 |
| edge | 边 | |
| conditional edge | 条件边 | |
| create_agent | create_agent | API 名不译 |
| Deep Agents / Harness / mini-SWE-agent / OpenHands / Pi / OpenClaw / Meta-Harness / Shepherd / Temporal | 保持原名 | Harness 可写「智能体 Harness」，不另造译名 |
| Activities / Activity / Workers / Worker | 保持英文 | Temporal 术语 |
| durable execution | 持久执行 | |
| LangFuse / MLflow / LangSmith / LiteLLM / OpenRouter / RLM / Terminal-Bench / SWE-bench | 保持原名 | 不译 |
| traces / trace | trace | 可观测性语境下保持英文 |
| evals | 评测 | |
| pass rate | 通过率 | |
| exact match | 精确匹配 | |
| LLM-as-a-Judge / LLM-as-Judge | LLM-as-Judge | 可保留英文形式 |
| structured output | 结构化输出 | |
| rollout | rollout | 训练 / 优化语境下不译 |
| jailbreak | 越狱 | |
