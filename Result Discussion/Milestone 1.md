# Skin Cancer Detection using ISIC SLICE-3D Data

## Proposal
### Presentation Comments Comments
- How did we come with the sensitivity threshold of 80% TPR?
- Where is the data in this dataset coming from? What kind of quality images are being received? 
- What is the system component of our project? 
- How does the ROC curve minimize misdiagnosis in the negative cases?

These questions are addressed in the proposal.

### Problem
Skin cancer, including melanoma, basal cell carcinoma, and squamous cell carcinoma, poses significant health risks if not detected early. Many populations, however, lack access to specialized dermatologic care, or for whatever reason, some are hesitant to seek out specialized healthcare. While dermoscopy-based AI algorithms have advanced skin cancer diagnosis, these systems often require high-quality images that are typically available only in specialized clinics. Thus, challenges often lie in developing models that can effectively analyze lower-quality images, such as those taken with cell phones. Our project will tackle the ISIC SLICE-3D dataset to explore whether we can achieve effective skin cancer detection using these more accessible images.
### Data
This project will utilize the ISIC SLICE-3D dataset, which includes cropped non-dermoscopic images of lesions obtained from 3D Total Body Photography (TBP). This dataset contains lesions from a variety of patients seen between the years 2015 and 2024 across nine institutions and three continents. The dataset also includes additional labels such as classifications (targets), patient information (age, sex), lesion details (location on the body, maximum diameter), and other attributes (image source, precise diagnosis).
### Methods

In this approach, we will apply the method from the “Skin lesion classification using ensembles of multi-resolution EfficientNets with metadata” paper. We will begin with collecting and preprocessing skin lesion images along with relevant patient data. We will train various EfficientNet models individually and then develop ensembles of these models to harness their combined predictive power. We will then evaluate our model using the metrics discussed in the next session. 

This paper studied a dataset of dermatoscopic images taken using equipment that is typically provided by a healthcare provider. Our dataset uses images of a similar quality to those produced by a smartphone camera. We want a way for users to be able to take a photo on their phone and get a diagnosis without having to seek out a healthcare provider. To achieve this, we will use cloud resources to do the computation. The user data will be stored with the ability to integrate it into the training data to improve the model. 
### Metric
In clinical practices, especially in systems for cancer detection, high sensitivity is crucial. Therefore, our focus is not only achieving a high performance with our model but ensuring it meets a sensitivity threshold. Our primary evaluation metric, as defined by the ISIC 2024 competition, is the area under the ROC curve, with the additional condition of considering only the area above an 80% true positive rate. 

The ROC curve evaluates the model by plotting the true positive rate against the false positive rate. We only have a threshold on the sensitivity because in clinical practice, a high number of false positives can be managed through follow-up procedures such as additional screenings or biopsies. However, a good diagnostic system should still aim to manage the false positive rate reasonably. Therefore in addition to the ISIC 2024 metrics we will measure each component - sensitivity and specificity.

We plan to compare our results against other submissions in the competition that use the same dataset but different approaches, which will help us understand how our solution fares compared to alternative methods. Additionally, we aim to compare our results with those from the research paper we implemented to assess the generalizability of our method across different datasets and conditions.
### References:
Nicholas Kurtansky, Veronica Rotemberg, Maura Gillis, Kivanc Kose, Walter Reade, Ashley Chow. (2024). ISIC 2024 - Skin Cancer Detection with 3D-TBP. Kaggle. https://kaggle.com/competitions/isic-2024-challenge
Gessert, N., Nielsen, M., Shaikh, M., Werner, R., & Schlaefer, A. (2020). Skin lesion classification using ensembles of multi-resolution EfficientNets with metadata. MethodsX, 7, 100864. https://doi.org/10.1016/j.mex.2020.100864
