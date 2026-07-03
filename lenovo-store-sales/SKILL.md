---
name: lenovo-store-sales
description: Create concise Chinese Lenovo retail product highlights and in-store sales talk tracks from a product photo, product link, pasted specs, or plain-language description. Use for Lenovo store sales enablement, customer-facing pitch preparation, product comparison talking points, objection handling, and transforming ThinkPad, Yoga, Legion, Xiaoxin, desktop, all-in-one, tablet, monitor, accessory, or other Lenovo product information into short retail-ready copy.
---

# Lenovo Store Sales

## Overview

Turn a Lenovo product photo, link, pasted specs, or text description into a short Chinese product highlight and 3-5 practical in-store sales talk tracks.

Default to concise, spoken, retail-friendly Chinese. Keep claims factual, avoid invented specs, and use competitor comparisons only when they are fair, relevant, and supported by the available information.

## Workflow

1. Identify the input type.
   - For photos: inspect visible model names, series labels, configuration stickers, ports, screen form factor, color, keyboard, bundled accessories, and any price tag or promotion text.
   - For links: open the user-provided link when available; verify current product facts against Lenovo official pages or credible retailer/product pages when specs, prices, or positioning may have changed.
   - For text: extract product name, series, configuration, scenario, budget, customer concern, and any stated competitor.

2. Confirm facts before selling.
   - Separate confirmed facts from assumptions.
   - Do not invent CPU/GPU, memory, storage, screen, battery, warranty, price, stock, promotion, or after-sales policy.
   - If the product is ambiguous, produce a useful output based on visible/provided facts and add one concise clarification question only when the missing detail materially affects the pitch.

3. Read `references/sales-framework.md` before drafting final sales copy unless the user explicitly asks for a one-off quick answer.
   - Use it for audience matching, category selling angles, competitor comparison boundaries, objection handling, and prohibited claims.

4. Shape the selling angle.
   - Lead with the customer job: office efficiency, study, gaming, design, portability, family use, business reliability, conference work, or accessories/ecosystem expansion.
   - Pick 2-4 strongest product highlights instead of listing every spec.
   - Convert specs into benefits: "what this means for the customer in store".

5. Draft the output.
   - Write in Chinese unless the user asks otherwise.
   - Keep the product highlight to 80-120 Chinese characters when enough product information is available.
   - Provide 3-5 sales talk tracks, each suitable for a salesperson to say aloud in store.
   - Include competitor comparison only when a relevant competitor, price band, or customer concern is present; keep it balanced and non-disparaging.

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
- [只列影响准确性的限制、假设或需要门店确认的信息。若无关键限制，可省略本节。]
```

## Quality Bar

- Sound like an experienced Lenovo store salesperson, not a product brochure.
- Prefer short sentences that can be spoken naturally in front of a customer.
- Avoid absolute claims such as "最强", "第一", "全网最低", "永不卡顿", "百分百适合", unless directly supported and legally safe.
- Avoid unsupported promises about price, inventory, gifts, warranty, return policy, financing, delivery, or enterprise procurement.
- When using current specs, prices, promotions, rankings, or recently released products, verify with browsing and cite or summarize the source basis in `核验/注意`.
