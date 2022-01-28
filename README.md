# COVID19 Mortality Prediction Project

The COVID19 pandemic has devastated the world, leaving over 5.1 million people dead since it's first appearance in 2019. The primary causes of death include a buildup of fluid in the lungs that results in suffocation, as well as organ damage due to cytokine storms. Diagnosis occurs via PCR tests, and disease prognosis is indicated by various patient features and chest X-rays. This project seeks to determine if we can take various sources of patient data (vitals, protein levels, etc) in addtion to X-ray images, and determine if we can predict the likelihood of patient mortality. Being able to make such predictions would allow medical practioners to allocate resources to high risk patients and lessen the burden on an already strained healthcare infrastructure.

## Data Sources
Data taken from: https://www.kaggle.com/toxite/covid-19-cxr-ny-sbu

Data was curated from: https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=89096912#89096912bcab02c187174a288dbcbf95d26179e8

Patient Chest X-Rays and metadata were used from COVID19 positive patients at Stony Brook University medical center in Stony Brook, NY. The patient data contains information about vitals (heart rate, blood pressure, oxygenation levels, etc.), protein levels (A1c, enzymes, etc), and electrolyte levels (sodium, chloride, etc). Multiple X-rays were taken of each patient at various time points and uploaded to the cancer image archive. The images were enhanced by a kaggle user and uploaded as a functional dataset. Enhanced images were used to to train CNN models. 

## Final Model Results and metrics

### CNN model
A Convoluntional neural network (CNN) model was used to evaluate patient images in order to predict the likelihood of patient mortality. The final model was chosen due to the loss function being similar for both training and test sets, and the accuracy for both increased with each epoch:

![image](https://user-images.githubusercontent.com/72315132/151589704-0f5f413a-cbb4-4864-b634-56fdf60d87a3.png)


Previously attempted CNN models can be seen in the following notebook: 
https://github.com/AMcqueen1980/COVID19_MortalityPred/blob/main/COVID19_xray_imganalysis.ipynb

Previous models either overfit to the training data, or did not have as high accuracy as the final model (61.2%).
With increased computing power and more images, it is possible to get even greater accuracy and a better performing model to make predictions. Due to time constraints and the limited computing power of my machine, this model was chosen to make predictions about the probability of mortality.


### KNN models

A KNN model ended up being the best model to use, with 91.6% accuracy on patient data alone. This model also minimized type 1 errors, which is ideal for these types of predictions:

  ![image](https://user-images.githubusercontent.com/72315132/151558199-0e12fd3a-9c2c-4dcf-9d06-adf9b6bd8867.png)
  
After making mortality probability predictions with the CNN model, these values were added to patient data and used as an additional feature to train and predict with the above KNN model. The final predictions had slightly higher accuracy (92.5%), did not overfit, and minimized type I errors:

![image](https://user-images.githubusercontent.com/72315132/151591018-8151c3e3-76f8-4e7a-bd9e-aebb60b73cd6.png)



## Summary
This project details the creations and predictions of machine learning models capable of predicting the probability of patient mortality from COVID19 infection using various sources of medical data. These models could be vastly improved by taking the following steps:

• **Increased computing power** This would single-handedly improve models by allowing more images for training and validation, larger image sizes for processing, and implementing further changes listed below.
• **Using object detection methods to modify images** Ports due to medical devices in each image could potentially inhibit model learning by assigning values to generate arrays that are not true to the lung image by itself. Object detection could serve to correct for these estimates to allow for a better fitting model.
• **Increased number of patients** While there were many images to train the CNN model, there were only about 1330 original patients that were used for the final modeling. Increasing the sample size is always a good method to improve model metrics and performance.

While futher improvements would be necessary to optimize for practical use, the use of CNN networks for diagnosis and detection of various diseases is a current area of research in medical informatics. In high stakes prediction domains such as medicine, the utmost care and caution must be taken when creating these models for deployment and practical use amongst medical practioners. As such, much more research is needed before we see these models in every day use.

## Repository Structure

```
├── README.md                           <- The top-level README for reviewers of this project
├── COVID19Models_notebook.ipynb        <- Various model creation and optimization for patient data
├── COVID19_SBU_Dataprep.ipynb          <- Cleaning of patient metadata
├── COVID19_xray_imganalysis.ipynb      <- CNN model creation and analysis of X-Ray images
├── Final_Notebook.ipynb                <- Final notebook with cleaned data used for final predictions and classification
├── Move_and_reformat_images.ipynb      <- Notebook for reorganizing directory structure on local machine      
├── Presentation.pdf                    <- PDF version of project presentation
└── Data                                <- Cleaned data generated from code. Images and unmodified data available for download via the Kaggle link
```
