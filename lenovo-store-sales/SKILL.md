---
name: lenovo-store-sales
description: Create concise Chinese Lenovo retail product highlights and in-store sales talk tracks from a product photo, product link, pasted specs, or plain-language description. Use for Lenovo store sales enablement, customer-facing pitch preparation, product comparison talking points, objection handling, and transforming ThinkPad, Yoga, Legion, Xiaoxin, desktop, all-in-one, tablet, monitor, accessory, or other Lenovo product information into short retail-ready copy. When the exact product model or configuration is unclear, ask the user for the missing model/configuration details before drafting product-specific sales copy.
---

# Lenovo Store Sales

## Overview

Turn a Lenovo product photo, link, pasted specs, or text description into a short Chinese product highlight and 3-5 practical in-store sales talk tracks.

Default to concise, spoken, retail-friendly Chinese. Keep claims factual, avoid invented specs, and use competitor comparisons only when they are fair, relevant, and supported by the available information. If the exact model or configuration is not clear enough to verify, ask for clarification before writing product-specific highlights or talk tracks.

## Workflow

1. Identify the input type.
   - For photos: inspect visible model names, series labels, configuration stickers, ports, screen form factor, color, keyboard, bundled accessories, and any price tag or promotion text.
   - For links: open the user-provided link when available; verify current product facts against Lenovo official pages or credible retailer/product pages when specs, prices, or positioning may have changed.
   - For text: extract product name, series, configuration, scenario, budget, customer concern, and any stated competitor.

2. Apply the Model Gate before drafting.
   - Do not output `产品亮点短介绍` or `销售话术` when the input only identifies a brand, series, or category, such as "小新电脑", "ThinkPad", "拯救者笔记本", "Yoga", or "联想平板".
   - For photos: if the model name, generation/year, or configuration label is unreadable or partially hidden, do not guess. List only visible information and ask for a clearer photo, product link, full model name, or configuration label.
   - For links: if the page contains multiple configurations or selectable CPU/memory/screen/GPU variants, ask which configuration the customer is considering, unless the user has already specified one or the link clearly resolves to one SKU.
   - Pass the gate only when there is enough information to identify the product and the key selling facts that will appear in the final copy.
   - When the gate fails, use the "Insufficient Information Format" below and stop; do not add generic product-specific selling points.

3. Confirm facts before selling.
   - Separate confirmed facts from assumptions.
   - Do not invent CPU/GPU, memory, storage, screen, battery, warranty, price, stock, promotion, or after-sales policy.
   - Verify current product facts with Lenovo official pages, PSREF, Lenovo support pages, or credible retailer/product pages when specs, prices, promotions, rankings, launch recency, or comparisons may have changed.
   - If facts cannot be verified, use only details explicitly provided by the user and say so in `核验/注意`.

4. Read `references/sales-framework.md` before drafting final sales copy unless the user explicitly asks for a one-off quick answer.
   - Use it for audience matching, category selling angles, competitor comparison boundaries, objection handling, and prohibited claims.

5. Shape the selling angle.
   - Lead with the customer job: office efficiency, study, gaming, design, portability, family use, business reliability, conference work, or accessories/ecosystem expansion.
   - Pick 2-4 strongest product highlights instead of listing every spec.
   - Convert specs into benefits: "what this means for the customer in store".

6. Draft the output.
   - Write in Chinese unless the user asks otherwise.
   - Keep the product highlight to 80-120 Chinese characters when enough product information is available.
   - Provide 3-5 sales talk tracks, each suitable for a salesperson to say aloud in store.
   - Include competitor comparison only when a relevant competitor, price band, or customer concern is present; keep it balanced and non-disparaging.
   - Add brief evidence in `核验/注意`, such as "用户提供配置", "联想官网/PSREF核验", or "未能联网核验，仅基于用户输入".

## Output Format

Use this format by default:

```markdown
**产品亮点短介绍**
[80-120字，可直接口播。]

**销售话术**
1. [开场/需求确认话术]
2. [核心卖点转利益话术]
3. [体验引导话术]
4. [对比或促单话术]
5. [异议处理话术；如无必要可省略]

**核验/注意**
- [简短列出事实依据、影响准确性的限制、假设或需要门店确认的信息。若使用了当前规格、价格、促销或竞品信息，必须保留本节。]
```

## Insufficient Information Format

Use this format when the Model Gate fails:

```markdown
**已确认信息**
- [只列用户提供或照片/链接中能明确确认的信息。]

**还需要你补充**
- [请补充完整型号、配置标签、产品链接或更清晰照片。]

**为什么需要补充**
- [说明缺少型号/配置会导致哪些卖点无法真实确认，例如处理器、屏幕、重量、电池、价格、库存或保修。]
```

## Quality Bar

- Sound like an experienced Lenovo store salesperson, not a product brochure.
- Prefer short sentences that can be spoken naturally in front of a customer.
- Avoid absolute claims such as "最强", "第一", "全网最低", "永不卡顿", "百分百适合", unless directly supported and legally safe.
- Avoid unsupported promises about price, inventory, gifts, warranty, return policy, financing, delivery, or enterprise procurement.
- When using current specs, prices, promotions, rankings, or recently released products, verify with browsing and cite or summarize the source basis in `核验/注意`.
- Do not infer one configuration's specs from another configuration in the same Lenovo series.
