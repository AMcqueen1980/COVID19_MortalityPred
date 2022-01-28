# COVID19 Mortality Prediction Project

The COVID19 pandemic has devastated the world, leaving over 5.1 million people dead since it's first appearance in 2019. The primary cause of death is a buildup of fluid in the lungs, resulting in suffocation. Diagnosis occurs via PCR tests, and disease prognosis is indicated by various patient features and chest X-rays. This project seeks to determine if we can take various sources of patient data (vitals, protein levels, etc) in addtion to X-ray images, and determine if we can predict the likelihood of patient mortality. Being able to make such predictions would allow medical practioners to allocate resources to high risk patients and lessen the burden on an already strained healthcare infrastructure.

## Data Sources
Data taken from: https://www.kaggle.com/toxite/covid-19-cxr-ny-sbu

Data was curated from: https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=89096912#89096912bcab02c187174a288dbcbf95d26179e8

Patient Chest X-Rays and metadata were used from COVID19 positive patients at Stony Brook University medical center in Stony Brook, NY.


## Repository Structure

```
├── README.md                           <- The top-level README for reviewers of this project
├── Final_notebook.ipynb                <- Final notebook with cleaned data used for final predictions and classification
├── Final_Notebook_2.ipynb              <- Final analysis in Jupyter notebook
├── Presentation.pdf                    <- PDF version of project presentation
└── Data                                <- Cleaned data generated from code. Images and unmodified data available for download via the Kaggle link
```
