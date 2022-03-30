---
layout: cv
title: Rodrigo Rodriguez's Cheat Sheet
---
# Python Cheat Sheet for CS250


## GENERAL
``` python
import math
import pandas as pd
import altair as alt
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn import tree
from sklearn.ensemble import GradientBoostingClassifier
from sklearn import metrics

dat = pd.read_csv('ur_link')
```

## PANDAS
``` python
dat.dropna()	    => axis, how, tresh, subset, inplace
dat.json_normalize(“data in JSON format”)
dat.fillna(“value_to_replace”)
dat.replace(to_replace=””, value=””)
dat.assign()        => to create a new column in data set, normally works with lambda
dat.describe()      => brief explanation of the data set
dat.filter()        => retrieve matching results
dat.to_markdown()   => to create a table for .md files
```

## NUMPY
``` python
np.NaN          => reference to "Not a Number"
np.random	=> choice, randomint, etc
```

## ALTAIR
``` python
chart = alt.Chart(dat).encode(
    x=alt.X('hp', title='Horse Power'),
    y='mpg',
    color='car'
).mark_circle()

```

## SKLEARN
<p>Documentation: <a href="https://scikit-learn.org/stable/supervised_learning.html">scikit-learn.org</a></p>
``` python
#creation of test/train data
#X_pred = dwellings_ml.filter(df_features.query("f_values > .02").f_names.to_list(), axis = 1)
X_pred = dwellings_ml.drop(['before1980', 'yrbuilt', 'parcel'], axis=1)
y_pred = dwellings_ml.filter(["before1980"], axis = 1)

# Use of models...
X_train, X_test, y_train, y_test = train_test_split(
    X_pred,
    y_pred,
    test_size = .34, 
    random_state = 76)

print(metrics.classification_report(y_test, y_pred))

metrics.plot_confusion_matrix(clf, X_test, y_test)
```

