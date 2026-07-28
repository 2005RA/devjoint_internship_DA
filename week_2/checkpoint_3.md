## What percentage of orders are returned, per category?

Used `=XLOOKUP([@[Order ID]];Orders!B:B;Orders!O:O)` in the Returns sheet to pull each returned order's category, then built a pivot table of return counts per category, cross-referenced against total order counts per category from the Orders sheet.

| Category | Total Orders | Returned Orders | Return Rate |
|---|---|---|---|
| Furniture | 2,201 | 136 | 6% |
| Office Supplies | 6,128 | 141 | 2% |
| Technology | 1,865 | 19 | 1% |
| **Grand Total** | **10,194** | **296** | **3%** |

![Order Trends Timeline](2ch3_1.png)

Overall, only about 3% of orders are returned which is not a significant issue. **Furniture** has the highest return rate (6%), while **Technology** has the lowest (1%).
