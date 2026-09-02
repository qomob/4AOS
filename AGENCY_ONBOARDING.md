# 4Aos Agency 落地手册（AGENCY_ONBOARDING）

> **目标读者**：4A / 独立 Agency 的 CEO、Managing Director、Account Director、Strategy Director、ECD
> **核心问题**：4Aos 不是替代 Agency 的人，而是把人从重复劳动释放到高价值环节。本文定义**采用门槛、人机协作 SOP 与价值定价**，让 Agency 在保留核心资产的同时放大产能。
> **版本**：v4.4.6（2026-09-02）· 本手册随 v4.4.5–v4.4.6 的评估诚信、交互模型与品牌记忆变更全面修订

---

## 零、采用门槛（先读这段，v4.4.6 新增）

以下三条**缺一不签采用决议**：

| # | 门槛 | 内容 |
|---|------|------|
| 1 | **质量证据** | 4Aos 当前质量证据为 `NEEDS_EVIDENCE`（结构全绿 ≠ 质量已验证）。**先跑 [一周三臂盲测试点](./evals/e2e/pilot.md)，结果存档后再决定**。别替工具作保，让数据作保——试点结果 fail 时，正确动作是不采用，而不是调阈值 |
| 2 | **商业授权** | v4.4.4 起转为商业授权模式：对外交付的项目与**商业比稿**须事先获得 Qomob.AI & XSkill.dev 书面授权（见 [README 授权条款](./README.md)） |
| 3 | **数据合规** | 客户数据脱敏后输入；敏感客户本地化部署；签 NDA + DPA。learnings 三条回流通道（lessons / outcome 台账 / 品牌记忆）全部 alias 键控、无预算明细、拒绝真实名称字段（脚本强制） |

---

## 一、人机协作三定律（Three Laws of Agency-AI Collaboration）

| 原则 | 说明 | 实操含义 |
|------|------|---------|
| **1. 人类拥有最终裁决权** | AI 输出是草稿，不是定稿。任何对外交付物必须经人类签字 | 强制中断点（终稿交付/预算定音等）是真门控，不是装饰 |
| **2. AI 做加法，不做减法** | AI 不允许删除 Agency 已有的策略判断、创意方向、客户关系资产 | 4Aos 输出 = 候选材料；Agency 在此上叠加洞察 / 关系 / 经验 |
| **3. 责任不可外包** | 对客户的承诺、合规风险、品牌安全最终由 Agency 承担 | AI 给的是建议，决策权和责任都在人 |

---

## 二、角色 × 4Aos 协作矩阵

| Agency 角色 | 与 4Aos 的协作方式 | 高价值环节（不可外包） | 可委托 4Aos 的环节 |
|------------|------------------|------------------|------------------|
| **Account Director / AE** | 用 AE Agent 生成 Brief 初稿；**老客户自动加载品牌记忆，免重复追问** | 客户关系经营、内部政治协调、危机预判、商业谈判 | Brief 结构化、追问清单、会议纪要、复盘文档 |
| **Strategy Director / Planner** | 用 Planner + Research Agent 做模型选择 / 案例扫描，人工做"洞察真伪"判断和客户心智建模 | 真正的 consumer insight、客户业务理解、行业人脉情报、策略叙事 | 模型库匹配、Tournament 评分、竞品数据扫描、策略文档结构化 |
| **ECD / Creative Director** | 用 Creative + AIGC Agent 做方向广撒网和 Craft 工艺指导，人工做"美感判断"和"戛纳级"创意把关 | Big Idea 灵感、视觉品味、文化敏感度、艺术家 / 导演 / 摄影师资源 | 创意方向广撒网、KV 构图建议、Copy Tone 草稿、AIGC Prompt、Benchmark 案例 |
| **Media Planner** | 用 Media + GEO Agent 做渠道组合 / 漏斗模拟 / 预算分配，人工做媒体主关系和议价 | 媒体主关系、议价、库存优先级、私域流量资源 | 渠道配比、漏斗情景、Programmatic 策略、CTV / DOOH 排期 |
| **Producer** | 用 Producer Agent 做排期 / 风险清单；**投放前签 Measurement Contract，复盘后回写效果台账与品牌记忆** | 供应商关系、现场调度、突发事件应对 | 时间线、风险矩阵、跨 Agent 校验、复盘草稿生成 |
| **Compliance / Legal** | 用 Compliance Agent 做四维扫描和 GARM 检查，人工做最终法律意见 | 法律意见签字、监管沟通、危机应对 | 法规扫描、Brand Safety 分级、平台规则检查、文档化 |
| **Proposal / Pitch Director** | 用 Proposal + Competitive Differentiation 做结构化和 Pitch Script，人工做现场演绎和即兴应答 | 现场演绎、即兴应答、与评审团的化学反应 | 8+1 章节结构、Pitch Script 逐字稿、Q&A Battle Card、Business Case |
| **Data / MMM Analyst** | 用 MMM Agent 做估算框架和预算优化，人工做业务解释和决策建议 | 业务解释、模型假设的合理性判断、CMO 汇报 | Adstock/Hill 框架、预算优化、敏感性分析（**全程估算示意值，非真实建模**） |

