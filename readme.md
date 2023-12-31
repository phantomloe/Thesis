# Thesis
This repository contains the code for my thesis on dataset (re)use in neuroimaging titled: "Hyperlinking brains: An investigation of data (re)use through URLs in neuroimaging"

## **Table of contents**
- [Objective](#objective)
- [Structure](#structure)
- [Installation](#installation)
- [Usage](#usage) 
- [References and credits](#referencesandcredits)

---

<a name='objective'></a>
# Objective

In the past two decades, open science has become integral to collaborative and accessible scientific research. The gradual integration of machine learning methods in research has further influenced how researchers disseminate results and share data, particularly in neuroimaging. This study explores the landscape of URLs in NeuroImage papers from 2022, focusing on their patterns, contexts, and usage to unravel data use and reuse dynamics in neuroimaging. The findings reveal a high inclusion of URLs in the articles; however, only a minority link to data. While many data URLs are accessible, they often lead to repositories rather than specific datasets, creating ambiguity regarding dataset use. Recurring URLs and domains across the articles suggest an interconnected and standardized nature of sharing data within the NeuroImage publications.

---

<a name='structure'></a>
# Structure
Each of the following main folders contains a readme.md that describes its contents. This project contains the following folders: 
- Code
- Data
- Legacy
- Resources
- Results
- Weekly updates 

---

<a name='installation'></a>
# Installation 

1. Clone the project 
```console 
git clone https://github.com/phantomloe/Thesis.git  
```

2. Install requirements 
```console 
cd Thesis
pip3 install -r requirements.txt
```

---

<a name='usage'></a>
# Usage 

## Get the NeuroImage articles 
- Execute *Code/ElsevierAPI/ElsevierAPI.ipynb* to download all articles published in NeuroImage in 2022 and put them in Data/ElsevierAPI/downloaded_pdfs/fulltext_articles_doi and ../fulltext_editorialboard_doi
    - NB. This file can only be executed if the user has an API key and an institution token. Neither of these are provided with this project, as it would break Elsevier's terms and conditions. 

## Make the extraction 
- Execute *Code/URL_extraction.ipynb* to get the URLs and sentences from the articles and to generate the Data/articles_all_urls.csv and ../articles_filtered_urls.csv. 
- Execute *Code/QA/QA_URL_extraction_v2.ipynb* to see the performance of the code compared to the baseline (established by me) and an extractor. 

## Make the classification 
- Execute *Code/classifier_SciBERT_v2.ipynb* to fine-tune and compare classifiers, as well as classify the sentences to get all dataset URLs and validate them to generate Data/scibert_predictions.csv (this contains all predictions), Data/classified_data.csv (this contains the filtered predictions, where the URLs have been cleaned for subsequent validation of reachability), Data/URLs_validated.csv (this contains the automatically reachable URLs), and Data/material_URLs.csv (this contains the automatically and manually validated data URLs)
    - The file Data/URLs_validated_comments.csv was created by manually editing Data/URLs_validated.csv to create Data/material_URLs.csv.

## Make the analysis 
- Execute *Code/articles_groundtruth_v2.ipynb* to investigate a sample of ten randomly selected NeuroImage articles.
- Execute *Code/reuse_NeuroImage.ipynb* to investigate the extent of (re)use among the NeuroImage articles, focusing on the common data URLs, the common domains, as well as a deep-dive into the HCPs URLs, including a look into the articles available through OpenAlex that also includes the HCPs URLs.  

---

<a name='referencesandcredits'></a>
# References and credits 
This project is done under the supervision of Veronika Cheplygina (IT University of Copenhagen). 

Each Jupyter Notebook in the **Code** folder contains a cell at the end titled *References*, where all the articles, webpages, software, etc., that were used (as inspiration, for implementation, or other) during the implementation of the given file are listed. 