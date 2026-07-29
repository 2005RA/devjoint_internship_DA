## Calculated Fields (SUMIFS, COUNTIFS, IF / Nested IF / IFS)

1. I created a small table with category names and used `=SUMIFS(U:U;O:O;W13)` formula in front of Furniture (W13) row to calculate how much profit each category earned. Results:

| Category | Sum of Profit |
|---|---|
| Furniture | 19,729.9956 |
| Office Supplies | 126,023.4434 |
| Technology | 146,543.3756 |

![Chart](../Results/2ch4_2.png)

2. I used `=COUNTIFS(U:U;"<0")` formula to count the number of negative profit (loss). Result: **1901**

3. I used `=IF([@Profit]>0;"Yes";"No")` to find out which orders were profitable and which were not.

![Chart](../Results/2ch4_3.png)

4. I used this formula `=IFS([@Discount]=0;"No discount";[@Discount]<0,2;"Low";[@Discount]>=0,2;"High")` to assign titles for discounts. Then I used the COUNTIFS formula `=COUNTIFS(W:W;Y2)` to count high, low, and no discounts. Results:

| Discount Level | Count |
|---|---|
| High | 5121 |
| Low | 148 |
| No discount | 4925 |

![Chart](../Results/2ch4_5.png)
