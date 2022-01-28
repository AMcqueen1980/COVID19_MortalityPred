# COVID19 Mortality Prediction Project

The COVID19 pandemic has devastated the world, leaving over 5.1 million people dead since it's first appearance in 2019. The primary causes of death include a buildup of fluid in the lungs that results in suffocation, as well as organ damage due to cytokine storms. Diagnosis occurs via PCR tests, and disease prognosis is indicated by various patient features and chest X-rays. This project seeks to determine if we can take various sources of patient data (vitals, protein levels, etc) in addtion to X-ray images, and determine if we can predict the likelihood of patient mortality. Being able to make such predictions would allow medical practioners to allocate resources to high risk patients and lessen the burden on an already strained healthcare infrastructure.

## Data Sources
Data taken from: https://www.kaggle.com/toxite/covid-19-cxr-ny-sbu

Data was curated from: https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=89096912#89096912bcab02c187174a288dbcbf95d26179e8

Patient Chest X-Rays and metadata were used from COVID19 positive patients at Stony Brook University medical center in Stony Brook, NY. The patient data contains information about vitals (heart rate, blood pressure, oxygenation levels, etc.), protein levels (A1c, enzymes, etc), and electrolyte levels (sodium, chloride, etc). Multiple X-rays were taken of each patient at various time points and uploaded to the cancer image archive. The images were enhanced by a kaggle user and uploaded as a functional dataset. Enhanced images were used to to train CNN models.

## Final Model Results and metrics
A Convoluntional neural network (CNN) model was used to evaluate patient images in order to predict the likelihood of patient mortality.
A KNN model ended up being the best model to use, with 91.6% accuracy on patient data alone. This model also minimized type 1 errors, which is ideal for these types of predictions:

![image](https://user-images.githubusercontent.com/72315132/151558199-0e12fd3a-9c2c-4dcf-9d06-adf9b6bd8867.png)


## Summary


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
