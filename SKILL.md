---
name: ltv-margin-to-cac-calculator
description: Calculates a Shopify brand's first-order profit, CAC payback month, and LTV margin to CAC at 3, 6, 9 and 12 months, fills in the free LTV Margin:CAC / Payback Calculator sheet, and shows which levers would improve the business most. Use when someone asks to run their LTV to CAC, LTV margin to CAC, payback period, unit economics, or "fill in the LTV calculator". Built by Sarah Carusona / BA Commerce.
---

# LTV Margin to CAC Calculator

You are helping a DTC founder or operator understand their unit economics on Shopify: what they make or lose on a new customer's first order, how many months it takes to earn back what they paid to acquire that customer, and what a customer is worth over 12 months after the cost of making and shipping every order.

The free calculator sheet is here (the user should make their own copy): https://docs.google.com/spreadsheets/d/1RSCbY0jeLCGZ1Vbg8Ij17ydQFTLMV-yoPsKeyGzoaoE/copy

This version covers **Shopify only**.

## Ground rules

- Never invent a number. If you can't pull it and the user doesn't have it, say what's missing and offer a clearly labeled assumption they can accept or change.
- Say where every number came from (which tool, which report, which date range).
- Use plain language. Define a term the first time you use it.
- Ask for inputs in small batches, not all at once. Lead with the ones you can't pull yourself.

## Step 1: See what you can pull

Before asking for anything, check which tools are connected in this session:

- **Shopify** (any Shopify connector or MCP with access to orders, reports or analytics): can usually pull new customer AOV, discounts, refunds, shipping income, the customer cohort report, and sometimes product costs.
- **Ad platforms** (Meta, Google Ads, TikTok, Pinterest, etc.): ad spend.
- **Google Sheets**: lets you write the values straight into the user's copy of the calculator.

Tell the user in one short list what you can pull and what you'll need from them. If nothing is connected, that's fine: walk them through where to find each number (Step 2).

## Step 2: Gather the inputs

Collect each input below. For each one, pull it if you can; otherwise ask the user and tell them exactly where to find it.

### Time frames

- **New customer sales and ad spend:** pull the **last 12 months** first. Then repeat for the **last 3 months** and the **last 30 days**, so the user can see whether things are getting better or worse lately.
- **LTV (cohort data):** use **at least the last 2 to 3 years** of cohorts, and only cohorts with a full 12 months of history for the 12-month numbers. If the business changed a lot (new product, new pricing, new offer, big shift in channels), recent cohorts are more representative than old ones. Point this out and tell the user they can manually override the monthly LTV inputs to weight recent cohorts more. You don't need to do the weighting unless they ask.
- **Costs per order:** last 12 months, unless costs changed recently (new 3PL, new carrier rates, new supplier), in which case use the last 3 months and say so.

### The inputs

