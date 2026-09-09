# `plotccda.results`

## Plot of the results of ccda.main

### Description
Plots the summarized results of CCDA for all possible groupings based on the output of `ccda.main`.

---

### Usage

```r
plotccda.results(x)
```

---

### Arguments

| Argument | Description |
| :--- | :--- |
| `x` | The output list of `ccda.main`. |

---

### See Also

* `ccda.main`
* `plotccda.cluster`
* `plotccda.q95`

---

### Examples

```r
result <- ccda.main(
  iris[, 1:4], 
  iris[, 5], 
  500, 
  c("setosa", "versicolor", "virginica"),
  "proportions", 
  return.RCDP = FALSE
)

plotccda.results(result)
```
