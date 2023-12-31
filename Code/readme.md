<a name='code'></a>
# Code 
This folder contains all the code implemented and executed during this project. 
Each file contains a cell at the end with references if I used any when implementing the respective file. 

---

## Folders

### ElsevierAPI
This folder contains the code and configuration necessary to download the NeuroImage articles hosted on Elsevier. 
-  *ElsevierAPI.ipynb* is a Jupyter Notebook. It contains the code to download PDFs hosted on Elsevier's online website. 
- *config.json* is a configuration file used in *ElsevierAPI.ipynb* to access and use Elsevier's API. 

### mlruns 
This folder will be created upon running *Code/classifier_sciBERT_v2.ipynb*.

### QA 
This folder contains the files to perform the qualitative assurances of the URL extraction and the dataset labeling. 
- *QA_manually_labeled_data.ipynb*
- *QA_URL_extraction.ipynb*

### SciBERT_finetuned_manualData
This folder will be created upon running *Code/classifier_sciBERT_v2.ipynb*.

### SciBERT_finetuned_SciRes 
This folder will be created upon running *Code/classifier_sciBERT_v2.ipynb*. It will contain a sciBERT model finetuned on labeled data created by Zhao, Luo, Chong, Anqing, Xiaopeng (2019). A Context-based Framework for Modeling the Role and Function of On-line Resource Citations in Scientific Literature. Association for Computational Linguistics, pp. 5205-5214. DOI: 10.18653/v1/D19-1524. 

---

## Files
- *articles_groundtruth_v2.ipynb* is a Jupyter Notebook. It contains the exploration of 10 random NeuroImage articles. It generates *Data/articles_groundtruth.csv*. 
- *classifier_SciBERT_v2.ipynb* is a Jupyter Notebook. It contains the classification of sentences containing URLs into three categories (Material, Methods, Supplement) using a fine-tuned SciBERT model. Two models trained on different data are compared. The URLs classified as Material are also validated. It generates *Data/scibert_predictions.csv*, *Data/classified_data.csv*, *Data/URLs_validated.csv*, and *Data/material_URLs.csv*. 
- *reuse_NeuroImage.ipynb* is a Jupyter Notebook. It contains the exploration of the data URLs extracted from the NeuroImage articles. It also contains the exploration of the Human Connectome Projects URLs and their mentions in the articles hosted on OpenAlex. 
- *URL_Extraction.ipynb* is a Jupyter Notebook. It contains the extraction of URLs and the sentences containing the URLs from all articles published in NeuroImage in 2022. It generates *Data/articles_all_urls.csv*,  *Data/articles_filtered_urls.csv*, and *Data/articles_groundtruth_urls_and_sentences.csv*