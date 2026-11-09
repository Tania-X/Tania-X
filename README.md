# 粟思源 / Max

**Java 后端工程师 · 5 年 · 券商交易系统出身**

5 年 Java，主要在券商做交易系统（场务端）：改过服务架构，重建过权限体系，也把国产化替换用生产流量做过并行验证。
2026 年起做 DevOps 平台和 LLM 应用落地。

我关心的两件事：同一个输入跑两次，结果要对得上；改了一次 prompt，指标要在 CI 里看得见变化。

主力是 Java。Python / Go / React 侧在 AI 协作下交付，能读、能改、能排障。

广州 · 英语可作为工作语言 · 可远程

---

## 在做的东西

**[dify-rag-lab](https://github.com/Tania-X/dify-rag-lab)** — 企业知识库 RAG 问答（**Java 17 / Spring Boot**）
Dify 负责切块、向量化和检索，外面套一层 Spring Boot 网关：鉴权、聚合、审计都在网关里，前端不碰 Dify 的 API Key。
为了搞清楚 Dify 的检索到底多做了什么，自己写了一版混合检索（向量召回 + BM25），拿 14 条评测题按 hit@1 / hit@5 对比两边。

**[ai-tools](https://github.com/Tania-X/ai-tools)** — AI 代码审查引擎（Python，AI 协作开发）
agent 多轮调用工具，对外是标准 MCP server，调用链用 OpenTelemetry 追踪。重点在评测：黄金场景集按严重度分级统计精确率和召回率，
改一次 prompt 就是数字上的 diff。
→ 同一批场景跟 Claude Code 逐条比过，9 个结论全部一致。

**[devops-dashboard](https://github.com/Tania-X/devops-dashboard)** — 自建运维平台（Go + React，AI 协作开发）
服务器资产、SSH 批量分发、许可证到期告警。Docker 多服务镜像、CI 推 ghcr.io、OpenTelemetry + Jaeger。
一个人从零做到上线，之后一直在上面运维。

**同一账号下还有**：semif-gate（Java 17 写的 Agent 判定网关，181 个测试不连数据库、不需要 GPU）、
ai-review-golden-tests（上面那套引擎的评测集），以及几个 RAG 和 agent 方向的实验。

---

## 做事方式

**契约先行：接口先定死，再写实现。** 金证那套 DevOps 平台是从 OpenAPI 契约开始的——契约用代码生成器出骨架，
实现只能长在契约里面，AI 补的代码也一样。评审的时候看契约比看实现快得多。

**小步发布：一块做完就上一块。** 平台一期拆成组件管理、产品管理、版本管理、CI 触发四块，做完一块上一块，
每块都能单独验证。个人项目也是这个路子：`devops-dashboard` 是一块一块加上去的，不是一次憋出来的。

**先跑通，再拆开看。** `dify-rag-lab` 一开始是拿 Dify 现成能力把链路跑通，跑通之后才自己写一版混合检索跟它对比
——不这么做，就不知道 Dify 到底替你做了哪些事。

---

## 技术栈

**Core**：`Java` `Spring Boot / Cloud` `Spring Security` `Netty` `MyBatis` `JVM 排障`
**Data**：`MySQL` `Redis` `Kafka` `RabbitMQ` `OceanBase` `Vastbase` `Weaviate`
**Engineering**：`Docker` `Kubernetes` `Jenkins` `GitHub Actions` `Grafana` `OpenTelemetry`
**AI 工程化**：`RAG（切分 / 向量召回 / Rerank）` `hit@k 评测` `MCP` `Agent 工具调用` `LLM-as-Judge`

📫 13126565350@163.com

---

<details>
<summary><b>English</b></summary>

### Su Siyuan / Max — Java backend engineer

Five years of Java, mostly trading systems for brokerages: a service architecture rework, an RBAC rebuild,
and a domestic-database migration validated against production traffic in parallel. Since 2026 I've been
working on DevOps platforms and LLM application delivery.

Two things I care about: the same input twice gives the same result, and a prompt change shows up as a number in CI.

Java is my main stack. Python / Go / React get delivered with AI in the loop — I can read, change, and debug them.

Guangzhou, China · English as a working language

**Projects**

- [dify-rag-lab](https://github.com/Tania-X/dify-rag-lab) — RAG knowledge-base Q&A. Spring Boot gateway in front of Dify;
  a hand-written hybrid retriever (vector recall + BM25) benchmarked against Dify's retrieval on 14 questions with hit@1 / hit@5.
- [ai-tools](https://github.com/Tania-X/ai-tools) — agentic code review engine, exposed as an MCP server, traced with OpenTelemetry.
  Golden scenario set scores precision/recall per severity; 9/9 parity against Claude Code on the same set.
- [devops-dashboard](https://github.com/Tania-X/devops-dashboard) — self-hosted ops platform (Go + React). Docker images,
  CI to ghcr.io, OpenTelemetry + Jaeger. Built and operated end-to-end.

</details>
