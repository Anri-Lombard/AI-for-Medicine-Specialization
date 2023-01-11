# AI for Medical Diagnosis

## Week 1: Disease Detection with Computer Vision

__Applications of Computer Vision to Medical Diagnosis__

- [Medical Diagnosis of Skin Cancer with Computer Vision reaches Human-Level Performance](https://www.nature.com/articles/nature21056) (Paywall)
- [Fundus photograph-based deep learning algorithms in detecting diabetic retinopathy](Fundus%20photograph-based%20deep%20learning%20algorithms%20in%20detecting%20diabetic%20retinopathy.pdf) (Free)
- [Impact of Deep Learning Assistance on the Histopathologic Review of Lymph Nodes for Metastatic Breast Cancer](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6257102/) (Free)

__Handling Class Imbalance and Small Training Sets__

- 3 key challenges:
  1. Class Imbalance
  2. Multi-task
  3. Data size
- Data imbalance means that the number of examples in one class is much larger than the number of examples in another class, and can be countered with _weighted loss_ to get equivalent probabilites for each type of example or _resampling_ to get equivalent amounts of examples of each type.
- Multi-task refers to different tasks that are related to each other, and can be countered with _multi-task learning_ to get better performance on each task.
- Dataset size refers to the small dataset size, and can be countered with _transfer learning_ to get better performance on the task.

__Checking your Model Performance__

- 3 key challenges:
   1. Patient Overlap
   2. Set Sampling
   3. Ground Truth
- Patient overlap is caused by incorrect data splitting. The recommended way to split medical data is to _split by patient_.
- We need to make sure we sample from both the normal and target sets.
- In medicine, inter-observer dissagreement is prevalent, so using _consensus voting_ is a potential solution.

__Quiz__
- [Disease Detection with Computer Vision](../Quizes/C1W1.md)

## Week 2: Evaluating Models

__Key Evaluation Metrics__

- Accuracy = sensitivity * prevalence + specificity * (1 - prevalence)
  - _Sensitivity_ is the proportion of positive examples that are correctly identified as positive.
  - _Specificity_ is the proportion of negative examples that are correctly identified as negative.
  - _Prevalence_ is the proportion of positive examples in the dataset.

__NOTES IN PROGRESS...__