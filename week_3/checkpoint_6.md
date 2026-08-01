## Already Calculated Field

**Measure: Target Sales**
```dax
Target Sales =
VAR SelYear = SELECTEDVALUE(DimDate2[Year])
VAR SelMonth = SELECTEDVALUE(DimDate2[Month])
VAR SelCategory = SELECTEDVALUE(DimProduct[Category])
RETURN
CALCULATE(
    SUM(FactSalesTarget[TargetSalesAmount]),
    FILTER(
        FactSalesTarget,
        FactSalesTarget[Year] = SelYear &&
        FactSalesTarget[Month] = SelMonth &&
        (ISBLANK(SelCategory) || FactSalesTarget[Category] = SelCategory)
    )
)
```

`FactSalesTarget` has no key columns, so it can't be linked via a standard model relationship. This measure resolves the link manually at query time using slicer 
selections, matching Year/Month/Category context from the report to the correct target row. Also powers `Sales vs Target %`.
