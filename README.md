# Customer Friction Analysis: Perpay & BNPL Peers

An independent analysis of **31,252 CFPB consumer complaints** (Nov 2023 – Nov 2026) about **Perpay, Affirm, Klarna, Sezzle, and Self Financial**, to find where customers get stuck and what each team could do about it.

**Tools:** Excel (Power Query, pivot tables) · Power BI (DAX) · PowerPoint


## Key findings

| # | Finding | Evidence |
|---|---|---|
| 1 | **Incorrect credit-report information is the #1 complaint across the industry** | 28% of all complaints (8,870 of 31,252), more than double the #2 issue; top issue for 4 of 5 companies |
| 2 | **It is even higher for Perpay** | 34% of Perpay complaints, driven by incorrect account information (43) and incorrect account status (35) |
| 3 | **BNPL companies have a different pattern** | 32% of Klarna's complaints are about BNPL/personal loans (Perpay: 6%); its top issues are payment problems (16%) and purchases on statements (14%) |
| 4 | **Perpay responds on time** | 100% timely response, tied with Affirm; Klarna is lowest at 93% |

**Why it matters:** Perpay+ is built to help customers build credit. An incorrect report works against that promise, and it creates support work and regulatory risk.

## Recommendations

| Team | Idea | How to measure it |
|---|---|---|
| **Product** | An in-app way to see what was reported to the credit bureaus and flag an error before filing a complaint | Credit-report share of complaints falls from 34% toward the industry's 28% |
| **Merchandising** | Clear order, shipping, and return status shown next to each payment | Purchase complaints stay well below Klarna's 14% as the marketplace grows |
| **CS / BPO** | Tag credit-report complaints by type of error and send Product a monthly friction report | Time to resolve disputes; fewer repeat complaints on the same issue |

## Process

1. **Data:** downloaded complaints for the 5 companies from the [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/) (Nov 11, 2023 – Nov 11, 2026).
2. **Cleaning (Power Query):** removed unused columns, converted dates, standardized text, trimmed values, removed duplicates, and added Year, Quarter, and Timely (1/0) helper columns.
3. **Analysis (pivot tables):** issue share by company, Perpay sub-issues, complaints by year, timely-response rate, and product mix. All comparisons use percentages, because counts reflect company size.
4. **Dashboard (Power BI):** KPI cards, top-10 issues, quarterly trend (log scale, full quarters only), product mix, state map, and company/year slicers. Key measure:

   ```DAX
   % of Complaints = DIVIDE([Total Complaints], CALCULATE([Total Complaints], REMOVEFILTERS(Complaints[Issue], Complaints[Issue Short])))
   ```

5. **Story:** a 5-slide deck with findings, recommendations, and limitations.

## Files

| File | What it is |
|---|---|
| `deck/` | 5-slide presentation (PDF) |
| `dashboard/` | Power BI file (.pbix) and PDF export |
| `analysis/` | Excel workbook with the Power Query steps and pivot tables |
| `data/` | Raw CFPB export (CSV) |
| `images/` | Dashboard screenshots |

## Limitations

- Complaints are customer-reported and not verified by the CFPB.
- Counts reflect company size, so compare percentages, not totals.
- Perpay has 299 complaints, so small sub-issues are noisy.
- Partial quarters are excluded from the trend, and recent data may still be updating.
- This export has no complaint narratives, so root causes are inferred from issue categories.

## About

Built by **Ngoc Mai (Melanie) Duong** · [LinkedIn](https://www.linkedin.com/in/melanie-duong-1b8aa0254/) · [Portfolio](https://maiiduong.github.io/melanieduong.github.io/)

*Independent portfolio project using public data. Not affiliated with or endorsed by any of the companies analyzed.*
