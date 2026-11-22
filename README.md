# Supplier Segmentation and Expediting Dashboard

An interactive dashboard that segments suppliers using ABC-XYZ analysis and ranks open purchase orders (POs) by how urgently they need expediting.

**Live demo:** open the site link shown in this repository's "About" section (GitHub Pages).

> **Data note:** all data is synthetic (100 suppliers, 12 past deliveries each, 260 open POs). No real company data is used.
> **Build note:** built with AI assistance (Claude) from my own segmentation and prioritization logic. Single HTML file, no installation needed.

## What it does

1. **ABC-XYZ segmentation of suppliers**
   - ABC by annual spend: A = top 80% of spend, B = next 15%, C = last 5%.
   - XYZ by lead-time variability across past deliveries (standard deviation divided by mean): X = steady, Y = some variation, Z = erratic.
   - Each of the nine segments (AX to CZ) has a suggested follow-up routine, for example daily follow-up and an alternate supplier for AZ, one reminder before the due date for CX.
2. **Expedite list for open POs**
   - Lateness chance is estimated from the supplier's past on-time rate, raised when the delivery date is unconfirmed.
   - Priority (High / Medium / Low) combines lateness chance, supplier segment and days until due.
   - Each PO gets a plain-language action, and can be ticked off as chased.
3. **What-if estimate**
   - Choose how many POs you can chase and how often a chase saves a late PO, and see the estimated effect on on-time delivery.

## Limitations

- Lateness chance is a simple estimate from past delivery history, not a trained machine learning model.
- The what-if result depends entirely on the two slider values and is not a measured outcome.
- Segment thresholds (including the XYZ cut-offs) are illustrative and should be tuned on real data.

## How to use with real data

The data is generated inside `index.html` (supplier and PO lists). To try your own data, replace those lists with exported supplier delivery history and open PO data (for example from SAP), keeping any confidential information out of public repositories.

## Tools

HTML, CSS and JavaScript (single file). AI-assisted development (Claude).

