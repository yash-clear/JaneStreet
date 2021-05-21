![Jane Street](https://images.squarespace-cdn.com/content/v1/56e2e0c520c6472a2586add2/1613499391116-T0ZWOVSAAVTVMC8SRO4R/ke17ZwdGBToddI8pDm48kAf-OpKpNsh_OjjU8JOdDKBZw-zPPgdn4jUwVcJE1ZvWQUxwkmyExglNqGp0IvTJZUJFbgE-7XRK3dMEBRBhUpwkCFOLgzJj4yIx-vIIEbyWWRd0QUGL6lY_wBICnBy59Ye9GKQq6_hlXZJyaybXpCc/CP+Index+logos+1+%284%29.png)

## INTRODUCTION
Jane Street hosted a code competition for stock prediction (from Feb 2021 to Aug 2021), with Kaggle: https://www.kaggle.com/c/jane-street-market-predictions, using historical high-frequency trading data (2 years prior to 2018?). Training information is given for a total of 2.4 million rows and includes 500 days of high-frequency trading details. This training dataset contains an anonymized set of features, feature_{0...129}, representing real stock market data. Each row in the dataset represents a trading opportunity.

## Aim
In general, if one is able to generate a highly predictive model which selects the right trades to execute, they would also be playing an important role in sending the market signals that push prices closer to “fair” values. That is, a better model will mean the market will be more efficient going forward. However, developing good models will be challenging for many reasons, including a very low signal-to-noise ratio, potential redundancy, strong feature correlation, and difficulty of coming up with a proper mathematical formulation.

## Proposed Solution
Even the world's finest financial expert wouldn't be able to gain anything from this anonymized data. Hence we are forced to use machine learning or data science approach to solve this problem.
Since the goal is clear (maximize profit) we want to see which features seem important or strange through EDA and visualizations. The dataset is large so operations so performed should be memory efficient. This will help us decide what to do with missing values and do feature engineering to help the computer learn.
Then we are going to build a classifier model to let the computer do the hard work of learning to make good predictions.

### Analysis
Initially, the notebook intends to simplify intricate time-series data from Jane Street Market using Descriptive Statistics and Exploratory Data Analysis which includes:
- Correlation between features and tags.
- Analysis of training dataset(excluding features) 
  -  Missing data
  -  Weights and Resps (Weight and resp multiplied together represents a return on the trade)
  -  Resps and Tags
- Analysis of feature set
  - Correlation between features.
  - Correlation Between features and resps
- Trades per day
### Preprocessing 
- Dropping NULL weights.
- Imputing NAN with mean values.
### Model
Used **CatBoostClassifier** to reduce time spent and although making an ensemble a large dataset is not memory efficient so they were run individually and the highest accuracy is given by CatBoost as compared to xgboost and LightGBM.


