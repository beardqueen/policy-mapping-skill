# Policy Mapping｜政策产品雷达

![Policy Mapping｜政策产品雷达核心能力](docs/policy-mapping-core-capabilities.png)

> **把政策变化，变成产品变化。**  
> From Policy Change to Product Change.

**不是告诉你“出了什么政策”，而是告诉你“这项政策会让什么产品发生什么变化”。**

Policy Mapping 将中国政策变化继续向下映射：

**政策 → 规则 → 行业 → 企业 → 产品 → 功能 / 技术 / 运营**

## 与普通政策抓取有什么不同？
普通工具通常停在：`发现 → 抓取 → 摘要 → 分类 → 新闻`

Policy Mapping 继续到：`政策生命周期 → Policy Event Chain → 规则变化 → 行业/企业 → 产品/系统 → 功能/API/算法/IoT/运营 → P0-P3 → 产品变化雷达`

它回答的不只是“最近发生了什么？”，而是：**这项政策会让哪些产品发生什么变化？**

## L1 → L2 → L3

```mermaid
flowchart LR
A[全国官方政策源] --> B[发现/去重]
B --> C[政策生命周期/事件链]
C --> D[规则变化]
D --> E[行业/企业影响]
E --> F[产品映射]
F --> G[P0-P3]
G --> H[L1 政策雷达]
G --> I[L2 产品映射]
G --> J[L3 产品变化卡片]
J --> K[APP/后台/API/数据/算法/IoT/运营]
```

- **L1**：发生了什么政策？
- **L2**：这些政策对产品意味着什么？
- **L3**：重点政策具体改哪里？

## Evidence Boundary
严格区分 **F｜政策事实、I｜企业推导、PS｜产品建议**。AI 产品建议不得冒充政策强制要求。

## ★ 个性化相关度
**★ = Policy × Current User Context**。只有用户明确提供行业、岗位、产品、项目或关注方向时才启用 ★；首次使用或上下文不足时不显示 ★、不猜行业。

## Quick Start

### 1. 首次使用｜全国政策扫描

适合第一次使用，直接扫描最近一段时间的全国政策。

```text
使用 Policy Mapping，扫描最近 7 天全国政策，
输出 L1→L2→L3 政策产品雷达。
```

首次使用且没有足够用户上下文时，自动进入 **Generic Mode**：不显示 ★、不猜测用户行业，也不默认任何行业偏好。

### 2. 个性化扫描｜告诉 Skill 你的行业、岗位或项目

适合已经有明确业务背景，希望雷达优先识别与自己高度相关的政策。

```text
我是跨境电商产品经理，
重点关注支付、税务、物流和平台合规。

使用 Policy Mapping 扫描最近 30 天政策，
告诉我哪些政策可能影响我的产品。
```

只有获得明确上下文后才进入 **Personalized Mode**，并允许根据真实用户上下文标记 ★ 高度相关政策。

### 3. 单条政策深度映射

适合已经拿到一条具体政策，希望直接分析它会带来哪些产品变化。

```text
使用 Policy Mapping 分析这条政策：《XXXX管理办法》。

重点告诉我：
1. 政府改变了什么规则；
2. 哪些行业和企业受影响；
3. 哪些产品或系统需要调整；
4. APP / 后台 / API / 数据 / 算法 / IoT / 运营分别可能改什么；
5. 严格区分政策事实、企业推导和产品建议。
```

### 4. 每小时政策产品雷达

适合持续监测。**Skill 是大脑，不是闹钟**，需要由 GitHub Actions、Cron 或其他 Scheduler 定时触发。

```text
GitHub Actions / Cron / Scheduler
              ↓
        Policy Mapping
              ↓
        全国官方政策源
              ↓
      发现 / 去重 / 事件链
              ↓
          产品映射
         ↙       ↘
    CHANGES     NO_CHANGE
```

如果抓取异常，必须输出 `MONITOR_ERROR` 或 `PARTIAL_ERROR`，不能把“网站抓取失败”误报成 `NO_CHANGE`。
## Repository Description
> Map China policy changes to concrete product, system, API, algorithm, IoT and operations changes — with evidence boundaries and L1→L2→L3 drill-down reports.

## Topics
`policy` `product-management` `ai-agent` `skills` `china-policy` `regtech` `compliance` `product-strategy` `policy-monitoring` `llm`

完整执行规则见 `SKILL.md`。

## License
MIT
