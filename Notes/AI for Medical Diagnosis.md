# AI for Medical Diagnosis

## Week 1: Disease Detection with Computer Vision

### __Applications of Computer Vision to Medical Diagnosis__

- [Medical Diagnosis of Skin Cancer with Computer Vision reaches Human-Level Performance](https://www.nature.com/articles/nature21056) (Paywall)
- [Fundus photograph-based deep learning algorithms in detecting diabetic retinopathy](Fundus%20photograph-based%20deep%20learning%20algorithms%20in%20detecting%20diabetic%20retinopathy.pdf) (Free)
- [Impact of Deep Learning Assistance on the Histopathologic Review of Lymph Nodes for Metastatic Breast Cancer](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6257102/) (Free)

### __Handling Class Imbalance and Small Training Sets__

- 3 key challenges:
  1. Class Imbalance
  2. Multi-task
  3. Data size
- Data imbalance means that the number of examples in one class is much larger than the number of examples in another class, and can be countered with _weighted loss_ to get equivalent probabilites for each type of example or _resampling_ to get equivalent amounts of examples of each type.
- Multi-task refers to different tasks that are related to each other, and can be countered with _multi-task learning_ to get better performance on each task.
- Dataset size refers to the small dataset size, and can be countered with _transfer learning_ to get better performance on the task.

### __Checking your Model Performance__

- 3 key challenges:
   1. Patient Overlap
   2. Set Sampling
   3. Ground Truth
- Patient overlap is caused by incorrect data splitting. The recommended way to split medical data is to _split by patient_.
- We need to make sure we sample from both the normal and target sets.
- In medicine, inter-observer dissagreement is prevalent, so using _consensus voting_ is a potential solution.

### __Quiz 1__

- [Disease Detection with Computer Vision](../Quizes/C1W1.md)

## Week 2: Evaluating Models

### __Key Evaluation Metrics__

- Accuracy = sensitivity \* prevalence + specificity \* (1 - prevalence)
  - _Sensitivity_ is the proportion of positive examples that are correctly identified as positive.
  - _Specificity_ is the proportion of negative examples that are correctly identified as negative.
  - _Prevalence_ is the proportion of positive examples in the dataset.

### __Threshold and Evaluation Metrics__

- _Threshold_ is a value that is used to make a decision or to classify an element of a set, by comparing it to the threshold and determining which of two possible regions the value falls into.
- _ROC Curve_ is a graphical representation of the performance of a binary classifier, plotted as the true positive rate against the false positive rate at different threshold settings.

### __Interpreting Confidence Intervals Correctly__

- _Confidence intervals_ in statistics are a range of values, calculated from a sample of data, that are used to provide an estimate of an unknown population parameter and indicate the level of uncertainty surrounding that estimate; however, it is commonly mis-interpreted as the the probability of the true parameter falling in that interval, it is rather an estimation of how often the intervals will include the true parameter if many samples were taken and intervals were constructed.

### __Quiz 2__

- [Evaluating Machine Learning Models](../Quizes/C1W2.md)

## Week 3: Image Segmentation on MRI Images

### __Image Segmentation__

- [U-Net: Convolutional Networks for Biomedical Image Segmentation](U-Net.pdf)
- _Image segmentation_ for brain tumors involves registering an image of the brain to a reference image, and then using techniques such as 2D or 3D segmentation to identify and separate the tumor from healthy tissue; 2D segmentation methods may struggle with accurately capturing the shape of the tumor and its relationship to surrounding structures, while 3D methods can be computationally intensive and require larger amounts of data.
- _U-Nets_ are a type of convolutional neural network (CNN) architecture for image segmentation, which uses a "U" shaped architecture consisting of a contracting path to capture context and a symmetric expanding path that enables precise localization.
- _Soft Dice loss_ is a measure of the similarity between two sets of data, commonly used as a loss function for training CNNs in semantic segmentation tasks, which calculates the Sørensen–Dice coefficient (a measure of similarity between two sets) with a smoothing term to address the class imbalance problem.

### __Practical Considerations__

- _Prospective data_ is collected from patients specifically for the purpose of training a model, while _retrospective data_ is collected from patients for clinical purposes and then retrospectively used for training a model.
- _Decision curve analysis_ (DCA) is a method for evaluating a diagnostic or predictive model that seeks to evaluate the clinical benefit of a model by plotting the net benefit of the model's predictions against various threshold probabilities, while _Randomized control trial_ (RCT) is a research study in which patients are randomly assigned to one of two or more groups, one that receives a treatment and the other a control, the treatment and control groups are followed and compared for a designated outcome. Both methods are commonly used for measure patient outcomes.

### __Quiz 3__

- [Segmentation on Medical mages](../Quizes/C1W3.md)
