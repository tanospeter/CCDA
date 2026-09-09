# `plotccda.q95`

## CCDA density drawer

### Description
The function `plotccda.q95` draws the simulated density for the randomly coded datasets.

---

### Usage

```r
plotccda.q95(x, pl = "max")
```

---

### Arguments

| Argument | Description |
| :--- | :--- |
| `x` | The output list of `ccda.main` which has to include the RCDP output! (Set `return.RCDP = TRUE` while running `ccda.main`). |
| `pl` | `"max"` if the grouping with the highest difference value is considered or the number of the grouping for which the plot is made. |

---

### See Also

* `ccda.main`
* `plotccda.results`
* `plotccda.cluster`

---

### Examples

```r
result <- ccda.main(
  iris[, 1:4], 
  iris[, 5], 
  500, 
  c("setosa", "versicolor", "virginica"), 
  "proportions", 
  return.RCDP = TRUE
)

plotccda.q95(result)
plotccda.q95(result, pl = 2)
```
