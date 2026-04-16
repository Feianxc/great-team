# Great Team

**Great Team** 是一个开工前的项目判断 Skill。  
它服务的不是“不会做东西的人”，而是**已经能快速做出来，但不确定该不该做、该先做什么、第一版该砍什么**的人。

## 它解决的不是执行问题，而是判断问题

现在做原型、写代码、生成页面、搭工作流已经很便宜。  
真正贵的是这些判断：

- 这个项目到底在做什么
- 第一版真正的切口是什么
- 哪些内容现在不该做
- 最大的风险在哪里
- 下一步最该验证什么

大多数 AI 工具会继续给你建议、继续帮你展开。  
**Great Team** 的作用正好相反：它帮你在开工前把方向压缩、把范围收紧、把错误版本提前砍掉。

## 适合谁

适合这些人：

- AI-native solo builder
- 小团队创始人
- 产品型工程师
- founder-designer
- 创意技术人

他们通常有同一个痛点：

> 不是做不出来，而是太容易做出来，反而更容易做错版本。

## 它会产出什么

输入一个想法、PRD、功能草案、游戏概念或策略草案，`Great Team` 会输出一份结构化 **decision memo**，包括：

1. 项目本质
2. 关键张力
3. 推荐视角组合
4. 视角到职能的映射
5. 最强反对意见
6. 决策建议
7. 下一步最小可证伪实验
8. 边界与未验证项

它的目标不是“说得更聪明”，而是：

> **改变你接下来要做什么。**

## 它不是什么

`Great Team` 不是：

- 名人模仿器
- 多 agent 开会表演
- 通用 agent 平台
- 虚拟公司模拟器
- 直接替你把项目做完的执行工具

它只做一件事：

> **在你开始做之前，帮你做更好的判断。**

## 核心方法

`Great Team` 的工作方式很简单：

1. 找出项目最关键的矛盾
2. 选择最合适的“伟大视角”
3. 把这些视角映射到真正需要判断的职能区
4. 输出一份硬一点的 decision memo

这里的“伟大视角”不是角色扮演，而是判断框架，比如：

- Philosopher
- Writer
- Scientist
- Editor-Critic
- Social Psychologist
- Poet
- Artist

## 这个仓库里有什么

```text
.
├── .codex/
│   ├── agents/                 # 可选的本地 reviewer / composer 配置
│   └── config.toml             # 已配置为相对路径，可直接引用 great-team
├── great-team/
│   ├── SKILL.md                # Skill 主体
│   ├── agents/openai.yaml      # UI 元数据
│   ├── assets/                 # 决策备忘录模板
│   ├── references/             # 运行协议、lens schema、验证方法等
│   ├── evals/                  # mini eval 批次结果
│   └── product/                # Great Team 产品 PRD
└── README.md
```

## 当前验证状态

当前仓库已经完成一轮内部 mini eval，对 5 个不同 brief 进行 `great-team` 与普通 baseline critique 的对比。  
结果显示，`great-team` 的稳定价值不是“更会说”，而是：

- 更快抓到真正的张力
- 更敢做 hard cut
- 更能缩小 next experiment
- 更容易阻止浪费时间去做错误版本

## 怎么用

如果你在 Codex 中直接打开这个仓库，`.codex/config.toml` 已经把 `great-team` 指向相对路径。

你可以直接这样用：

```text
Use $great-team to review this idea before we build: what is the real wedge, what should we cut, and what should we test first?
```

或者直接给中文需求，例如：

- 帮我用 great-team 审一下这个产品方向
- 这个 PRD 第一版到底该砍什么
- 这个想法的真正 wedge 是什么
- 这个项目现在最应该先验证什么

## 开源目标

这个仓库当前的目标不是做一个“炫”的 agent 系统。  
它的目标很具体：

> 做出一个真正能在开工前改变建造决策的 judgment skill。

## License

MIT