---

## 三、交互模型（v4.4.5 起：风险触发中断）

| 档位 | 中断点 | 适用 |
|------|--------|------|
| **半自动（默认）** | 仅 5 类强制中断点：策略定音 / 预算定音 / 风险信号 / 假设超限 / 终稿交付。deep 全程 3-5 次 | 日常 Campaign / 老客户 |
| 全手动（opt-in） | 每个 Agent 后逐步确认 | 比稿 / 新客户 / 预算 ≥ 100 万——说「每步都停」 |
| 全自动 | 仅终稿交付停 | 标准化复投；危机 sprint 默认 |

> 设计依据：确认疲劳会让高频确认退化为橡皮图章——系统只在「期望遗憾 > 中断成本」的时刻打扰你。

---

## 四、四种典型工作流（Agency 内部 SOP）

### SOP-A：日常 Campaign（半自动）

```
Day 0：客户 Brief 进来
├─ AE 用 4Aos AE Agent 起草结构化 Brief（老客户品牌记忆自动注入，15 min）
├─ AE 与 Planner 一起做 Stakeholder Mapping（30 min，人工）
└─ AE 提交 Brief 给客户确认（人工把关 + 关系沟通）

Day 1：策略阶段
├─ Planner 用 4Aos Research + Planner Agent 跑 v1 策略（1-2 hr）
├─ 【CP-1 策略定音】Strategy Director 人工审核冠军策略，重点 challenge "洞察真伪"（人工）
├─ Verifier #1 自动跑一致性验证（10 min）
└─ Planner 修订后输出 v2 策略

Day 2-3：创意阶段
├─ ECD 召开 Kickoff，分享 v2 策略（人工）
├─ Creative Agent 广撒网 5 个方向（1 hr）→ ECD + CD 人工评选 Top 2（2 hr）
├─ 创意回炉循环（≥2 轮自动触发 CP-3 风险中断）
└─ AIGC Agent 生成 Prompt + 素材草稿

Day 4-5：投放 + 执行
├─ Media Agent 跑渠道组合 →【CP-2 预算定音】Media Director 人工确认分配，叠加媒体主关系（人工）
├─ Producer Agent 输出排期 + 风险矩阵 → Producer 人工核对供应商
└─ 投放前：AE + Producer 与客户签 Measurement Contract（primary_metric / window / threshold）

Day 6-7：合规 + 提案
├─ Compliance Agent 自动四维扫描（非 pass 自动触发 CP-3 中断）
├─ Legal 人工签字确认（人工，必须）
├─ Proposal Agent 整合 8+1 章节 + Business Case + Pitch Script
├─【CP-5 终稿交付】Proposal Director 人工润色 + 演练（4 hr，人工）
└─ 客户汇报
```

**效率预期**：传统 2-3 周 → 7 天。⚠️ 此为设计目标，非测量结果——以上线首月用试点协议实测为准。

### SOP-B：比稿 / Pitch（全手动 opt-in + 试点先行）

```
T-21：收到 RFP
├─ AE 用 4Aos 起草 Brief；CEO / MD 召开 Pitch Team Kickoff（人工）
└─ 说「每步都停」切全手动档：每个 Agent 产出逐步确认

T-21 ~ T-14：策略 + 创意
├─ 与 SOP-A Day 1-3 相同，但启用 Cross-Model Verification、创意回炉强制 ≥ 2 轮
├─ Competitive Differentiation 三层分析（含竞对 Agency 打法）
└─ ECD / Strategy Director 深度参与每个中断点（人工，必须）

T-14 ~ T-7：提案打磨
├─ Proposal Agent 输出完整方案 + Pitch Script + Q&A Battle Card
├─ Pitch Director 主持 3 轮内部 Mock Pitch（人工，必须）→ feedback-loop 迭代
└─ ECD 现场演绎彩排（人工）

T-7 ~ T-0：现场交付
├─ PPTX 导出 → 设计师人工美化封面 / 关键页（人工）
└─ Pitch Team 现场演绎 + Q&A（AI 仅做备答库参考）
```

