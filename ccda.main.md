# `ccda.main`

## Combined Cluster and Discriminant Analysis

### Description
Classification into homogeneous groups using combined cluster and discriminant analysis (CCDA).

---

### Usage

```r
ccda.main(
  dataset, 
  names_vector, 
  nr, 
  nameslist, 
  prior = "proportions", 
  return.RCDP = FALSE, 
  hclust.method = "ward.D"
)
```

---

### Arguments

| Argument | Description |
| :--- | :--- |
| `dataset` | Contains only the dataset as a matrix (without labels). |
| `names_vector` | Contains labels (names of sample origins) for each individual observation. |
| `nr` | Number of randomly coded datasets (RCD) investigated. |
| `nameslist` | Contains the names of sample origins as a list. |
| `prior` | A specified method that can be either `"proportions"` (in the case of different group sizes) or `"equal"` (in the case of equal group sizes). If unspecified, `"proportions"` is used as the default. |
| `return.RCDP` | A logical value indicating whether the method should return the percentages for the randomly coded datasets as a matrix. Not returned, unless set to `TRUE`. |
| `hclust.method` | A specified clustering method referring to the methods defined in the `hclust` stats function. If unspecified, `"ward.D"` is used as the default. |

---

### Details

`ccda.main` determines the basic grouping (Step I). For this it uses hierarchical clustering with Ward's method for the averages of the measured variables. Step II, the core cycle then runs for every one of the obtained groupings. For a suggestion on the number of randomly coded datasets investigated (`nr`), see Appendix in Kovacs et al., 2014. It should be noted that `nr` has a linear influence on the amount of time needed for computing.

Step III, the evaluation of the results is left to the user based on the output of `ccda.main`. Based on these outputs, the function `plot.ccda.result` helps the decision regarding further division.

The subgroups component of the output contains the grouping with the highest corresponding difference value. The iterative further investigation of these subgroups is required in order to obtain homogeneous groups as a final result. One should stop when the highest difference value is reached when every sampling location belongs to the same group.

---

### Value

Returns a list containing the following components:

| Component | Description |
| :--- | :--- |
| `nameslist` | Returns the input `nameslist`. |
| `q95` | The 95% quantiles of the ratios of correctly classified cases by LDA for the randomly coded datasets. |
| `ratio` | Ratios of correctly classified cases by LDA for each coded dataset. |
| `difference` | `ratio` - `q95`. |
| `sub_groups` | Suggestion for subdivision according to the maximal difference value. |
| `RCDP` | Percentages for the randomly coded datasets as a matrix. |

---

### References

Jozsef Kovacs, Solt Kovacs, Norbert Magyar, Peter Tanos, Istvan Gabor Hatvani, Angela Anda (2014): *Classification into homogeneous groups using combined cluster and discriminant analysis (CCDA)*. Environmental Modelling & Software. DOI: [10.1016/j.envsoft.2014.01.010](http://dx.doi.org/10.1016/j.envsoft.2014.01.010)

---

### See Also

* `percentage`
* `plotccda.results`
* `plotccda.q95`
* `plotccda.cluster`

---

### Examples

```r
ccda.main(
  iris[, 1:4], 
  iris[, 5], 
  500, 
  c("setosa", "versicolor", "virginica"),
  prior = "proportions", 
  return.RCDP = FALSE, 
  hclust.method = "ward.D"
)
```
