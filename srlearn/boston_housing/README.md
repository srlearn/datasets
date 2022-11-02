# boston_housing

!!! warning end
    The Boston Housing dataset is deprecated. It is included here for backwards compatibility and reproducing results in old publications, but should not be used for benchmarking future results.

    The dataset contains a variable `B` which is ethically problematic. The original dataset authors assumed that Black neighbors were undesirable, and that this would affect housing prices. However, this assumption was encoded in a way that makes it impossible to analyze further.

    We recommend the "California Housing" dataset instead.

    **See also**:

    - M Carlisle, "[racist data destruction?](https://medium.com/@docintangible/racist-data-destruction-113e3eff54a8)" Medium.com, retrieved: 2022-11-02
    - [sklearn.datasets.load_boston (archived)](https://web.archive.org/web/20221014215704/https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_boston.html)

"Boston Housing" is a common benchmark dataset for regression.

## Task

**Regression**: Predict the median value of homes.

```prolog
crim(+id,#varsrim).
zn(+id,#varzn).
indus(+id,#varindus).
chas(+id,#varchas).
nox(+id,#varnox).
rm(+id,#varrm).
age(+id,#varage).
dis(+id,#vardis).
rad(+id,#varrad).
tax(+id,#vartax).
ptratio(+id,#varptrat).
b(+id,#varb).
lstat(+id,#varlstat).
medv(+id).
```
