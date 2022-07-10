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

## References

- Pace, R. Kelley and Ronald Barry, Sparse Spatial Autoregressions,
  Statistics and Probability Letters, 33 (1997) 291-297
