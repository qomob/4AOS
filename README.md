# 4AOS

> **From Brief to Business Impact** — 4A 全案智能体工作流。14 个专业 Agent 协作，覆盖广告传播全业务周期。

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](./LICENSE) [![Version](https://img.shields.io/badge/Version-v3.4.0-green.svg)](./CHANGELOG.md) [![Health](https://img.shields.io/badge/Health_Check-20%2F20-brightgreen.svg)](./evals/health_report.json)

---

## 是什么

4AOS 是一套**面向 4A 广告集团与品牌主的 AI 全案工作流 Skill**，把策略、创意、媒介、合规、提案等 13 个流程 Agent 串成一条完整链路，从用户一句话 Brief 自动产出可交付的 Campaign 方案、品牌咨询报告、危机公关 SOP、电商大促方案。

- **14 个 Agent 定义** = 13 流程 Agent + 1 个 MMM 独立工具
- **20 条专项工作流** — Campaign / 品牌 / 社媒 / KOL / 危机 / 电商 / 数据分析
- **13 大行业垂直模板** — 9 传统（美妆 / 3C / 快消 / 汽车 / 食饮 / 医疗 / 金融 / 教培 / 奢侈品）+ 4 新兴（电竞 / 宠物 / 银发 / ESG）
- **18 个 JSON Schema** — Agent 间结构化数据契约，杜绝字段漂移
- **基于 Anthropic 工作流范式** — Adversarial Verification / Tournament / Generate-and-Filter

---

## 能做什么

### 七大服务线

| 服务线 | 典型场景 | 工作流示例 |
|--------|---------|-----------|
| **广告 Campaign** | 新品上市 / 品牌升级 / 比稿提案 | campaign / feedback-loop / sprint / creative-review |
| **品牌咨询** | 品牌定位 / 品牌诊断 / 品牌战略 / 品牌识别 | brand-consulting / brand-audit / brand-strategy / brand-identity |
| **社媒运营** | 代运营 / 内容日历 / 社群 / 数据分析 | social-operations / content-calendar / community-management |
| **KOL 营销** | 达人种草 / 直播带货 / 金字塔分层 | influencer-campaign |
| **危机管理** | 舆情应急 / 代言人塌房 / 产品召回 | crisis-management（P0-P3 + 24h SOP） |
| **线下/电商** | 快闪店 / 发布会 / 618 / 双11 | event-activation / ecommerce-promotion |
| **数据分析** | 营销组合建模 / 品牌追踪 / 复盘 | auto-campaign / brand-tracking / post-campaign + MMM 独立工具 |

### Agent 能力速览

| Agent | 核心能力 |
|-------|---------|
| 🔀 **Traffic** | 意图识别 + 4 模式路由 + Token 预算 + Auto-Cruise 巡航 |
| 🔍 **Research** | 联网搜索 + 竞品分析 + 社交聆听 |
| 🛡️ **AE** | Brief 澄清 + Stakeholder Mapping + Quarantine 隔离 |
| 🧠 **Planner** | 15 模型 Tournament 选优 + OKR 五级 + ESG |
| 🔄 **Verifier** | Adversarial Verification + Cross-Model L0/L1/L2 验证 |
| ✨ **Creative** | 4 大方法论 + Craft 工艺指导 + 创意回炉 + 视觉参考层 |
| 🔥 **AIGC** | 图像/视频/音频 Prompt（Midjourney / Runway / Sora） |
| ✍️ **Content** | Slogan + 视频脚本 + 社媒 + 电商详情页 |
| 🔥 **GEO** | AI 引用优化 + Voice SEO + 多模态 SEO |
| 📺 **Media** | 漏斗模拟 + Programmatic + CTV + 传统媒体 |
| 📋 **Producer** | 排期 + 资源 + 风险 + 跨 Agent 校验 |
| ⚖️ **Compliance** | 广告法 + GARM + 国际合规（FTC/ASA/GDPR/景品表示法） |
| 🔥 **Proposal** | 8+1 章节 + Pitch Script + Business Case / ROI 论证 + PPTX/PDF 导出 |
| 📊 **MMM**（独立工具） | Adstock/Hill + 贝叶斯 MMM + 预算优化 |

---

## 怎么用

### 一句话触发

Skill 会按关键词自动路由到对应工作流，无需手动指定模式或巡航级别：

```
"客户X要推一款新茶饮，预算50万，目标人群Z世代，帮我跑一个完整Campaign。"
→ campaign.yaml · deep 模式

"帮我快速看看这个美妆新品的大致方案。"
→ campaign.yaml · fast 模式（精简链路）

"代言人塌房了，需要24h内出危机公关方案！"
→ crisis-management.yaml · sprint 模式

"今年双11的电商方案，GMV目标5000万。"
→ ecommerce-promotion.yaml · deep 模式

"想用 MMM 分析上一季度各渠道的贡献度。"
→ mmm-agent.md · 独立工具入口
```

> 首次使用详见 [QUICKSTART.md](./QUICKSTART.md)（2 分钟读完）。

### 四种执行模式

| 模式 | 链路 | Token 消耗 | 适用场景 |
|------|------|----------|---------|
| **deep** | 全链路 13 Agent + 2 Verifier | ~85K（懒加载后） | 正式 Campaign / 大额预算 / 品牌升级 |
| **fast** | 跳过部分 Agent | ~64K | 小预算 / 紧急需求 / 初步方案 |
| **creative** | 强化 Creative + AIGC | ~50K | 创意比稿 / 视觉方案 |
| **strategy** | 强化 Planner | ~45K | 品牌战略 / 定位规划 |

### Auto-Cruise 三档巡航

| 档位 | 用户交互次数 | 适用 |
|------|-------------|------|
| 全手动（默认） | 8-12 次 | 比稿 / 大额预算 / 新客户 |
| 半自动 | 3-5 次 | 常规 Campaign / 老客户 |
| 全自动 | 1-2 次 | 标准化需求 / fast 模式 |

### 工具脚本

```bash
# 启动前预估 token 成本
python3 scripts/estimate_cost.py --mode deep --industry fmcg --international

# 生成 18 个 schema 的合并 bundle（-93% IO）
python3 scripts/generate_bundle.py

# 10 项健康检查
python3 scripts/health_check.py --skill-path .
```

---

## 核心亮点

| 亮点 | 解决了什么问题 |
|------|--------------|
| **Adversarial Verification** | 干验分离 + 跨模型族 L0/L1/L2 验证，消除同模型自偏袒 |
| **15 模型 Tournament 选优** | 用成对比较替代绝对打分，避免策略模型选择困难 |
| **Quarantine 隔离** | 用户原始内容仅 AE 可读，其他 Agent 通过 Brief 间接获取，防误导 |
| **零配置启动** | 用户描述需求即可，无需理解 4 模式 / 3 巡航 / 13 行业参数 |
| **懒加载指令** | 每个 Step 显式 `📍 加载文件`，Token 消耗下降 ~40% |
| **SSOT 单一事实源** | `shared/manifest.json` 统一管理元数据，健康检查脚本自动校验数字漂移 |
| **数据飞轮 MVP** | Campaign 完成后自动沉淀 Lessons Learned，下次同行业自动注入 |
| **PPTX/PDF 物理导出** | 对接 pptx / pdf skill，直接产出甲方可用的 Deck / Report |
| **比稿差异化打击** | Pitch Killer Slides + Q&A Battle Card，专为多供应商竞标场景设计 |
| **Agency 落地手册** | 人机协作三原则 + 4 种典型 SOP + 90 天上线路径，让真实 Agency 可用 |

---

## 架构

### Agent 协作链路

```
Traffic Agent (调度路由 + Token 预算 + Auto-Cruise) 🔀
  → Research Agent (市场调研 + 社交聆听) 🔍
    → AE Agent (需求澄清 + Quarantine) 🛡️
      → Planner Agent (15 模型 Tournament 选优) 🧠
        → [Verifier #1] 策略一致性验证 🔄
          → Creative Agent (创意 + Craft + 视觉参考层) ✨
            → AIGC Expert (素材生成指令) 🔥
              → Content Agent (全栈内容) ✍️
                ├→ GEO Expert (生成式引擎优化) 🔥  ─┐ 并行
                └→ Media Agent (投放 + 传统媒体)    ─┤
                  → Producer Agent (执行统筹) ←─────┘
                    → Compliance Agent (合规 + 国际) ⚖️
                      → [Verifier #2] 最终质量门控 🔄
                        → Proposal Agent (提案 + ROI) 🔥
                          → MMM Agent (营销建模，独立工具) 📊
```

### 核心设计理念

- **Adversarial Verification** — 独立验证者解决 Self-Preferential Bias
- **Tournament** — 成对比较淘汰赛替代绝对打分
- **Generate-and-Filter** — 先生成 N 个方向再筛选 Top K
- **Token Budget** — 全局预算 + Agent 配额 + 10% Emergency Reserve
- **Quarantine** — 用户内容仅 AE 可读，其他 Agent 通过 Brief 间接获取
- **Progressive Disclosure** — SKILL.md ≤500 行，资源按需加载

---

## 文件结构

```
4aos/
├── SKILL.md                 # Skill 主入口（≤500 行，含懒加载指令）
├── README.md                # 本文件
├── QUICKSTART.md            # 2 分钟快速入门
├── CHANGELOG.md             # 唯一版本历史（SSOT）
├── AGENCY_ONBOARDING.md     # Agency 落地手册（v3.4 新增）
├── TEST_REPORT.md           # 评估测试报告
├── LICENSE                  # Apache 2.0
│
├── agents/                  # 14 个 Agent 定义
│   ├── traffic-agent.md     # 调度路由
│   ├── research-agent.md    # 市场调研
│   ├── ae-agent.md          # 客户总监（Quarantine）
│   ├── planner-agent.md     # 策略引擎（Tournament）
│   ├── verifier-agent.md    # 对抗验证（#1+#2 复用）
│   ├── creative-agent.md    # 创意总监（Craft + 视觉参考）
│   ├── aigc-agent.md        # AIGC 制作
│   ├── content-agent.md     # 全栈内容
│   ├── geo-agent.md         # GEO 优化
│   ├── media-agent.md       # 媒介策划（含传统媒体）
│   ├── producer-agent.md    # 执行统筹
│   ├── compliance-agent.md  # 合规审查（含国际）
│   ├── proposal-agent.md    # 提案交付（含 Business Case）
│   └── mmm-agent.md         # 营销建模（独立工具）
│
├── workflows/               # 20 条工作流 yaml
│   └── *.yaml               # campaign / brand-* / social-* / crisis-* / ...
│
├── references/              # 29 份参考资料
│   ├── industry-*.md        # 13 大行业垂直模板（9 传统 + 4 新兴合并文件）
│   ├── planner-*.md         # 15 模型库 / OKR-ESG / 输出示例
│   ├── creative-*.md        # 跨文化 / 视觉参考层 / 输出示例
│   ├── media-*.md           # Programmatic / Privacy-CTV
│   ├── compliance-*.md      # GARM / 国际合规
│   ├── proposal-*.md        # Pitch Script / PPTX-PDF 扩展
│   ├── learnings-protocol.md # 数据飞轮协议
│   └── architecture-paradigm.md / context-protocol.md / checkpoint-format.md
│
├── shared/
│   ├── manifest.json        # 🔥 SSOT 单一事实源
│   └── schemas/             # 18 个独立 schema + bundle.json（合并产物）
│
├── scripts/                 # 工具脚本
│   ├── health_check.py      # 10 项健康检查
│   ├── generate_bundle.py   # Schema bundle 生成器
│   ├── estimate_cost.py     # Token 成本预估
│   └── test_runner.py       # 评估测试运行器
│
└── evals/                   # 16 个测试场景 + 健康报告
```

---

## 版本历史

> 完整变更详见 [CHANGELOG.md](./CHANGELOG.md)。

### v3.4.0（2026-06-08）— 评审团评估落地版

**P0 核心修复**：Cross-Model Verification（L0/L1/L2 跨模型族验证）/ PPTX·PDF 物理导出 / 比稿差异化打击 / Agency 落地手册

**P1 深化补完**：9 行业创意范式 × KPI 基准 × 案例索引 / 数据飞轮 MVP / 视觉参考层 / Agency Brief 分发 / 4 个新兴行业模板（电竞/宠物/银发/ESG）

### v3.3.0 — 企业级生产化改造

SSOT manifest / 懒加载指令 / 零配置启动 / Schema bundle（-93% IO）/ 成本预估工具 / 10 项健康检查

### v3.2.0 — Enterprise Audit Release

Business Case + ROI 论证 / Craft 工艺指导 / 传统媒体策略 / 危机管理工作流 / 21 世纪营销理论 / 国际合规（FTC/ASA/GDPR）/ Auto-Cruise 三档巡航 / 创意回炉循环

### v3.0 — 动态架构（Anthropic 工作流范式）

Adversarial Verification / Tournament / Generate-and-Filter / Token Budget / Quarantine

### 评估演进

| 版本 | v3.0 | v3.2 | v3.3 | v3.4 |
|------|------|------|------|------|
| **综合得分** | 75 (B) | ~88 (A-) | ~92 (A) | **~95 (A)** |

详见 [`references/industry-vertical-evaluation.md`](./references/industry-vertical-evaluation.md)。

---
# 加入群聊

<div align="center">
  <img src="https://qomob.ai/xskill.jpg" width="600" alt="XSkill">
</div>

---

## License

Apache License 2.0 — 见 [LICENSE](./LICENSE)

Copyright 2026 Qomob.ai & XSkill.dev
