# ☕ Coffee Shop Sales Analysis
### Uncovering the Lower Manhattan Evening Revenue Gap

> **Role:** Junior Data Analyst — Portfolio Project  
> **Dataset:** Coffee Shop Sales (149,116 transactions · Jan–Jun · 3 NYC stores)  
> **Tools:** Python · Pandas · Matplotlib · ReportLab  

---

## 📌 Business Problem

While all three coffee shop locations contribute nearly identical total revenue
(~33% each), a granular hourly analysis reveals a significant and persistent gap:

> *"Lower Manhattan store captures only **125 transactions** during the 7–8 PM hour
> — **97% fewer than Astoria (3,565)** — consistently across all 6 months,
> pointing to an unresolved operational cutoff that results in an estimated
> **$6,191+ in unrealized revenue** over the analysis period."*

This finding was invisible in summary-level reporting because the store's overall
revenue share looks healthy. It was only discovered through **hourly dimensional
drill-down** — exactly the kind of analysis this project demonstrates.

---

## 🔍 The Key Finding at a Glance

| Store | Total Revenue | % of Total | 7–8 PM Revenue Share | 7–8 PM Transactions |
|---|---|---|---|---|
| Astoria | $232,244 | 33.23% | 7.3% | 3,565 |
| Hell's Kitchen | $236,511 | 33.84% | 4.6% | 2,402 |
| **Lower Manhattan** | **$230,057** | **32.92%** | **0.3% ⚠️** | **125** |

---

## ❓ Five Business Questions Investigated

### Q1 — Which store underperforms at which hour, and by how much?
The heatmap below shows revenue share (%) earned per hour per store.
Lower Manhattan's 7–8 PM cell (blue outline) is the only near-zero cell in the entire grid.

![Chart 1 – Revenue Heatmap](charts/chart1_heatmap.png)

**Finding:** All three stores behave similarly throughout the day — until 7 PM,
when Lower Manhattan drops to 0.3% while Astoria peaks at 7.3%.

---

### Q2 — Is the gap a weekday problem or does it happen on weekends too?
A natural hypothesis: Lower Manhattan is a financial district — offices empty by 6 PM.
If that were the cause, weekends should show normal evening activity.

![Chart 2 – Weekday vs Weekend](charts/chart2_weekday_weekend.png)

**Finding:** The gap is equally severe on weekends (22 transactions) and weekdays (103).
This **rules out the office-crowd hypothesis** and confirms an operational cutoff.

---

### Q3 — What products drive Astoria's 7–8 PM sales that Lower Manhattan lacks?
If Lower Manhattan is missing evening-specific products, the problem could be a menu gap.

![Chart 3 – Product Mix](charts/chart3_products.png)

**Finding:** Both stores offer the same products at 7–8 PM. The difference is entirely
volume — **20–40x fewer transactions** at Lower Manhattan across every category.
The store is barely operational at that hour, not simply less popular.

---

### Q4 — Is the gap worsening, stable, or improving over 6 months?
A month-by-month view tests whether the pattern is temporary or structural.

![Chart 4 – Monthly Trend](charts/chart4_trend.png)

**Finding:** Astoria nearly doubles its 7–8 PM transactions from January to June
(415 → 853). Lower Manhattan stays flat at 12–31 transactions the entire period.
**Six consecutive months of flatness confirms this is structural, not seasonal.**

---

### Q5 — How much revenue could Lower Manhattan recover?
Using a **conservative benchmark** (50% of peer store average), the monthly gap is estimated.

![Chart 5 – Revenue Opportunity](charts/chart5_opportunity.png)

**Finding:** Even at just 50% of peer performance, Lower Manhattan is leaving
**$6,191 unrealized across 6 months** (~$1,032/month). At full parity: ~$12,400.
As peer stores grow month-over-month, inaction becomes increasingly costly.

---

## 🔎 Root Cause Analysis (5 Whys)

| # | Question | Answer |
|---|---|---|
| Why 1 | Why so few transactions at 7–8 PM? | 91% transaction drop between 6–7 PM and 7–8 PM in a single hour |
| Why 2 | Why a cliff, not a gradual decline? | Sudden cliff = something stops (closing time), not declining demand |
| Why 3 | Why does Astoria stay strong all evening? | Astoria's 7–8 PM is its busiest hour — real evening demand exists |
| Why 4 | Why undetected for 6 months? | Summary revenue (~33%) looks healthy; hourly gap is hidden |
| **Why 5 — Root cause** | **Why the operational cutoff?** | **Lower Manhattan likely closes ~7 PM based on an assumption that the financial district empties after office hours — a premise the data contradicts** |

---

## 💡 Recommendation

**Pilot extended operating hours at Lower Manhattan to 8 PM for 1 month.**

| Item | Detail |
|---|---|
| Target | Reach 50% of Astoria's average 7–8 PM transaction volume (~1,700/month) |
| Expected uplift | $1,000–$1,500/month (conservative) · up to $2,000+ at parity |
| Success metric | 7–8 PM transaction count and revenue vs. baseline month |
| Key caveat | Staffing cost for 1 additional hour × 30 days must be weighed against uplift |

---

## ⚠️ Limitations

The analysis is based entirely on transaction data. These data points would
strengthen the root cause confirmation:

- **Store operating hours log** — directly confirm whether Lower Manhattan closes at 7 PM
- **Staff scheduling records** — verify staffing reductions after 6 PM
- **Foot traffic data** — determine whether evening demand exists outside the store
- **Cost data** — model ROI of extended staffing hours
- **Customer feedback** — assess whether evening unavailability is a known pain point

---

## 📁 Repository Structure

```
coffee-shop-analysis/
│
├── README.md                          ← You are here
├── coffee_shop_analysis_report.pdf    ← Full analyst report (PDF)
│
├── data/
│   └── Coffee_Shop_Sales.xlsx         ← Source dataset
│
├── notebook/
│   └── analysis.py                    ← Full Python analysis script
│
└── charts/
    ├── chart1_heatmap.png             ← Q1: Revenue share heatmap
    ├── chart2_weekday_weekend.png     ← Q2: Weekday vs weekend gap
    ├── chart3_products.png            ← Q3: Product mix comparison
    ├── chart4_trend.png               ← Q4: 6-month trend line
    └── chart5_opportunity.png         ← Q5: Revenue opportunity sizing
```

---

## 🛠️ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/YOUR-USERNAME/coffee-shop-analysis.git
cd coffee-shop-analysis

# 2. Install dependencies
pip install pandas matplotlib openpyxl reportlab

# 3. Run the analysis
python notebook/analysis.py
```

---

## 🧠 Skills Demonstrated

`Exploratory Data Analysis` · `Anomaly Detection` · `Dimensional Drill-down`  
`Business Problem Framing` · `Root Cause Analysis (5 Whys)` · `Opportunity Sizing`  
`Data Visualization` · `Storytelling with Data` · `Python (Pandas · Matplotlib)`

---

*This project was completed as part of a junior data analyst portfolio.
Dataset: Coffee Shop Sales (publicly available sample data).*
