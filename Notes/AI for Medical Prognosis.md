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