# LTV Margin to CAC Calculator

A free AI skill that works out your Shopify brand's unit economics:

- What you make or lose on a new customer's first order
- How many months it takes to earn back what you paid to get that customer (payback)
- Your LTV margin to CAC at 3, 6, 9 and 12 months
- Which levers would improve it most

It pulls what it can from the tools you have connected (Shopify, ad platforms, Google Sheets), asks you for the rest, tells you exactly where to find each number, and fills in the free calculator sheet for you.

**Calculator sheet (make a copy):** https://docs.google.com/spreadsheets/d/1RSCbY0jeLCGZ1Vbg8Ij17ydQFTLMV-yoPsKeyGzoaoE/copy

**Video walkthrough:** [YouTube link]

## How to use it

**Claude (claude.ai or the desktop app)**
1. Download this repo as a ZIP (green "Code" button → Download ZIP).
2. In Claude, go to Settings → Capabilities → Skills and upload the ZIP.
3. Start a chat and say: "Run my LTV margin to CAC."

**Claude Code**
Copy the `ltv-margin-to-cac-calculator` folder into `~/.claude/skills/`, then ask Claude to run your LTV margin to CAC.

**Any other AI tool**
Open `SKILL.md`, copy everything, paste it into a new chat, and say: "Run this for my brand."

Connecting Shopify and your ad accounts to your AI tool saves the most time, but it works without them. It will just ask you for the numbers.

## What you'll need

- Shopify customer cohort report (2 to 3 years)
- New customer sales for the last 12 months, 3 months and 30 days
- Total ad spend on every platform, plus influencer and affiliate costs, for the same periods
- Product cost (COGS), payment processing, and your fulfillment and shipping cost per order

Shopify only for now.

## About

Built by Sarah Carusona, DTC growth operator and founder of [BA Commerce](https://ba-commerce.com). I've run a 9-figure ecommerce P&L and work with $5-50M DTC brands.
