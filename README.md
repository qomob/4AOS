# 4AOS

> **From Brief to Business Impact** — 4A 全案智能体工作流。24 个 Agent 文件协作覆盖广告/营销/传播全业务周期。
>
> **先把话说准**：它交付的是 *Impact Plan*（可执行方案），不是 Impact 本身——效果依赖人工执行与数据回流。

[![Version](https://img.shields.io/badge/Version-v4.4.6-green.svg)](./CHANGELOG.md) [![SSOT](https://img.shields.io/badge/SSOT-manifest.json-blue.svg)](./shared/manifest.json) [![Evidence](https://img.shields.io/badge/质量证据-NEEDS_EVIDENCE-yellow.svg)](#诚实声明) [![Agents](https://img.shields.io/badge/Agents-24_(9_submodules)-orange.svg)](#agent-能力速览)

```
"做个新茶饮 Campaign，预算 50 万，目标 Z 世代"
  → Traffic（路由）→ AE（澄清）→ Planner（策略 Tournament）
    → Verifier（对抗验证 + 元反思）→ Creative → Content → Media
    → Proposal（8 章方案 + 董事会摘要 + 合规免责）
```

---

## 🎬 演示视频

<video src="4aos_promo_video.mp4" controls muted playsinline width="100%"></video>

> 若浏览器未内嵌播放，[点此直接观看](4aos_promo_video.mp4)。

---

## 诚实声明（先读这段）

本项目的价值分层清晰，证据等级不同。我们拒绝用"结构全绿"冒充"质量已验证"。

| 价值层 | 状态 | 证据 |
|------|------|------|
| **结构价值**：流程完备、合规拦截、决策留痕 | ✅ 已证明 | 20 项健康检查、20 个 Schema 契约、四维合规扫描全通过 |
| **效率价值**：比稿/提案前端提效 | 🟡 可信但未测量 | "2-3 周→7 天"是设计目标（见 [AGENCY_ONBOARDING.md](./AGENCY_ONBOARDING.md)），非测量结果 |
| **质量溢价**：比一个强单 Prompt 好多少 | ❌ **未证明** | 当前 `NEEDS_EVIDENCE`：8/24 场景质量预期零证据；E2E 盲测协议已建（[evals/e2e/protocol.md](./evals/e2e/protocol.md)）但**从未运行** |
| **复利价值**：越用越懂你的数据护城河 | ⬜ 尚未开始 | 效果台账 0 条记录，回流手动（[measurement-contract.md](./references/measurement-contract.md)） |

实时证据状态：`evals/test_report_latest.json` 的 `overall_status` 字段（当前 `NEEDS_EVIDENCE`）。
在 E2E 盲测跑过之前，对本工具质量溢价的任何断言都是假设——包括我们自己做的。

---

## 适合谁 / 不适合谁

| 你是谁 | 结论 | 原因 |
|--------|------|------|
| **无代理的中长尾品牌**（预算 5-50 万） | ✅ **最强场景** | 备选项不是"更好的代理"而是"没有"。策略分解 + 媒介组合 + 合规扫描是你唯一可得的全案能力 |
| **代理商的比稿/提案前端** | ✅ 真实价值 | 压缩结构化初稿的 senior 工时；Junior 杠杆 + 方法论强制（需先解决商业授权与数据合规，见文末） |
| **高频营销事故品类**（医美/食品/金融） | ✅ 合规第一道网 | 广告法/平台规则扫描拦截低级事故。**但它是 LLM 读参考文件，不是法规数据库：`pass` ≠ 法律意见**，敏感品类必须过真人法务 |
| **大型企业**（有代理体系 + CDP/真 MMM） | ⚠️ 价值薄 | 无 first-party 数据接入，产出的方案不如内部两周做得贴身。可用作反审乙方方案的"同一把尺子" |
| **期待创意质量跃升** | ❌ 别抱此预期 | 创意天花板 = 模型天花板。Tournament 选出的是"15 框架内最优"，产出**结构化的合格**，不是**独特的卓越** |
| **期待增长系统** | ❌ 不成立 | 媒介/ROI 数字是行业基准估算（内部讨论可用，客户面前须重做）；买到的方案生产工具，不是增长引擎 |

**给代理商的一个额外提醒**：多家代理用同一套模型库与模板会导致方案趋同，比稿胜负手（对客户业务的独特洞察）恰是本工具不承载的。用它做骨架、注入你的真洞察，甲方无感；直接交原始输出，采购闻得出模板味。

---

## 当前状态（v4.4.6 / 2026-09-02）

| 维度 | 数量 | 说明 |
|------|:----:|------|
| Agent 文件 | 24 | 14 流程 + 1 独立工具 + 9 条件子模块 |
| 工作流 | 20 | Campaign / 品牌咨询 / 社媒 / KOL / 危机 / 电商 |
| 参考资料 | 28 | 顶层注册 28 份 + 3 份子模块/附件（行业模板 / 创意范式 / 合规 / 元反思框架 / 测量契约） |
| Schema | 20 | Agent 间数据契约（含 trace-schema 可观测性） |
| 行业模板 | 13 | 9 传统 + 4 新兴（电竞/宠物/银发/ESG） |
| SKILL.md | 308 行 | 路由 manifest，完整索引在 `_skill-index.md` |

> **SSOT**：所有元数据以 `shared/manifest.json` 为准，本文件数字与 manifest 同步（v4.4.6 已校准）。

---

## 怎么用

### 零配置启动（推荐）

直接说需求，系统自动路由：

```
"帮我们做个智能宠物喂食器 Campaign，预算 100 万，抖音+小红书"
```

→ 自动识别为 `campaign` 路径 × `deep` 模式（budget ≥ 30 万）。

### 四种模式

| 模式 | 链路 | 适用 |
|------|------|------|
| **deep** | 全链路 12 步（GEO/Media 并行，Phase A/B/Council 为 4.x 子步） | 正式 Campaign / 大额预算 / 品牌升级 |
| **fast** | 精简 6-8 步 | 快速预览 / < 5 万预算 |
| **creative** | Creative → AIGC → Content | 创意比稿 / 视觉方案 |
| **strategy** | Traffic → AE → Planner → Proposal | 品牌战略 / 定位规划 |

### 首次交互预期

完整 Campaign = 多步骤自动推进的对话（12 步主链路 + 4.x 子步）。**默认半自动**：只在 5 类强制中断点暂停（策略定音 / 预算定音 / 风险信号 / 假设超限 / 终稿交付），deep 全程约 3-5 次确认；其余步骤以进度行播报。说「每步都停」恢复逐步确认，说「接下来全自动」一路跑到终稿。可随时断点续跑或跳过。

> 详细入门见 [QUICKSTART.md](./QUICKSTART.md)（2 分钟）。

---

## 如何验证它的价值（别信我们，自己测）

两套协议都已就绪，成本低于任何一篇评估文章：

1. **代理商——三臂盲测**：拿 2 个真实比稿 Brief，对比 ①4Aos 链路 ②资深策略 + 单 Prompt ③传统 junior 流程，让未参与者盲评。协议见 [evals/e2e/protocol.md](./evals/e2e/protocol.md)，工具：`scripts/e2e_eval.py`（预注册阈值，胜率 ≥60% 才算赢）。
2. **企业方——回放回测**：拿一个**已结束** Campaign 的 Brief + 真实结果，让系统重做方案，对比方案与实际效果的偏差。
3. **质量证据怎么升级**：`NEEDS_EVIDENCE → llm_e2e → outcome_backed`，路径与判据见 test runner v3.0 与测量契约。跑完盲测，本节的"未证明"字样才会被数据替换。

---

## 架构原则

| 原则 | 应用 |
|------|------|
| **干验分离** | Verifier 独立于 Planner，不自判自卷 |
| **Tournament** | 成对 PK 替代绝对打分，避免"策略选择困难症" |
| **Quarantine** | 用户原始内容仅 AE 可读，防 Agent 被误导 |
| **懒加载** | 子模块条件触发，Token 消耗降 ~40% |
| **风险触发中断** | Checkpoint 只在 5 类强制中断点暂停（策略/预算/风险/假设/终稿），deep 全程 3-5 次 |
| **决策可追溯** | 决策型 Agent 强制 decision_log；六层 Decision Artifact：Evidence → Analysis → Record → Package → Brief → Proposal |
| **证据分级** | 结构全绿 ≠ 质量已验证：quality_evidence_level = structural_only < llm_e2e < outcome_backed |
| **SSOT** | manifest.json 为唯一事实源，健康检查自动校验数字漂移 |
| **三通道回流** | Lessons（定性）/ Outcome 台账（定量）/ 品牌记忆（画像），全部脱敏 alias 键控 |

---

## Agent 能力速览

| Agent | 角色 | 关键能力 |
|-------|:----:|---------|
| 🔀 **Traffic** | 调度路由 | 意图识别 → 4 模式选径 → 巡航档位判定 → Token 预算 |
| 🛡️ **AE** | 客户总监 | Brief 澄清 + Quarantine 隔离 + **持久品牌记忆**（老客户免追问，红线直入约束） |
| 🧠 **Planner** | 策略引擎 | 15 模型 Tournament + OKR 五级 + ESG |
| 🔄 **Verifier** | 验证者 | 5 Persona Challenge + 6 Adversarial Review + 元反思前置层 + Decision Council |
| 📋 **Executive Brief** | 决策摘要官 | Decision Council 输出 → 3 页董事会摘要 |
| ✨ **Creative** | 创意总监 | 4 方法论 + Craft 工艺 + 回炉循环 + 视觉参考层 |
| 🔥 **Proposal** | 方案交付 | 双模式 + Business Case + ROI + PPTX/PDF 导出 + Decision Memo |
| 📊 **MMM** | 独立工具 | Adstock/Hill 建模框架 + 预算优化（**输出为估算示意值，非真实建模结果**） |

> 还有 Research / AIGC / Content / GEO / Media / Producer / Compliance 7 个专职 Agent，完整列表见 [SKILL.md](./SKILL.md) 或 [references/_skill-index.md](./references/_skill-index.md)。

---

## 版本进化

| 版本 | 核心变更 | 影响 |
|------|---------|------|
| **v4.4.6**（当前）| 价值验证工具链：三臂盲测试点套件 + 品牌记忆（brand memory）+ 回测协议 | 质量溢价一周可验证；同品牌第二次合作免重复追问；企业方一小时回测 |
| **v4.4.5** | 评估诚信（双账本修复 + E2E 盲测协议）+ Checkpoint 风险触发自适应中断（12→3-5 次）+ Measurement Contract 效果闭环地基 | eval 从结构检查升级为证据分级；交互只在「期望遗憾 > 中断成本」时打断；学习解冻有了 success 定义 |
| **v4.4.4** | SSOT 对齐 + MMM 估算免责 + workflow DAG 修复 | 消除版本漂移、假定量化、流程断裂三类 P0 |
| **v4.4.3** | SkillForge P0-P2 重构：references 合并 32→25 + trace-schema + Agent 天花板规则 | 结构合规率提升 |
| **v4.4.2** | Meta-Reflection Framework（8 维度认知层自检） | 防止"逻辑自洽但前提错误"废案 |
| **v4.4.0** | Executive Brief Layer + Architecture Freeze | Proposal 四职责冲突根因修复 |
| **v4.0** | Decision Council + Type 1/2 分类 | 11 Persona 有收敛，不再分析瘫痪 |
| **v3.6-v3.7** | Multi-Perspective Challenge + Adversarial Review + Decision Memo | 对抗评审体系建立 |
| **v3.4** | Cross-Model Verification + PPTX/PDF + Agency 手册 | 企业级可用性 |

> 完整变更历史见 [CHANGELOG.md](./CHANGELOG.md)。

---

## 文件结构（简）

```
4aos/
├── SKILL.md              # 主入口（308 行路由 manifest，含懒加载指令）
├── README.md             # 本文件
├── QUICKSTART.md         # 快速入门
├── CHANGELOG.md          # 版本历史
├── agents/               # 24 个 Agent 文件
│   ├── {agent}.md        # 15 个核心文件（14 流程 + 1 独立工具 MMM）
│   └── *.submodule.md    # 9 个条件子模块（planner/creative/proposal/verifier）
├── workflows/            # 20 条工作流 yaml（含 interaction_policy 交互策略）
├── references/           # 28 份顶层参考资料（含 _skill-index.md 与测量契约）
├── evals/
│   ├── e2e/              # 盲测协议 + 场景集 + adapter 模板 + 三臂试点手册（pilot.md）
│   ├── backtest.md       # 回测协议（企业方一小时验证法）
│   └── test_report_latest.json  # 诚实账本测试报告（overall_status 三态）
├── scripts/              # 健康检查 / 测试 / 盲测 / 结果台账 / 品牌记忆等工具
├── learnings/            # 三条回流通道（当前为空——诚实状态）
│   ├── _framework_performance.json  # 框架×上下文统计容器（学习冻结中）
│   ├── outcomes.jsonl    # 结果台账（首条实测记录后创建）
│   └── brands/           # 品牌记忆档案
└── shared/
    ├── manifest.json     # SSOT
    └── schemas/          # 20 个 JSON Schema
```

> 完整文件清单见 [references/_skill-index.md](./references/_skill-index.md)。

---

## 相关文档

| 文档 | 用途 |
|------|------|
| [SKILL.md](./SKILL.md) | 完整规则与流程定义（Agent 必读） |
| [QUICKSTART.md](./QUICKSTART.md) | 2 分钟上手 |
| [CHANGELOG.md](./CHANGELOG.md) | 版本变更历史 |
| [AGENCY_ONBOARDING.md](./AGENCY_ONBOARDING.md) | Agency 落地手册（人机协作 SOP 与角色矩阵） |
| [references/_skill-index.md](./references/_skill-index.md) | Agent/Schema/参考完整索引 |
| [references/measurement-contract.md](./references/measurement-contract.md) | 测量契约 + 结果分类（学习解冻前提） |
| [references/meta-reflection-framework.md](./references/meta-reflection-framework.md) | 8 维度元反思框架 |
| [evals/e2e/protocol.md](./evals/e2e/protocol.md) | E2E 盲测评估协议（vs 单 Prompt 基线） |
| [evals/e2e/pilot.md](./evals/e2e/pilot.md) | 三臂盲测试点手册（一周回答"值不值"） |
| [evals/backtest.md](./evals/backtest.md) | 回测协议（企业方一小时验证法） |

---

## 版权与授权

**作者**：Qomob.AI & XSkill.dev

**版权声明**：本作品版权归 **Qomob.AI & XSkill.dev** 所有。

### 第三方素材声明

- **Python 依赖**：`PyYAML`（MIT License，Copyright (c) Kirill Simonov），按 MIT 许可条款使用，仅作为运行时依赖调用，未复制其源码入仓。其余脚本仅使用 Python 标准库（argparse / json / re / pathlib / typing 等）。
- **视觉素材**：本 skill 为营销策略工作流引擎，不渲染视觉产物，未引用任何第三方 UI 组件库或调色板（如 Tailwind CSS / Bootstrap / Ant Design 等）。

### 授权条款

- ✅ **个人学习与评估**：可免费使用、阅读、研究本 skill
- ✅ **内部非商业项目**：在署名 Qomob.AI & XSkill.dev 的前提下可使用
- ❌ **商业用途**：必须事先获得 Qomob.AI & XSkill.dev 书面授权
  - 包括但不限于：商业产品集成、付费 SaaS 服务、对外交付的项目、培训课程收费、Agency 商业比稿
- ❌ **再分发**：不得去除或修改版权声明与作者信息

如需商业授权，请联系 **Qomob.AI & XSkill.dev**。

> 未经授权而将本 skill 用于商业用途的，视为侵权行为，Qomob.AI & XSkill.dev 保留追究法律责任的权利。

> ⚠️ **历史许可变更说明**：本 skill 此前以 Apache License 2.0 发布，自 v4.4.4 起转为商业授权模式。已删除原 LICENSE 文件。在许可变更前已合法获取 Apache 2.0 副本的使用者，其在该许可下的权利不因本次变更而溯及性失效，但后续版本更新不再以 Apache 2.0 发布。

---

## 💬 加入群聊

<div align="center">
  <img src="https://qomob.ai/xskill.jpg" width="600" alt="XSkill 微信群二维码">
  <p>扫码加入微信群，与 XClaw 社区交流</p>
</div>
