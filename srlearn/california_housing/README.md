# california_housing

## Task

**Regression**: Predict the median house value for California districts,
in units of hundreds of thousands of dollars ($100,000).

```prolog
med_inc(+id,#varmed_inc).
house_age(+id,#varhouse_age).
ave_rooms(+id,#varave_rooms).
ave_bedrms(+id,#varave_bedrms).
population(+id,#varpopulation).
ave_occup(+id,#varave_occup).
latitude(+id,#varlatitude).
longitude(+id,#varlongitude).
med_house_val(+id).
```

## Overview

This is based on the scikit-learn `sklearn.datasets.fetch_california_housing`,
which was based on a copy from the StatLib repository.
https://www.dcc.fc.up.pt/~ltorgo/Regression/cal_housing.html

These are the notes accompanying the scikit-learn documentation:

```
This dataset was derived from the 1990 U.S. census, using one row per census
block group. A block group is the smallest geographical unit for which the U.S.
Census Bureau publishes sample data (a block group typically has a population
of 600 to 3,000 people).

An household is a group of people residing within a home. Since the average
number of rooms and bedrooms in this dataset are provided per household, these
columns may take surpinsingly large values for block groups with few households
and many empty houses, such as vacation resorts.
```

## Creating Folds

Something similar to the dataset shown here can also be created with the scikit-learn `fetch_california_housing` method. For example, the following shows how to split the dataset into five folds and create `train` and `test` objects.

```python
from sklearn.datasets import fetch_california_housing
from sklearn.model_selection import KFold
from sklearn.preprocessing import KBinsDiscretizer
from relational_datasets.convert import from_numpy

housing = fetch_california_housing()

X, y = housing.data, housing.target

variable_names = [
    "med_inc", "house_age", "ave_rooms",
    "ave_bedrms", "population", "ave_occup",
    "latitude", "longitude", "med_house_val",
]

disc = KBinsDiscretizer(n_bins=5, encode="ordinal")

for i, (train_ind, test_ind) in enumerate(KFold(n_splits=5).split(X)):

    X_train = disc.fit_transform(X[train_ind]).astype(int)
    X_test = disc.transform(X[test_ind]).astype(int)

    train, modes = from_numpy(X_train, y[train_ind], names=variable_names)
    test, _ = from_numpy(X_test, y[test_ind], names=variable_names)

print("\n".join(modes))
```

## References

- Pace, R. Kelley and Ronald Barry, Sparse Spatial Autoregressions,
  Statistics and Probability Letters, 33 (1997) 291-297
