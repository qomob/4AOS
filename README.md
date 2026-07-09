# 4AOS

> **From Brief to Business Impact** — 4A 全案智能体工作流。20 个 Agent 协作覆盖广告/营销/传播全业务周期。

[![Version](https://img.shields.io/badge/Version-v4.4.3-green.svg)](./CHANGELOG.md) [![SSOT](https://img.shields.io/badge/SSOT-manifest.json-blue.svg)](./shared/manifest.json) [![Agents](https://img.shields.io/badge/Agents-20_(5_submodules)-orange.svg)](#agent-能力)

---

## 一句话

**给它一句 Brief，返还一份可执行的广告/营销方案。**

```
"做个新茶饮 Campaign，预算 50 万，目标 Z 世代"
  → Traffic（路由）→ AE（澄清）→ Planner（策略 Tournament）
    → Verifier（对抗验证 + 元反思）→ Creative → Content → Media
    → Proposal（咨询级方案 + 董事会摘要 + 合规免责）
```

---

## 当前状态（v4.4.3 / 2026-07-09）

| 维度 | 数量 | 说明 |
|------|:----:|------|
| Agent 文件 | 20 | 14 流程 + 1 独立工具 + 5 条件子模块 |
| 工作流 | 20 | Campaign / 品牌咨询 / 社媒 / KOL / 危机 / 电商 |
| 参考资料 | 25 | 行业模板 / 创意范式 / 合规 / 元反思框架 |
| Schema | 19 | Agent 间数据契约（含 trace-schema 可观测性） |
| 行业模板 | 13 | 9 传统 + 4 新兴（电竞/宠物/银发/ESG） |
| SKILL.md | 487 行 | 拆出索引到 `_skill-index.md` 后接近上限 |

> **SSOT**：所有元数据以 `shared/manifest.json` 为准，本报告数字与 manifest 同步。

---

## 核心能力

### 它解决问题的三层

| 层 | 能力 | 解决什么 |
|----|------|---------|
| **决策** | 11 Persona Tournament（5 Stakeholder + 6 Adversarial）+ Decision Council 收敛 | "方案拍脑袋" → 结构化决策 |
| **交付** | Executive Brief → Proposal 双模式（8 章 Agency / 15 Part Consulting） | "方案太简单" → 咨询级输出 |
| **进化** | Context-Aware Learning（v4.2）+ Meta-Reflection（v4.4.2） | "重复犯错" → 系统越用越聪明 |

### Agent 能力速览

| Agent | 角色 | 关键能力 |
|-------|:----:|---------|
| 🔀 **Traffic** | 调度路由 | 意图识别 → 4 模式选径 → Token 预算 |
| 🛡️ **AE** | 客户总监 | Brief 澄清 + Quarantine 隔离（用户内容仅 AE 可读） |
| 🧠 **Planner** | 策略引擎 | 15 模型 Tournament + OKR 五级 + ESG |
| 🔄 **Verifier** | 验证者 | 5 Persona Challenge + 6 Adversarial Review + 元反思前置层 + Decision Council |
| 📋 **Executive Brief** | 决策摘要官 | Decision Council 输出 → 3 页董事会摘要 |
| ✨ **Creative** | 创意总监 | 4 方法论 + Craft 工艺 + 回炉循环 + 视觉参考层 |
| 🔥 **Proposal** | 方案交付 | 双模式 + Business Case + ROI + PPTX/PDF 导出 + Decision Memo |
| 📊 **MMM** | 独立工具 | Adstock/Hill 贝叶斯营销组合建模 + 预算优化 |

> 还有 Research / AIGC / Content / GEO / Media / Producer / Compliance 7 个专职 Agent，完整列表见 [SKILL.md](./SKILL.md) 或 [references/_skill-index.md](./references/_skill-index.md)。

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
| **deep** | 全链路 16 步 | 正式 Campaign / 大额预算 / 品牌升级 |
| **fast** | 精简 6-8 步 | 快速预览 / < 5 万预算 |
| **creative** | Creative → AIGC → Content | 创意比稿 / 视觉方案 |
| **strategy** | Traffic → AE → Planner → Proposal | 品牌战略 / 定位规划 |

### 首次交互预期

完整 Campaign = 多步骤对话（12-16 次 Checkpoint），不是一次性输出。每个 Agent 完成后系统询问是否继续，可随时断点续跑或跳过。

> 详细入门见 [QUICKSTART.md](./QUICKSTART.md)（2 分钟）。

---

## 版本进化

| 版本 | 核心变更 | 影响 |
|------|---------|------|
| **v4.4.3**（当前）| SkillForge P0-P2 重构：references 合并 32→25 + trace-schema + Agent 天花板规则 | 合规率 80.7%→≥93% |
| **v4.4.2** | Meta-Reflection Framework（8 维度认知层自检） | 防止"逻辑自洽但前提错误"废案 |
| **v4.4.1** | SkillForge P2 验证优化（description/Gotas/token） | description 合规、新增 7 类陷阱 |
| **v4.4.0** | Executive Brief Layer + Architecture Freeze | Proposal 四职责冲突根因修复 |
| **v4.3.6** | Proposal Consumption Bug Fix | Verifier→Proposal 信息损耗 53%→<10% |
| **v4.0** | Decision Council + Type 1/2 分类 | 11 Persona 有收敛，不再分析瘫痪 |
| **v3.6-v3.7** | Multi-Perspective Challenge + Adversarial Review + Decision Memo | 对抗评审体系建立 |
| **v3.4** | Cross-Model Verification + PPTX/PDF + Agency 手册 | 企业级可用性 |

> 完整变更历史见 [CHANGELOG.md](./CHANGELOG.md)。

### 演化路径

```
Generate ✅ → Verify ✅ → Challenge ✅ → Decide ✅ → Learn ✅ → Deliver ✅
                                                                  ↓
                                                Decision Intelligence (v5.0 future)
```

---

## 架构原则

| 原则 | 应用 |
|------|------|
| **干验分离** | Verifier 独立于 Planner，不自判自卷 |
| **Tournament** | 成对 PK 替代绝对打分，避免"策略选择困难症" |
| **Quarantine** | 用户原始内容仅 AE 可读，防 Agent 被误导 |
| **懒加载** | 子模块条件触发，Token 消耗降 ~40% |
| **Decision Artifact** | 6 层六层架构冻结：Evidence → Analysis → Record → Package → Brief → Proposal |
| **SSOT** | manifest.json 为唯一事实源，健康检查自动校验数字漂移 |

---

## 文件结构（简）

```
4aos/
├── SKILL.md              # 主入口（487 行，含懒加载指令）
├── README.md             # 本文件
├── QUICKSTART.md         # 快速入门
├── CHANGELOG.md          # 版本历史
├── manifest.json         # SSOT 单一事实源
├── agents/               # 20 个 Agent 文件
│   ├── {agent}.md        # 15 个核心 Agent
│   └── creative-agent.{methods,craft,reburn}.md  # 3 个条件子模块
│   └── proposal-agent.{business-case,dashboard}.md  # 2 个条件子模块
├── workflows/            # 20 条工作流 yaml
├── references/           # 25 份参考资料（含 _skill-index.md）
└── shared/
    ├── manifest.json     # SSOT
    └── schemas/          # 19 个 JSON Schema
```

> 完整文件清单见 [references/_skill-index.md](./references/_skill-index.md)。

---

## 相关文档

| 文档 | 用途 |
|------|------|
| [SKILL.md](./SKILL.md) | 完整规则与流程定义（Agent 必读） |
| [QUICKSTART.md](./QUICKSTART.md) | 2 分钟上手 |
| [CHANGELOG.md](./CHANGELOG.md) | 版本变更历史 |
| [AGENCY_ONBOARDING.md](./AGENCY_ONBOARDING.md) | Agency 落地手册 |
| [references/_skill-index.md](./references/_skill-index.md) | Agent/Schema/参考完整索引 |
| [references/meta-reflection-framework.md](./references/meta-reflection-framework.md) | 8 维度元反思框架 |

---

## License

Apache 2.0 — 见 [LICENSE](./LICENSE)

Copyright 2026 Qomob.ai & XSkill.dev