**效率预期**：传统 4-6 周 → 3 周。⚠️ 同上，属设计目标。**收敛警告**：比稿胜负手是对客户业务的独特洞察——4Aos 产出的骨架必须叠加你们独有的事实与洞察，直接交原始输出会被采购识别为模板。

### SOP-C：紧急响应（全自动 + Crisis Management）

```
T+0：危机触发 → crisis-management.yaml 启动 → Traffic 判定 P0-P3 → CEO/CMO/ECD 紧急召集
T+0 ~ T+4h：Research 舆情扫描 → Planner 出 3 个应对策略 → Compliance 即时审查 → CEO/Legal 人工签字
T+4h ~ T+24h：Content 出声明/文案（ECD 把关调性）→ Media 紧急投放方案 → 发布 + 监测 + feedback-loop（≤3 轮）
```

### SOP-D：复盘 + 三通道回流（v4.4.6 数据飞轮）

```
Campaign 结束 T+30/60/90：post-campaign.yaml
├─ 【定性通道】Producer 生成 Lessons Learned → learnings/{industry}/（下次同行业自动检索）
├─ 【定量通道】outcome-draft 步骤按 Measurement Contract 生成结果草稿
│    → 人工两件事：--provenance 声明实测/估算 + 核对脱敏
│    → python3 scripts/outcome_ingest.py record --from-draft draft.json --provenance measured --confirm
├─ 【品牌通道】brand-memory-update 步骤生成品牌记忆增量（新红线 / campaign 摘要）
│    → python3 scripts/brand_memory.py upsert --from-draft draft.json --confirm
└─ 解冻就绪度检查：python3 scripts/outcome_ingest.py summary（只读，永不自动翻转学习开关）
```

> 价值逻辑：lessons 让下次"长记性"，outcome 台账是唯一能解冻策略权重的水源，品牌记忆让同品牌第二次合作免追问——**这三样是竞品抄不走的积累，24 个 agent 文件本身一个下午就能被复制。**

---

## 五、一周试点（采用的第一步，v4.4.6）

完整 SOP 见 [evals/e2e/pilot.md](./evals/e2e/pilot.md)。三臂设计：

| 臂 | 是什么 | 回答什么 |
|----|--------|---------|
| A | 4Aos 链路（同模型） | 质量 vs 强基线 |
| B | 资深策略 + 强单 Prompt（同模型） | 反 strawman 基线 |
| C | 你们自己的传统流程 | 质量 vs 人 + 效率 vs 人 |

判定规则预注册：A 质量胜率 ≥60% 才算赢；质量 fail 时效率数据不构成辩护。**结果区存档后，才进入定价谈判与对外宣称。**

---

## 六、价值定价模型（Value-Based Pricing）

> **核心原则**：4Aos 放大 Agency 产能，如果继续按人天收费等于自我贬值。Agency 应迁移到**价值定价**——但以下区间的底层假设（提效幅度、胜率提升）须经试点实测后方可写进对客承诺。

### 6.1 三层定价架构

| 层级 | 计价单位 | 适用场景 | 参考区间 |
|------|---------|---------|---------|
| **L1 — Retainer 月费** | 品牌 / 月 | 长期品牌代运营 | ¥15-80 万 / 月 / 品牌 |
| **L2 — Project Fee** | 项目 | 一次性 Campaign / Pitch | Campaign 预算的 8-20% |
| **L3 — Performance Bonus** | KPI 达成 | 效果类 Campaign | 基础 Fee + 超额分成 10-30% |

### 6.2 4Aos 加价因子

| 模块 | 加价幅度 | 理由 |
|------|---------|------|
| Cross-Model Verification | +15% Pitch Fee | 双盲双模型验证 |
| Competitive Differentiation | +10% Pitch Fee | 差异化分析 + Q&A Battle Card |
| Business Case / ROI 论证 | +5-10% Campaign Fee | CFO 视角，提高预算通过率 |
| MMM 建模 + 预算优化 | +20% Performance Bonus | 量化贡献，超额分成（输出为估算示意） |
| 13 大行业垂直模板 | +5-15% Campaign Fee | 行业专家身份 |
| Crisis Management 24h SLA | +50-100% Project Fee | 紧急响应 + 风险溢价 |

### 6.3 价格锚定话术（给客户）

