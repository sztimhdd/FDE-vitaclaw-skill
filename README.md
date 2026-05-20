<div align="center">

# FDE Operator OS

[English](#english) | [中文](#中文)

![FDE Operator OS Banner EN](./assets/readme/banner-en.svg)

</div>

<a id="english"></a>

## English

An operator-grade FDE skill and reusable operator playbook for forward deployed engineers, applied AI leads, and delivery owners who need to turn messy customer problems into delivery-worthy AI operating loops.

### What It Is

`fde-operator-os` is a general-purpose FDE skill for:

- qualifying whether an AI opportunity is worth pursuing
- modeling operational reality instead of idealized process maps
- framing the real system bottleneck
- designing ontology, action surfaces, and human-in-the-loop boundaries
- compressing a broad idea into a minimum viable loop
- defining a delivery-ready path from pilot to expansion

It is intentionally cross-industry. Domain cases should stay outside the core skill unless you choose to maintain a separate case pack.

### Who It Is For

This skill is written for:

- Forward Deployed Engineers
- Applied AI Engineers
- AI delivery leads
- solution architects working on operational AI systems
- founders or early delivery teams doing customer-specific AI implementations

It is not optimized for:

- pure prompt tinkering
- generic AI workshops
- one-off coding tasks with no delivery framing

### Core Model

The skill runs a seven-stage decision chain:

1. Mission Qualification
2. Operational Reality Capture
3. System Framing
4. Ontology & Action Model
5. Intervention & Pilot Design
6. Delivery Architecture
7. Expansion Logic

It also ships with eight operator artifacts:

- Mission Brief
- Operational Reality Map
- System Problem Frame
- Ontology & Action Model
- AI Intervention Design
- Minimum Viable Loop
- POC Acceptance Contract
- Expansion Roadmap

### Repository Layout

```text
fde-operator-os/
├── SKILL.md
├── README.md
├── LICENSE
├── agents/
│   └── openai.yaml
├── references/
│   ├── doctrine.md
│   ├── operator-heuristics.md
│   └── failure-patterns.md
└── assets/
    ├── readme/
    │   ├── banner-en.svg
    │   └── banner-zh.svg
    └── templates/
        ├── mission-brief.md
        ├── operational-reality-map.md
        ├── system-problem-frame.md
        ├── ontology-action-model.md
        ├── ai-intervention-design.md
        ├── minimum-viable-loop.md
        ├── poc-acceptance-contract.md
        └── expansion-roadmap.md
```

### Install

You can use this repository in two ways:

1. As a Codex-style skill by copying the folder into your local skills directory.
2. As a portable FDE playbook by adapting the doctrine, references, and templates to your own agent or delivery workflow.

Example Codex-style install:

```powershell
Copy-Item -Recurse .\fde-operator-os "$HOME\.codex\skills\"
```

Then use prompts like:

- `Use $fde-operator-os to decide whether this AI opportunity is worth pursuing.`
- `Use $fde-operator-os to turn this workflow into a minimum viable loop.`
- `Use $fde-operator-os to define the operator artifacts for this pilot.`

### Design Principles

- Qualify before designing.
- Model the real operating system, not the narrated one.
- Solve for closed-loop outcomes, not feature demos.
- Keep AI on the narrowest surface that creates measurable value.
- Treat ownership, trust, and auditability as design constraints.

### Validation

This skill passes the standard skill validation flow with `quick_validate.py`.

### License

MIT

---

<a id="中文"></a>

## 中文

这是一个面向 Forward Deployed Engineer、Applied AI 交付负责人和方案架构角色的通用 FDE skill / operator playbook，用来把混乱的客户问题推进成可交付、可验证、可扩展的 AI 运营闭环。

### 它解决什么问题

`fde-operator-os` 适合用来：

- 判断一个 AI 机会到底值不值得做
- 把真实业务现场而不是理想流程结构化出来
- 找到真正的系统瓶颈，而不是堆功能清单
- 设计 ontology、action surface 和人机边界
- 把宽泛想法压缩成一个最小可验证闭环
- 定义从 pilot 到规模化扩展的交付路径

它默认是跨行业的。领域案例建议留在 skill 外部，按你自己的私有项目或独立 case pack 来验证。

### 它更适合谁

- FDE / 前线部署工程师
- Applied AI 工程师
- AI 交付负责人
- 负责运营型 AI 系统的方案架构师
- 做客户定制 AI 落地的创始团队或早期交付团队

它不适合：

- 纯 prompt 调优
- 泛 AI 培训工作坊
- 没有交付 framing 的一次性编码任务

### 核心框架

这套 skill 采用 7 阶段 FDE 决策链：

1. Mission Qualification
2. Operational Reality Capture
3. System Framing
4. Ontology & Action Model
5. Intervention & Pilot Design
6. Delivery Architecture
7. Expansion Logic

并配套 8 个标准 operator artifacts：

- Mission Brief
- Operational Reality Map
- System Problem Frame
- Ontology & Action Model
- AI Intervention Design
- Minimum Viable Loop
- POC Acceptance Contract
- Expansion Roadmap

### 安装

这个仓库可以有两种用法：

1. 作为 Codex 风格 skill，复制到本地 skills 目录。
2. 作为通用 FDE playbook，把 doctrine、references 和 templates 迁移到你自己的 agent 或交付流程里。

如果按 Codex 风格使用，可以这样安装：

```powershell
Copy-Item -Recurse .\fde-operator-os "$HOME\.codex\skills\"
```

然后可以这样调用：

- `Use $fde-operator-os to decide whether this AI opportunity is worth pursuing.`
- `Use $fde-operator-os to turn this workflow into a minimum viable loop.`
- `Use $fde-operator-os to define the operator artifacts for this pilot.`

### 设计原则

- 先判断值不值得做，再谈设计
- 建模真实 operating system，而不是照抄口头流程
- 目标是闭环结果，不是功能演示
- 把 AI 压在最窄但最有价值的介入面上
- 把 ownership、trust 和 auditability 当作设计约束

### 验证

该 skill 已通过标准 `quick_validate.py` 校验。

### License

MIT
