# AI for Medical Prognosis

## Week 1: Linear Prognostic Models

__What is the Risk of Getting a Disease?__

- _Medical prognosis_ refers to the prediction of the likely course and outcome of a medical condition based on the patient's current condition and medical history.

__Prognostic Models in Medical Practice__

- AI prognosis in medicine is the process of using machine learning algorithms and techniques to create models that predict the likelihood of a patient's future medical outcome, based on the patient's current condition, medical history and other relevant data, typically these models output a risk score which can be a number or a probability that indicates the level of risk for a specific outcome.

__Evaluating Prognostic Models__

- Concordant pairs and discordant pairs are measures used to evaluate the performance of prognostic models. They are used to assess the ability of a model to rank individual cases according to their risk of an event, such as death or disease.
    
    A _concordant pair_ is a pair of individuals where the individual with the higher predicted risk also has a higher observed event rate. In other words, the model's prediction is in agreement with the observed outcome for those individuals.

    A _discordant pair_ is a pair of individuals where the individual with the lower predicted risk actually has a higher observed event rate. In other words, the model's prediction is not in agreement with the observed outcome for those individuals.

    _Risk-ties_ are cases with the same predicted risk. They can be understood as ties in the ranking of predicted risk and they don’t contribute to the concordance statistic.

    When evaluating the performance of a prognostic model, a greater number of concordant pairs and a lower number of discordant pairs are desirable. The ratio of concordant pairs to discordant pairs is commonly used to assess the model's performance and it is known as the concordance index or c-index. The c-index is a measure of the model's ability to discriminate between high- and low-risk individuals. It ranges between 0.5 (random prediction) and 1.0 (perfect prediction)

- The _c-index_, also known as the concordance index, is a measure of the performance of a prognostic model that ranges between 0.5 and 1, it assesses the model's ability to discriminate between high- and low-risk individuals, by counting the number of concordant pairs (agreements between predicted and observed event) and discordant pairs (disagreements between predicted and observed event) among all pairs of individuals.

__Quiz__

- [Prognostic Models](../Quizes/C2W1.md)

## Week 2: Prognosis with Tree-based Models

__Tree-based Models__

- A _decision tree_ for medical prognosis is a model that uses a flowchart-like structure to predict the outcome of a patient's condition by making sequential decisions based on the values of certain features, dividing the feature space into rectangular regions (horizontally and vertically) with each internal node representing a feature and each leaf node representing a class label.
- _Preventing overfitting_ in decision tree models can be achieved by techniques such as pruning, setting minimum number of samples required at a leaf node, or by using ensemble methods such as random forests.
- _Random forests_ are an ensemble learning method that combines multiple decision trees to improve the overall performance and reduce overfitting by averaging the results of multiple decision trees trained on different subsets of the data.
- Ensemble methods such as _gradient boosting_, _XGBoost_, and _LightGBM_ are tree-based algorithms that create a sequence of decision trees to improve the overall performance by combining the predictions of multiple weak decision trees, where gradient boosting and XGBoost use gradient descent for optimization, LightGBM uses a novel technique called gradient-based one-side sampling (GOSS) and exclusive feature bundling (EFB) which results in faster training time.

__Identifying Missing Data__

- Missing data can be classified into three categories:

  1. Missing Completely at Random (MCAR) - the data is missing completely at random and there is no relationship between the missing data and the other variables in the dataset.
  2. Missing at Random (MAR) - the data is missing at random and the probability of the data being missing is related to other variables in the dataset but not the missing data itself.
  3. Not Missing at Random (NMAR) - the data is not missing at random and the probability of the data being missing is related to the missing data itself.
     
  It is important to understand the pattern of missingness in data because it can affect the validity of the results obtained from the analysis.

__Using Imputation to Handle Missing Data__

- Imputation of missing data is a technique used to substitute the missing values with estimated ones. There are various methods for imputation such as:

    1. Mean/Median imputation: Replacing missing values with the mean or median of the non-missing values for that variable.
    2. Random sample imputation: Replacing missing data with random values that are similar to the non-missing data.
    3. Regression imputation: Modeling the relationship between the missing data and other variables and then using the model to predict the missing values.
    4. Multiple imputation: Creating multiple imputed datasets by imputing the missing data multiple times and then combining the results.
    5. Hot-Deck imputation: replacing missing values with values from similar observations.

    It's important to note that imputation of missing data can introduce bias into the dataset, so it is important to choose an appropriate method and evaluate the impact of imputation on the analysis.

__Quiz__

- [Decision Trees, Missing Data and Imputation](../Quizes/C2W2.md)

## Week 3: Survival Models and Time

__Survival Estimates__

- A survival function, also known as a reliability function, is a probability distribution function used in survival analysis to describe the probability that an individual will survive beyond a certain time point. The two main properties of a survival function are:

  1. Non-increasing property: The survival function is non-increasing, meaning that the probability of survival cannot increase as time goes on.
  2. Starting at 1: The survival function starts at 1, meaning that at time zero, the probability of survival is 1, and as time goes on, it decreases.
  
  It is defined as $S(t) = P(T>t)$ where T is the survival time. The survival function can handle right-censored data, which means that some individuals may not have experienced an event (e.g. death) at the time of analysis and their survival time is unknown. A common representation of the survival function is the Kaplan-Meier estimator, which is a non-parametric method for estimating the survival function from observed data. It works well when the censoring rate is low and the number of events is high.

__Estimate Survival with Censored Data__

- _Right censoring_ occurs when an individual has not yet experienced an event (e.g. death) at the time of analysis and their survival time is unknown, and it needs to be handled when estimating the survival function in survival analysis.
- The _Kaplan-Meier estimator_ is a non-parametric method for estimating the survival function that takes into account right censoring by calculating the probability of survival at each time point as the proportion of individuals who have not yet experienced the event at that time point. The Kaplan-Meier estimator is given by the formula: S(t) = (n(t) - d(t)) / n(t).

__Quiz__

- [Survival](../Quizes/C2W3.md)

## Week 4: Build a Risk Model Using Linear and Tree-based Models

_Survival and Hazard Functions_

- A _hazard function_, also known as the failure rate, is a function that describes the instantaneous rate of failure at a specific time point in survival analysis, which can provide insight into the underlying cause of failure and the impact of covariates on the failure rate.
- The hazard function (h(t)) and the survival function (S(t)) are related through the following relationship:

  $S(t) = exp(-∫h(t)dt)$

  The survival function can be calculated from the hazard function by taking the integral of the hazard function from 0 to t and then taking the exponential of the negative of that value.

  On the other hand, the hazard function can be calculated from the survival function by taking the derivative of the negative logarithm of the survival function with respect to time.

  Therefore, to go from hazard function to survival function we use the cumulative integral of the hazard function and to go from survival function to hazard function we use the derivative of the negative logarithm of the survival function.


