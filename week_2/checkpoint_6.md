## Formulas Used

| Formula | Purpose |
|---|---|
| `=XLOOKUP([@[Order ID]];Orders!B:B;Orders!O:O)` | Pulled Category into Returns sheet by matching Order ID |
| `=SUMIFS(U:U;O:O;A2)` | Summed Profit per Category, referencing category name from a helper cell |
| `=COUNTIFS(U:U;"<0")` | Counted number of loss-making orders (negative Profit) |
| `=IF([@Profit]>0;"Yes";"No")` | Flagged each order as Profitable or not |
| `=IFS([@Discount]=0;"No discount";[@Discount]<0,2;"Low";[@Discount]>=0,2;"High")` | Categorized each order into a Discount Level |
| `=COUNTIFS(W:W;Y2)` | Counted orders per Discount Level |
