# 待办事项梳理会

## 什么是待办事项梳理会

待办事项梳理会是团队对即将进入迭代 Backlog 中故事的全体审查。通过检查 Story 是否满足进入 PI Planning 的就绪条件暴露 Story 的风险并给出下一个阶段的计划。

Story 的**INVEST** 原则是指：

- **Independent** 独立的 ：故事相互之间可以并行开发，有相对独立的价值。
- **Negotiable** 可协商的：在能够实现用户价值的前提下，实现方式的细节可协商。
- **Valuable** 有价值的：给最终用户提供的价值且可度量。
- **Estimable** 可估算的：团队在估算故事大小时能达成一致，不存在不可估算的内容。
- **Small** 小的：一个迭代内可以完成的，不超过 5 点。
- **Testable** 可测试的：具备验收规格和测试条件，且可自动化测试。

待办事项梳理会是整个迭代中总计占用时长最长的活动，迭代中 10 个工作日扣除 2 天（16个小时中，其中）

- 迭代计划会：1 - 2 小时
- 每日站立会议：0.25 小时 * 8 = 2 小时
- 迭代评审会：0.5 - 1 小时
- 迭代复盘会：1 -  2小时

上述会议最多占 7 小时，最少占用 4.5 小时。则待办事项梳理会占用团队 9 - 12 小时。**Product Owner**和**Scrum****Master** 商议时间，在不影响团队工作进展的时候进行。

建议时间点及时长：

- 每周两次，每次 4 小时。时间灵活安排。

- 在迭代回顾会议（Retrospective）之后安排一天：需要把回顾会议行动计划的某一项进行 Refine。

- 每天 1 小时，时间灵活安排。

- 一个整天（不写代码日）

## 为什么要召开待办事项梳理会

待办事项梳理会的目标是需要团队评审 Story 的风险。是否能在未来的 PI 和迭代完成。在这之前**产品负责人** 要能够基本完成 Story 的准入条件。

待办事项梳理会不是需求讨论会，如果陷入细节讨论，则是需求没有准备好的信号。

## 准备

在梳理会之前，**Product Owner** 要根据**Feature**的优先级对**Story** 的优先级进行排序。并且**Story**要符合准入条件。

**Story**进入待办事项梳理会的准入条件是：

1. 完成了**Story**格式的编写：**作为**<某个/某类用户>，**我想要**<某个功能/解决方案>，**以便**<达到某种目的>

1. 有验收条件的拆分，且验收条件拆分为多个场景。对不同场景下有规则的描述和举例。

1.**Story**验收条件 Gherkins 语法的描述，以便团队采用**BDD**的方式进行开发。**BDD**是一种拉通用户、产品、团队的测试驱动开发实践。

Scrum Master 要根据需要梳理的故事规划时间，每个故事不超过 30 分钟。然后根据团队的燃起图和累计流图选择比较合适的时间，发送会议通知。



## 议程

在待办事项梳理会中，团队需要评审需求是否满足**INVEST**原则。Scrum Master 要向团队声明梳理会的目的和**INVEST**原则。 

1.**Product Owner** 按照优先级由高到低逐个介绍每个**Story**，包括**Story** 的描述。包括**Story**相应的原型图和业务规则以及举例。以及验收条件是否已**BDD**的方式描述。

1. 团队根据**Product Owner** 的文档描述提出问题并进行评审，尽可能提出问题，以暴露风险。**Scrum Master** 要判断，如果超过时间盒，就表明需求没有准备好。时刻记得：**Backlog Refinement**占用了团队的时间，所以要准备好。

1. 如果团队对完成这个**Story**没有任何的问题/风险，并且符合**INVEST**原则，则该 Story 可以就绪作为未来**PI** 的候选**Story**。则可以开始评估下一个**Story**。

1. 如果团队提出某个风险项需要调研，则需要为其创建一个**Spike**（探索）故事，在接下来的 PI 中和安排迭代带宽进行处理。

如果超出整体的时间盒，就需要终止会议。Scrum Master 需要 15 分钟来就以下事项询问团队：

1. 会议中记录的风险是否都有责任人以及下一步的措施以及截至时间？

1. 本次的梳理会议中什么地方做的好？

1. 本次的梳理会议中有什么地方可以改进的？



## 在待办事项梳理会应用Scrum五个价值

**承诺**– 在待办事项梳理会中，能够承诺故事没有风险。

**专注**– 在待办事项梳理会中，产品负责人，**Scrum Master**和开发团队要专注于当前故事的评审完成。如果没有完成当前故事的评审，则不要开始下一个。

**开放**– 在待办事项梳理会中，针对于是否可以完成故事，**Story**的细节都要抱持开放的态度来讨论。

**尊重**– 在待办事项梳理会中，产品负责人和开发团队要尊重并信任对方的判断和解释。

**勇气**– 在待办事项梳理会中，当无法承诺时，要有勇气提出需求的不合理并且维护制度。



## 常见问题及处理方案

1. 如果团队当前阶段已经落后于进度，且加班赶工。则不能召开精梳会，原因是下个迭代团队会继续完成当前遗留的工作任务。

1. 如果有紧急的需求需要精梳，也需要通知**Scrum Master** 进行协调。

1. 如果陷入细节讨论，**Scrum Master**要注意是否需要 Meet After。
