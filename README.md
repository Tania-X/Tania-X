# 粟思源 / Max

**后端工程师：Java、Go，以及让 LLM Agent 变得可信的那套基础设施。**

我做 AI 系统里不性感的那一半 —— 让模型行为可复现到能放进 CI 流水线的程度：评测集、决策网关、审计链路，以及让它们保持诚实的运维管道。

广州（UTC+8）· 5 年 Java 后端（金融交易系统 / DevOps 平台）· 全英文工作环境 · 可远程

<sub>[English version ↓](#english)</sub>

---

## 在做的东西

**[ai-tools](https://github.com/Tania-X/ai-tools)** — AI 代码审查引擎，已在真实 PR 上跑
agentic 工具调用 + 质量门，封装为标准 MCP server，OpenTelemetry 全链路追踪。重点不在功能，在评测：
黄金场景集按严重度分级统计精确率/召回率，改一次 prompt 是数字上的 diff，不是感觉。
→ 同一场景集与 Claude Code **9/9 对齐**，且严重度策略是自发涌现的，没有被注入。

**[semif-gate](https://github.com/Tania-X/semif-gate)** — Agent 决策网关（Java 17）
把"模型的判定"变成可缓存、可计量、可审计的基础设施：完整概率分布、契约指纹进缓存键、
降级永远 fail-closed 而不是猜一个。
→ **181 个测试。不连外网、不需要数据库、不需要 GPU。**

**[ai-review-golden-tests](https://github.com/Tania-X/ai-review-golden-tests)** — 上面那套引擎的评测集
带已知答案的场景矩阵，作为 CI 里的回归门禁。

**[devops-dashboard](https://github.com/Tania-X/devops-dashboard)** — 自建运维平台
服务器资产、SSH 批量分发、许可证到期告警、Webhook 集成。Go + React、Docker 多服务镜像、
CI 推 ghcr.io、OpenTelemetry + Jaeger。**一个人从 0 做到上线并持续运维。**

---

## 三件在我每个仓库里都能看到的事

**先测量，再设计。** 我怀疑决策 prompt 里选项顺序有语义，就去测了一遍：只调换顺序，**30.6%** 的判定翻转；
换一块 GPU，只动 **0.7%** —— 差 40 倍。所以顺序现在进了缓存键：复用旧结果在机制上不可能，
而不是靠"记得升版本"。

**公开改正自己的结论。** 三份设计文档里都留着对早期结论的明确更正，标注为更正，并链到推翻它的那次改动。
没有悄悄改掉。一个能推翻我设计的测量，是最有价值的东西。

**把不变式放进类型系统，而不是放进约定。** `state.hash() == sha256(state.json())` 之所以恒成立，
是因为能破坏它的构造函数不对外公开。"记得升版本"不是控制手段，一个撞不上的缓存键才是。

---

`Java` `Go` `Python` `TypeScript / React` `Spring Boot` `Gin` `PostgreSQL` `Redis`
`Docker` `Kubernetes` `GitHub Actions` `OpenTelemetry / Jaeger` `MCP` `LLM 路由与评测`

📫 13126565350@163.com

---

<a id="english"></a>

<details>
<summary><b>English version — click to expand</b></summary>

<br>

### Backend engineer — Java, Go, and the infrastructure that makes LLM agents trustworthy.

I build the unglamorous half of AI systems: the part that makes model behaviour reproducible
enough to put in a CI pipeline. Evaluation sets, decision gateways, audit trails, and the ops
plumbing that keeps all of it honest.

Based in Guangzhou (UTC+8) · 5 years of Java backend work (securities trading systems, DevOps
platforms) · English working environment · open to remote collaboration

---

#### What I'm building

**[ai-tools](https://github.com/Tania-X/ai-tools)** — an AI code review engine, running on real PRs
Agentic review with tool calling, packaged as an MCP server, traced end-to-end with OpenTelemetry.
The part that matters is the evaluation: a golden scenario set scores precision and recall *per
severity level*, so changing a prompt is a diff in numbers instead of an opinion.
→ 9/9 parity against Claude Code on the same scenario set — and the same severity rules emerged
without being injected.

**[semif-gate](https://github.com/Tania-X/semif-gate)** — an agent decision gateway (Java 17)
Turns a model verdict into cacheable, metered, auditable infrastructure: full probability
distribution, contract fingerprint inside the cache key, degradation that always fails closed
rather than guessing.
→ 181 tests. No network, no database, no GPU.

**[ai-review-golden-tests](https://github.com/Tania-X/ai-review-golden-tests)** — the evaluation set
behind the engine above. A scenario matrix with known-good answers, used as a regression gate in CI.

**[devops-dashboard](https://github.com/Tania-X/devops-dashboard)** — a self-hosted ops platform
Server inventory, SSH fan-out, licence expiry alerting, webhook integrations. Go + React, Docker
multi-service images, CI to ghcr.io, OpenTelemetry + Jaeger. Built and operated end-to-end, alone.

---

#### Three things you'll find in every repo here

**I measure instead of guessing.** I suspected option ordering in our decision prompts was
semantically meaningful, so I measured it: reordering options flipped 30.6% of decisions, while
swapping the GPU moved them 0.7% — a 40× difference. The order is now part of the cache key,
so reusing a stale result is mechanically impossible rather than a matter of remembering to
bump a version.

**I correct myself in public.** Three of my design documents carry an explicit correction of an
earlier conclusion, labelled as a correction, linked from the change that overturned it. Not
quietly edited. A measurement that contradicts my design is the most useful thing I can get.

**I put invariants in the type system, not in a convention.** `state.hash() == sha256(state.json())`
holds because the constructor that would break it isn't public. "Remember to bump the version"
is not a control; a cache key that can't collide is.

---

`Java` `Go` `Python` `TypeScript / React` `Spring Boot` `Gin` `PostgreSQL` `Redis`
`Docker` `Kubernetes` `GitHub Actions` `OpenTelemetry / Jaeger` `MCP` `LLM routing & evaluation`

📫 13126565350@163.com

</details>
