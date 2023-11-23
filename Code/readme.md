<a name='code'></a>
# Code 
This folder contains all the code that was produced during this project. 
Each file contains a cell at the end with references, if I used any when working in the respective file. 


<br>
## Folders

<br>
### ElsevierAPI
-  *ElsevierAPI.ipynb* is a Jupyter Notebook. It contains the code to download PDFs hosted on Elsevier's online website. 
- *config.json* is a configuration file that is used in *ElsevierAPI* to access and use Elsevier's API. 

<br>
### mlruns 
- This folder will be created upon running 'classifier_sciBERT_v2.ipynb'.

<br> 
### QA 
- *QA_manually_labeled_data.ipynb*
- *QA_URL_extraction.ipynb*

<br> 
### SciBERT_finetuned_manualData
- This folder will be created upon running 'classifier_sciBERT_v2.ipynb'.

<br>
### SciBERT_finetuned_SciRes 
- This folder will be created upon running 'classifier_sciBERT_v2.ipynb'. It will contain a sciBERT model finetuned on labeled data created by Zhao, Luo, Chong, Anqing, Xiaopeng (2019). A Context-based Framework for Modeling the Role and Function of On-line Resource Citations in Scientific Literature. Association for Computational Linguistics, pp. 5205-5214. DOI: 10.18653/v1/D19-1524. 


<br>
## Files
- *articles_groundtruth_v2.ipynb* is a Jupyter Notebook. It contains the exploration of 10 random NeuroImage articles. The results are stored in a file titled *articles_groundtruth.csv* in 'Data'. 
- *classifier_SciBERT_v2.ipynb* is a Jupyter Notebook. It contains the classification of sentences containing URLs into three categories (Material, Methods, Supplement) using a fine-tuned SciBERT model. Two models trained on different data are compared. Additionally, the URLs classified as Material are validated (the results are in 'Data/URLs_validated.csv' and 'Data/URLs_validated_comments.csv'). The results are in 'Data/classified_data.csv' and 'Data/material_URLs.csv'. 
- *datasets_v6.ipynb* is a Jupyter Notebook. It is an old file that contained both URL_Extraction and classifier_SciBERT_v2.ipynb.
- *OpenAlexAPI.ipynb* is a Jupyter Notebook. It contains the code to get the DOIs of the articles that were published in NeuroImage in 2022. 
- *URL_Extraction.ipynb* is a Jupyter Notebook. It contains the extraction of URLs and the sentences containing the URLs from all articles published in NeuroImage in 2022. The results are in 'Data/articles_all_urls.csv' and 'Data/articles_filtered_urls.csv'. 