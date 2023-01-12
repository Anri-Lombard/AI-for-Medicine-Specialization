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
