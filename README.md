<p align="center">
  <img src="assets/logo.svg" width="128" height="128" alt="architecture-design logo">
</p>

<h1 align="center">architecture-design</h1>

<p align="center">
  <strong>把目标收敛成可实施、可组合、可验证的架构设计 skill</strong><br>
  需求澄清 · 功能拆解 · 架构设计 · 反例验证
</p>

<p align="center">
  <a href="https://github.com/Luo-root/architecture-design/blob/main/LICENSE"><img src="https://img.shields.io/github/license/Luo-root/architecture-design?style=flat-square" alt="License"></a>
  <a href="https://github.com/Luo-root/architecture-design/stargazers"><img src="https://img.shields.io/github/stars/Luo-root/architecture-design?style=flat-square" alt="Stars"></a>
  <a href="https://github.com/Luo-root/architecture-design/issues"><img src="https://img.shields.io/github/issues/Luo-root/architecture-design?style=flat-square" alt="Issues"></a>
  <img src="https://img.shields.io/badge/format-Agent%20Skill-0ea5e9?style=flat-square" alt="Agent Skill">
  <img src="https://img.shields.io/badge/language-中文-2563eb?style=flat-square" alt="Chinese-first">
</p>

> `architecture-design` 从需求澄清和功能拆解开始，把产品目标、现有方案和工程约束整理成一套能落地的架构设计与功能契约。它会先弄清为谁做、做什么、做到什么程度，再落实责任、接口、数据、失败恢复与验收。

## 它解决什么

从一句“我要做一个商城软件”到可以开发的方案，需要逐步回答：

- 服务谁、卖什么或处理什么内容、有哪些角色、首版完成哪些流程；
- 访问量和数据量大概多大、有什么质量目标，以及时间、预算和环境约束；
- 每项能力由谁负责，事实源在哪里，哪些事情明确不负责；
- 多入口、多提供方或插件加入后，身份、授权、状态和错误语义是否仍然一致；
- 请求超时、连接断开、取消、重试或进程崩溃之后，结果如何判断和恢复；
- 数据如何提交、迁移、保留和清理，算法、模式和技术依赖如何选定与验证。

需求模糊时，它会先提出少量关键问题，随着答案整理功能点和约束；需求足以支撑本次设计后，再闭合功能契约和技术决策，用反例检查方案。已有明确需求的任务可以直接复用，不必重做整轮访谈。

## 核心能力

| 能力 | 关注点 |
|---|---|
| 需求澄清 | 从目标、角色、业务流程和规模出发，分轮反问，区分已确认需求、候选和假设 |
| 功能拆解 | 边澄清边整理业务动作，明确首版/后续/排除范围，保留规模、质量和交付约束 |
| 功能全集 | 用稳定的功能 ID 追踪需求，覆盖适用的用户操作、后台能力、扩展点、外部连接、迁移、清理和诊断 |
| 八项契约 | 对每项功能明确职责、输入输出、不负责、交接、授权、生命周期、失败并发、限制验收 |
| 组合设计 | 根据真实变化轴设置提供方、注册表、Port 和公共服务，避免入口复制业务逻辑 |
| 技术决策 | 把算法、模式、框架、数据库、协议和运行时落到版本、接线、代价与重审条件 |
| 反例审查 | 针对双提交、旧执行、外部副作用、版本切换、导入、删除、容量等风险构造可观察结果 |
| 证据边界 | 区分已决定、建议、待验证和阻断；没有实测时不把设计预算写成性能保证 |

## 安装

把下面的仓库地址直接交给 Agent，并告诉它“安装这个 Skill”即可：

https://github.com/Luo-root/architecture-design

安装完成后，让 Agent 读取 `SKILL.md`，再用自然语言描述任务即可。Skill 的核心文件只依赖 Markdown，不需要额外运行时依赖。

## 怎么使用

适合直接提出这些任务：

```text
我想做一个商城软件，用 architecture-design 先帮我捋清需求和功能点。

用 architecture-design 为这个产品设计一套可实施的完整架构。

开发前先把这个功能的边界、功能契约和失败恢复定清楚。

审查现有方案，找出职责重叠、第二个真相源和悬空交接。

对比两种技术路线，给出接线方式、迁移代价、验证门槛和重审条件。

把这份架构方案按反例走一遍，重点检查并发、重试、升级和删除。
```