> ⚠️ 诚实条款：下表话术中的效果主张（如"胜率 30%→60%+"）目前是设计假设。试点实测数据出来前，只可用"我们用结构化对抗验证 + 人工终审"这类**可证实的过程描述**，不可用未经测量的结果数字。

| 客户质疑 | 应对话术 |
|---------|---------|
| "AI 做的为什么要收 Agency 费？" | "你付的不是 AI 的钱，是我们用 AI 加 15 年行业经验做的判断。AI 是工具，决策权和责任在我们。" |
| "为什么比传统报价贵 20%？" | "因为每个策略经过 11 个角色的对抗评审和人工终审，方案的结构完整度与合规把关是可审计的。"（胜率数字待试点数据） |
| "为什么 Performance Bonus 这么高？" | "因为 Measurement Contract 事先定义了成功口径，达成与否用数据说话。" |

---

## 七、AI 产出"去 AI 化"清单

> **风险**：LLM 产出有可辨识的"AI 感"，客户可能质疑 Agency 专业价值。交付前必须做去 AI 化处理。

| 维度 | AI 痕迹 | 人工修正 |
|------|--------|---------|
| **语言** | "在...的背景下"、"赋能"、"打造"、"全链路" 等套路化表达 | 改写为口语化、行业黑话、客户专属用语 |
| **结构** | 每段都是"背景→挑战→方案→预期" | 重排叙事，加入非常规结构 |
| **数据** | 引用泛化的"行业数据显示" | 补充具体数据源（艾瑞 / 尼尔森 / 监测平台）|
| **洞察** | 看似深刻实则是常识 | ECD / Strategy Director 注入"只有我们知道"的独家洞察 |
| **创意** | 概念清晰但缺乏张力 | ECD 加入"戏剧性反转 / 文化挑衅 / 视觉破坏" |
| **PPT** | 模板化排版 | 设计师手工美化封面 / 关键页 / Moodboard |

---

## 八、风险与应对

| 风险 | 应对 |
|------|------|
| **Agency 内部抵制 AI** | 先在非核心品牌跑试点；建立"AI Operator"新岗位；老员工转岗为"AI Trainer" |
| **客户质疑专业价值** | 公开"AI-Augmented Agency"理念；展示对抗验证 + 人工终审的可审计过程 |
| **数据安全** | 脱敏后输入；敏感客户本地化部署；NDA + DPA；learnings 档案 alias 键控（脚本强制） |
| **AI 输出错漏** | 所有对外交付物 ≥ 2 道人工审核；Compliance + Legal 签字；Compliance Agent 的 pass ≠ 法律意见 |
| **比稿对手也在用 4Aos** | 结构会被普及稀释；差异化靠品牌记忆积累 + outcome 数据 + 客户亲密 + ECD 把关——用得越久护城河越深 |
| **多品牌方案趋同** | 同库同模板的必然结果：每个品牌建立独立 brand 档案，注入独有红线与历史教训 |
| **学习层学到噪声** | 已内置防护：success 无契约不入账、estimated 不参与解冻采样、权重封顶 ±15%（见测量契约） |

---

## 九、上线 90 天路径

| 阶段 | 目标 | 行动 |
|------|------|------|
| **Day 1-30：试点** | 用数据回答"值不值" | 按 [pilot.md](./evals/e2e/pilot.md) 跑三臂盲测（2-3 个真实 Brief）；结果存档；解决商业授权与数据合规 |
| **Day 31-60：扩展** | 3 个品牌 / 3 个团队 | 内部培训；建立 AI Operator 岗位；为每个客户建立品牌档案并开始 outcome 回流 |
| **Day 61-90：全面** | 全 Agency | 按实测数据调整定价模型；对外沟通"AI-Augmented"；learnings 三通道成为日常 |

---

## 十、参考

- [SKILL.md](./SKILL.md) — 完整规则与流程定义
- [QUICKSTART.md](./QUICKSTART.md) — 2 分钟快速入门
- [evals/e2e/pilot.md](./evals/e2e/pilot.md) — 三臂盲测试点手册（采用门槛）
- [evals/backtest.md](./evals/backtest.md) — 回测协议
- [references/measurement-contract.md](./references/measurement-contract.md) — 测量契约与结果分类
- [references/learnings-protocol.md](./references/learnings-protocol.md) — 数据飞轮三通道（含品牌记忆）
- [CHANGELOG.md](./CHANGELOG.md) — 版本历史

*最后更新: 2026-09-02 | 维护者: 4Aos Team*