| Input | Exactly what it means | Where to find it |
|---|---|---|
| **New AOV** | Average first order value for **new customers**, defined as **gross sales minus discounts** (before refunds, shipping and tax). | Shopify connector, or Shopify Analytics → Reports → first-time vs returning customer sales (filter to first-time). Shopify's AOV is usually gross sales minus discounts, but **check how the user's report defines it** before using it. If their number includes shipping or is after refunds, adjust it and say so. |
| **Refund %** | Refunds and returns on new customer orders, as a % of New AOV. | Shopify sales report (Returns), filtered to new customers if possible; otherwise the store-wide rate. |
| **Shipping income %** | Shipping charged to customers, as a % of New AOV. | Shopify sales report (Shipping charges). |
| **COGS %** | Product cost, including freight to the warehouse and packaging, as a % of New AOV. | Shopify's profit or gross profit report **only if** cost per item is filled in for products (check). Otherwise the user's bookkeeping or supplier invoices. |
| **Merchant processing %** | Payment fees (Shopify Payments, Shop Pay, PayPal, etc.) as a % of New AOV. | Shopify → Finance → payouts / fees, or the payment provider's statements. Typically about 3%. |
| **Fulfillment $ per order** | What it costs to pick, pack and box one order. | 3PL invoices ÷ orders shipped in the same period. If they fulfill in-house, labor plus packing materials ÷ orders. If they only have fulfillment and shipping as one combined number, that's fine: put the combined cost per order in Shipping Fee $ and $0 in Fulfillment $. If their bookkeeping lumps payment processing in with shipping and fulfillment too, take out about 3% of revenue for processing (tell them) and divide the rest by total orders. |
| **Shipping $ per order** | Outbound postage per order. | Carrier or 3PL invoices ÷ orders shipped. If they buy labels in Shopify, Shopify's shipping label charges ÷ orders. |
| **Ad spend** | **All** paid advertising that drives Shopify sales, on every platform (Meta, Google, TikTok, Pinterest, Snap, YouTube, etc.), **plus influencer and affiliate costs.** Not just Meta. Not attributed spend. Everything. | Ad platform connectors, or each ad account's billing, or bookkeeping. Same time windows as new customer sales. If the number comes from a dashboard or report, ask whether it includes influencer and affiliate costs; most media dashboards don't. Leave out Amazon and TikTok Shop ad spend, since this version is Shopify only. |
| **New customer revenue** | Total first-order revenue from new customers on Shopify, gross minus discounts, for the same window as ad spend. | Shopify (same report as New AOV). |
| **Monthly LTV increase, months 0 to 12** | How much more the average new customer spends in each month after their first order, as a % of their first order. | Shopify connector, or Shopify Analytics → Reports → Customer cohort analysis, showing amount spent per customer by month since first order. |
| **Repeat CM1 %** | % of repeat order revenue kept after product, refunds, fees, fulfillment and shipping. | Ask (see below). |

### aMER and CAC

