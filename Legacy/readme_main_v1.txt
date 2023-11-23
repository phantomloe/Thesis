<a name='data'></a>
## Data 
This folder contains the results produced during this project. 

<br>
### Folders 


<br>
#### ElsevierAPI 
* *downloadedPDFs_info.json* is a json file that contains the DOIs and titles of the articles (called 'article_names'). 
* (NB! NOT ON GITHUB) *downloaded_pdfs* is a directory. It contains the PDFs for the 846 articles that were published in NeuroImage in 2022. 
    * *fulltext_articles_doi* is a directory. It contains the PDFs for the 815 research articles that were published in NeuroImage in 2022. The filename is the DOI of the research article. 
    * *fulltext_editorialboard_doi* is a directory. It contains the PDFs for the 19 articles titled 'Editorial board' that were published in NeuroImage in 2022. The filename is the DOI of the article. 


<br>
#### OpenAlexAPI
* *papers_fulltext* is a directory. It contains the attempted downloaded PDFs for the articles that were published in NeuroImage in 2022. 
    * *articles_pdf* is a directory. It contains the attempted downloaded PDFs for a small sample of research articles that were published in NeuroImage in 2022. However, these PDFs are broken. 
    * *paratext_pdf* is a directory. It was created to contain the PDFs for the articles titled 'Editorial board' published in NeuroImage in 2022. 

<br>
#### QA_manually_labeled_data
* *AnonymousAxololt.docx* is a document containing the labeled sentences performed by one of the annotators. 
* *AnonymousPlatypus.docx* is a document containing the labeled sentences performed by one of the annotators. 
* *AnonymousQuokka.docx* is a document containing the labeled sentences performed by one of the annotators. 
* *articles_sentences_to_be_labeled.txt* is a .txt file that was used on Taguette for the manual labeling. 
* *labeled_data.csv* is a csv-file containing the results from the code in *Code/QA/QA_manually_labeled_data.ipynb*. There are 129 labeled sentences. 
* *DOI_forty.csv* is a csv-file containing the DOIs of the articles whose URLs and sentences were used for manual labeling. 

<br>
#### QA_URL_extraction 
* *together.csv* is a file containing the DOI, URL, and sentences found by CVL and the external extractor in two articles. 
* *groundtruth.csv* is a file containing the manually extracted DOI, URL, and sentences in ten articles. This was performed by CVL. 
* *extractor1.csv* is a file containing the manually extracted DOI, URL, and sentences in ten articles. This was performed by an external extractor.  


<br>
### Files 
- *articles_groundtruth.csv*
- *articles_groundtruth_urls_and_sentences.csv*
- *articles_all_urls.csv* contains the URL, Sentences, and DOI from the articles published in NeruoImage 2022 without any URLs filtered out. 
- *articles_filtered_urls.csv*  contains the URL, Sentences, and DOI from the articles published in NeruoImage 2022 with some URLs filtered out (described in *Code/URL_Extraction.ipynb*. 



<br>
<a name='code'></a>
## Code 
This folder contains all the code that was produced during this project. 


<br>
### Folders

<br>
#### ElsevierAPI
-  *ElsevierAPI.ipynb* is a Jupyter Notebook. It contains the code to download PDFs hosted on Elsevier's online website. 
- *config.json* is a configuration file that is used in *ElsevierAPI* to access and use Elsevier's API. 

<br>
#### mlruns 

<br> 
#### QA 
- *QA_manually_labeled_data.ipynb*
- *QA_URL_extraction.ipynb*

<br> 
#### SciBERT_finetuned_manualData

<br>
#### SciBERT_finetuned_SciRes 


<br>
### Files
- *articles_groundtruth_v2.ipynb* is a Jupyter Notebook. It contains the exploration of 10 random NeuroImage articles. The results are stored in a file titled *articles_groundtruth.csv* in 'Data'. 
- *Classifier_SciBERT.ipynb* is a Jupyter Notebook. 
- *datasets_v6.ipynb*
- *OpenAlexAPI.ipynb* is a Jupyter Notebook. It contains the code to get the DOIs of the articles that were published in NeuroImage in 2022. 
- *URL_Extraction.ipynb* 


<br>
<a name='legacy'></a>
## Legacy 
This folder contains previous versions of code files. Before making any major changes or edits in code files, I would always make a copy and store the old version in here, so I could easily find previous versions. 

<br> 
<a name='resources'></a>
## Resources 
This folder contains (...). 

Files: 
- *LabelingGuide.pdf* 

<br>
<a name='weeklyupdates'></a>
## WeeklyUpdates 
This folder contains a file used throughout the project to describe and keep track of what I am working on and when. The format is implemented using Whitaker Lab Project Management (2023 [2017]). 

