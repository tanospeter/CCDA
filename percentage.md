# `percentage`

## Calculation of the ratio of correctly classified cases by linear discriminant analysis

### Description
Extracts the ratio of correctly classified cases from the output of LDA.

---

### Usage

```r
percentage(dataset, starting_vector, prior)
```

---

### Arguments

| Argument | Description |
| :--- | :--- |
| `dataset` | Contains only the dataset as a matrix (without labels). |
| `starting_vector` | A vector specifying the class for each observation. |
| `prior` | A specified method that can be either `"proportions"` (in the case of different group sizes) or `"equal"` (in the case of equal group sizes). |

---

### Value

Returns a list/value containing:

| Component | Description |
| :--- | :--- |
| `perctg` | The ratio of correctly classified cases by LDA for the input grouping. |

---

### See Also

* `ccda.main`