任务规模较小时输出一页即可；涉及多个模块、扩展点或副作用时，按责任拆成索引和章节。每个尚未验证的能力都应有责任人、证据、影响范围、失败退出路径和解除条件。

## 工作方式

1. **读取已有事实**：复用当前请求、已确认讨论、现行文档与相关实现，标明来源。
2. **澄清需求并拆功能**：每轮优先问少量关键问题，更新角色、流程、规则、功能清单和非功能约束；访问量未知时先用数量级。
3. **判断能否进入设计**：本次范围足够明确即可推进；未知部分保留假设或问题，不强行等全部细节确定。
4. **闭合逐功能契约**：沿着输入、授权、执行、提交、观察、恢复和清理走通副作用链路。
5. **落地关键决策**：说明约束、候选、选择、具体接线、版本兼容、代价和重审条件。
6. **运行反例与对抗检查**：构造并发、崩溃、旧版本、外部成功、本地超时等具体交错。
7. **收敛并追踪变化**：先沿用编号账本，再更新需求、功能、契约、决策和验收；新增事项追加编号，拆分合并记录对应关系，退役编号保留原义。交付前对照上一轮清单，需求改变时重审受影响部分。

需求阶段交付需求摘要、初版功能清单、问题和假设；架构阶段补齐责任、接口、数据及失败机制。用户已给出明确材料时，只补缺口。

## 验证

[需求澄清样本](evals/requirements-discovery-cases.json) 固定输入和原 18 项检查，另列编号连续性检查。样本包括分轮推进的商城需求（规模未知、补齐规则、进入设计、途中改需求），以及需求已明确的局部改动。

[编号账本流程重跑](evals/requirements-discovery-rerun.json) 在本轮样本中通过原 18 项检查，编号连续性另项通过，并关联新基线、实际逐轮答复和独立判读。[历史执行记录](evals/requirements-discovery-results.json) 保留之前 16/18 及辅助纠错后仍失败的事实。新流程从新上下文重跑，没有将旧失败覆盖成通过，也没有向执行者提供旧错误提示或未来用户答案。

这些是单次合成样本的执行记录，不代表所有领域、模型、宿主或真实访谈界面都已验证。

## 目录

```text
.
├── SKILL.md
├── references/
│   ├── requirements-discovery.md
│   ├── composition-and-review.md
│   ├── feature-contract.md
│   └── mechanism-decisions.md
├── assets/
│   └── logo.svg
├── evals/
│   ├── requirements-discovery-cases.json
│   ├── requirements-discovery-results.json
│   ├── requirements-discovery-rerun.json
│   └── runs/
├── LICENSE
├── .gitattributes
└── README.md
```

- `SKILL.md`：触发条件、需求到架构的执行流程、功能覆盖、技术决策和完成门槛。
- `references/requirements-discovery.md`：分轮提问、需求事实、功能拆解、进入设计的条件与需求变更处理。
- `references/composition-and-review.md`：组合轴、提供方契约、风险反例与对抗闭环。
- `references/feature-contract.md`：八项功能契约、事实源、存储决策和覆盖矩阵模板。
- `references/mechanism-decisions.md`：算法、设计模式和技术选型的记录模板与评审清单。

## 设计边界

- “待验证”表示需要补证据，不表示可以省略内部机制。
- 设计结论会标明证据强度；静态阅读、文档依据和实际探针分别表达。
- 设计完成不等于代码、跨平台行为或生产能力已经验证。
- 安装、部署、发布、迁移、删数据和产生费用都需要明确授权与执行边界。

## 贡献

欢迎通过 Issue 或 Pull Request 提交新的反例、契约模板和可复现的设计缺口。修改 `SKILL.md` 或 `references/` 时，请同时说明：

- 触发问题的具体输入、交错或使用场景；
- 预期行为与当前行为的差异；
- 最小修改点和不会破坏的既有规则；
- 对应的验证方式或仍待验证的部分。

请保留 `SKILL.md` 的 YAML frontmatter、相对引用和 LF 换行格式。

## License

[MIT](LICENSE) © 2026 jiangnan (Luo-root)

如果这份 Skill 对你的架构工作有帮助，欢迎在 GitHub 上点一个 Star，或提交一个能让契约更完整的例子。
