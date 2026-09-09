# `plotccda.cluster`

## Plot of the basic grouping

### Description
The function `plotccda.cluster` draws the dendrogram for the basic grouping using hierarchical clustering for the averages with Ward's method (as used in `ccda.main`).

---

### Usage

```r
plotccda.cluster(x)
```

---

### Arguments

| Argument | Description |
| :--- | :--- |
| `x` | The output list of `ccda.main`. |

---

### See Also

* `ccda.main`
* `plotccda.results`
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

plotccda.cluster(result)
```