- **aMER** = new customer revenue ÷ total ad spend, for the same window. (It's like ROAS, but on new customers only and using all ad spend, not platform-attributed revenue.)
- **CAC** = Customer Price ÷ aMER. If the user already knows their blended CAC (total ad spend ÷ new customers), you can work backwards: aMER = Customer Price ÷ CAC.

### Monthly LTV increase

From the cohort report:

1. Use cohorts with at least 12 months of history (see time frames above).
2. Check how the export labels months. Some exports label the first-order month as month 0, others as month -1 with month 0 as the rest of that month. The first-order row is the one where the customer count equals the full cohort size. Say which convention you found.
3. For each month since first order (month 0 = the rest of the month they first bought in, month 1 = the next month, and so on to month 12), take the **extra** spend per customer in that month only. If the report shows cumulative spend, subtract the previous month.
4. Divide by the first-order spend per customer **from the same cohort report**, not by New AOV. The cohort report usually uses a different revenue basis (often net of refunds, or excluding shipping), so dividing by its own first-order number keeps the % consistent. That's the LTV increase % for that month.
5. Weight cohorts by size (add up the dollars across cohorts, then divide), so a tiny cohort doesn't swing the curve.
6. Always divide by the original number of customers in the cohort, never by customers still active.
7. Build the curve two ways: the last 2 to 3 years of mature cohorts, and the most recent 12 mature cohorts. If the recent curve is noticeably lower or higher, show both and let the user pick (or override by hand).
8. Tell the user which cohorts you used and flag anything unusual (a spike from a big sale, very small cohorts, missing months).

### Repeat CM1 %

Ask the user: *"Do you want to assume repeat orders keep the same margin as first orders?"*

Tell them repeat CM1 is usually slightly higher, because repeat customers tend to use smaller discounts and sometimes buy more per order. Suggest a number: their first-order CM1 % plus about 3 to 5 points, unless they have repeat order data that says otherwise. Use whatever they choose.

## Step 3: Calculate

Run this for each time window (12 months, 3 months, 30 days). The LTV curve and repeat CM1 % stay the same across windows unless the user changes them. This is exactly how the calculator sheet works, so your numbers should match it.

```
Customer Price  = New AOV × (1 − Extra discount %)        [extra discount is 0% unless the user is testing one]
CM1 $           = Customer Price
                  − Customer Price × Refund %
                  + Customer Price × Shipping income %
                  − Customer Price × COGS %
                  − Customer Price × Merchant processing %
                  − Fulfillment $
                  − Shipping $
CM1 %           = CM1 $ ÷ Customer Price
CAC             = Customer Price ÷ aMER
CM2 $ (first-order profit) = CM1 $ − CAC
CM2 %           = CM2 $ ÷ Customer Price

For each month m = 0 to 12:
  Repeat revenue_m   = Customer Price × LTV increase_m
  Repeat CM1_m       = Repeat revenue_m × Repeat CM1 %
  Total profit_m     = CM2 $ + sum of Repeat CM1 from month 0 to m
  Gross LTV_m        = Customer Price + sum of Repeat revenue from month 0 to m

Payback month          = first month where Total profit_m > 0
LTV margin to CAC (m)  = Gross LTV_m × Repeat CM1 % ÷ CAC     for m = 3, 6, 9, 12
12-month LTV to CAC    = Gross LTV_12 ÷ CAC
```

## Step 4: Fill in the calculator

Give the user a table they can type straight into their copy of the sheet, one column per time window:

| Cell | Label | 12 months | 3 months | 30 days | Source |
|---|---|---|---|---|---|
| B8 | Repeat CM1 % | | | | |
| B11 | New AOV (gross minus discounts) | | | | |
| B12 | Extra Discount % (optional) | 0% | 0% | 0% | Only change to test an extra discount |
| B15 | Refund % | | | | |
| B16 | Shipping Income % | | | | |
| B17 | COGs % | | | | |
| B18 | Merchant Processing % | | | | |
| B19 | Fulfillment $ | | | | |
| B20 | Shipping Fee $ | | | | |
| B24 | aMER | | | | |
| E12 to E24 | LTV Increase, months 0 to 12 | | (same) | (same) | |

The sheet holds one scenario at a time, so suggest they enter the 12-month version first, then try the others. If a Google Sheets connector is available and the user shares their copy, offer to write the 12-month values in for them.

## Step 5: Show the results and the opportunities

**Results.** For each window, show: CM1 $ and %, CAC, first-order profit (CM2 $ and %), payback month, LTV margin to CAC at 3, 6, 9 and 12 months, and 12-month LTV to CAC. Then say in two or three sentences what changed between the 12-month, 3-month and 30-day numbers and what that suggests.

**Benchmarks** (Sarah Carusona's rules of thumb for fast-growing 7- and 8-figure DTC brands):
- 12-month LTV margin to CAC around **1.6x** is healthy.
- Above **2x**, they may be under-scaling and could likely spend more.
- Below about **1.3x**, CAC is too high, LTV is too low, or product margins are too thin.
- Break-even by **month 3** is a good payback goal. Longer paybacks can work with wholesale, strong investor backing, or real conviction in repeat behavior, but self-funded or still-proving brands should stay at 2 to 3 months.

**Levers.** Using the 12-month window (or the most recent window if it's clearly more representative, and say which), change one input at a time and show how much each moves first-order profit, the payback month and 12-month LTV margin to CAC:
- New AOV up 10% **at the same CAC** (bundles, thresholds, upsells). In the calculator, CAC = Customer Price ÷ aMER, so raise aMER by 10% too. If you only raise AOV, CAC rises with it and the lever looks useless.
- Discount down 5 points **at the same CAC**: New AOV × 1.05 and aMER × 1.05.
- COGS down 3 points: lower COGS % and raise Repeat CM1 % by 3 points, because repeat orders get cheaper too.
- Fulfillment plus shipping down $1 per order: lower Shipping Fee $ by $1 and raise Repeat CM1 % by $1 ÷ Customer Price.
- CAC down 10%: aMER ÷ 0.9.
- Month 1 to 3 repeat spend up 20%: multiply those three LTV increase %s by 1.2.

Rank the three levers with the biggest impact. For each, say in plain language what the brand would actually have to do to pull it.

**Watch-outs.** If the 12-month window includes BFCM or another big sale, point out that it can pull aMER and AOV away from a normal month, and lean on the 3-month and 30-day windows for "where are we now." Flag anything in the data that looks off, and any assumption that changes the answer a lot (for example, an LTV curve built on cohorts from before a big pricing change).

Close by offering to rerun with different assumptions.

---
Built by Sarah Carusona, DTC growth operator and founder of BA Commerce. Video walkthrough: [YouTube link]
