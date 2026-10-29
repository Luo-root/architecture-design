<p align="center">
  <img src="assets/logo.svg" width="128" height="128" alt="architecture-design logo">
</p>

<h1 align="center">architecture-design</h1>

<p align="center">
  <strong>把目标收敛成可实施、可组合、可验证的架构设计 skill</strong><br>
  功能契约 · 技术决策 · 失败恢复 · 反例审查
</p>

<p align="center">
  <a href="https://github.com/Luo-root/architecture-design/blob/main/LICENSE"><img src="https://img.shields.io/github/license/Luo-root/architecture-design?style=flat-square" alt="License"></a>
  <a href="https://github.com/Luo-root/architecture-design/stargazers"><img src="https://img.shields.io/github/stars/Luo-root/architecture-design?style=flat-square" alt="Stars"></a>
  <a href="https://github.com/Luo-root/architecture-design/issues"><img src="https://img.shields.io/github/issues/Luo-root/architecture-design?style=flat-square" alt="Issues"></a>
  <img src="https://img.shields.io/badge/format-Agent%20Skill-0ea5e9?style=flat-square" alt="Agent Skill">
  <img src="https://img.shields.io/badge/language-中文-2563eb?style=flat-square" alt="Chinese-first">
</p>

> `architecture-design` 用来把产品目标、现有方案和工程约束整理成一套能落地的架构设计与功能契约。它关注责任边界、组合关系、接口和数据语义，也关注失败、并发、恢复、迁移与验收。

## 它解决什么

很多架构文档能讲清楚“系统由哪些组件组成”，却没有讲清楚下面这些决定实现成败的问题：

- 每项能力由谁负责，事实源在哪里，哪些事情明确不负责；
- 多入口、多提供方或插件加入后，身份、授权、状态和错误语义是否仍然一致；
- 请求超时、连接断开、取消、重试或进程崩溃之后，结果是确定、失败还是未知；
- 数据如何提交、恢复、迁移、保留和清理，哪些数字是预算，哪些数字已经经过测量；
- 一个算法、设计模式或技术依赖具体解决了什么变化，怎样验证，什么时候重新选择。

它会先建立功能全集和决策账本，再逐项闭合功能契约，最后用反例和证据检查设计是否真的收敛。

## 核心能力

| 能力 | 关注点 |
|---|---|
| 功能全集 | 用稳定的功能 ID 覆盖用户操作、后台能力、扩展点、外部连接、迁移、清理和诊断 |
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
用 architecture-design 为这个产品设计一套可实施的完整架构。

开发前先把这个功能的边界、功能契约和失败恢复定清楚。

审查现有方案，找出职责重叠、第二个真相源和悬空交接。

对比两种技术路线，给出接线方式、迁移代价、验证门槛和重审条件。

把这份架构方案按反例走一遍，重点检查并发、重试、升级和删除。
```

任务规模较小时输出一页即可；涉及多个模块、扩展点或副作用时，按责任拆成索引和章节。每个尚未验证的能力都应有责任人、证据、影响范围、失败退出路径和解除条件。

## 工作方式

1. **固定目标与证据**：区分已确认需求、已有实现、设计决定、假设和待验证事项。
2. **建立功能全集**：为用户可见能力、后台任务、扩展点、外部连接和维护任务分配稳定 ID。
3. **闭合逐功能契约**：沿着输入、授权、执行、提交、观察、恢复和清理走通副作用链路。
4. **落地关键决策**：说明约束、候选、选择、具体接线、版本兼容、代价和重审条件。
5. **运行反例与对抗检查**：构造并发、崩溃、旧版本、外部成功、本地超时等具体交错。
6. **收敛交付结论**：把已闭合、仍有缺口、待工程验证和未覆盖分开表达。

## 目录

```text
.
├── SKILL.md
├── references/
│   ├── composition-and-review.md
│   ├── feature-contract.md
│   └── mechanism-decisions.md
├── assets/
│   └── logo.svg
├── LICENSE
├── .gitattributes
└── README.md
```

- `SKILL.md`：触发条件、架构设计流程、功能覆盖、技术决策和完成门槛。
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
