# Thesis
This repository contains the code for my thesis on open neuroimaging datasets and dataset re-use.

## **Table of contents**
- [Objective](#objective)
- [Structure](#structure)
    - [Data](#data)
    - [Code](#code) 
    - [Legacy](#legacy]
    - [Weekly updates](#weeklyupdates) 
- [Installation](#installation)
- [Usage](#usage) 
- [References and credits](#referencesandcredits)

<br>
---
<br>

<a name='objective'></a>
# Objective

<br>
---
<br>

<a name='structure'></a>
# Structure

<a name='data'></a>
## Data 
This folder contains all the results produced during this project. 

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
### Files 
- *articles_groundtruth.csv*
- *articles_dataset_sections.csv*



<br>
<a name='code'></a>
## Code 
This folder contains all the code that was produced during this project. 


<br>
### Folders
- *ElsevierAPI*
    - *ElsevierAPI.ipynb* is a Jupyter Notebook. It contains the code to download PDFs hosted on Elsevier's online website. 
    - *config.json* is a configuration file that is used in *ElsevierAPI* to access and use Elsevier's API. 


<br>
### Files
- *articles_groundtruth_v2.ipynb* is a Jupyter Notebook. It contains the exploration of 10 random NeuroImage articles. The results are stored in a file titled *articles_groundtruth.csv* in 'Data'. 
- *datasets_v3.ipynb* is a Jupyter Notebook. 
- *OpenAlexAPI.ipynb* is a Jupyter Notebook. It contains the code to get the DOIs of the articles that were published in NeuroImage in 2022. 


<br>
<a name='legacy'></a>
## Legacy 
This folder contains previous versions of code files. Before making any major changes or edits in code files, I would always make a copy and store the old version in here, so I could easily find previous versions. 

<br>
<a name='weeklyupdates'></a>
## WeeklyUpdates 
This folder contains a file used throughout the project to describe and keep track of what I am working on and when. The format is implemented using Whitaker Lab Project Management (2023 [2017]). 


<br>
---
<br>

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

<br>
--
<br>

<a name='usage'></a>
# Usage 


<br>
---
<br>

<a name='referencesandcredits'></a>
# References and credits 
This project is done under the supervision of Veronika Cheplygina (IT University of Copenhagen). 

I used the following: 
- Akkoç, A. (2023). PublicDatasets [Jupyter Notebook]. https://github.com/madprogramer/PublicDatasets (Original work published 2022)
- Elsapy. (2023). [Python]. Elsevier Developers. https://github.com/ElsevierDev/elsapy (Original work published 2016)
- Elsevier B.V. (2023a). Article (Full Text) Retrieval API. Elsevier Developer Portal. https://dev.elsevier.com/documentation/ArticleRetrievalAPI.wadl#d1e52
- Elsevier B.V. (2023b). Article Metadata API. Elsevier Developer Portal. https://dev.elsevier.com/documentation/ArticleMetadataAPI.wadl
- Elsevier B.V. (2023c). ScienceDirect Article Metadata Guide. Elsevier Developer Portal. https://dev.elsevier.com/sd_article_meta_tips.html
- Elsevier B.V. (2023d). ScienceDirect Search API Migration. Elsevier Developer Portal. https://dev.elsevier.com/tecdoc_sdsearch_migration.html
- Lipovský, J. (2022). urlextract: Collects and extracts URLs from given text. (1.8.0) [Python]. https://github.com/lipoja/URLExtract
- NeuroImage | Journal | ScienceDirect.com by Elsevier. (n.d.). Retrieved September 17, 2023, from https://www.sciencedirect.com/journal/neuroimage
- OpenAlexAPI. (n.d.-a). Filter works. OpenAlex API Documentation. Retrieved September 14, 2023, from https://docs.openalex.org/api-entities/works/filter-works
- OpenAlexAPI. (n.d.-b). Search institutions. OpenAlex API Documentation. Retrieved September 14, 2023, from https://docs.openalex.org/api-entities/sources/source-object
- OpenAlexAPI. (n.d.-c). Sources. OpenAlex API Documentation. Retrieved September 17, 2023, from https://docs.openalex.org/api-entities/sources
- OpenAlexAPI. (n.d.-d). Work object. OpenAlex API Documentation. Retrieved September 17, 2023, from https://docs.openalex.org/api-entities/works/work-object#is_paratext
- Priem, J., Piwowar, H., & Orr, R. (2022). OpenAlex: A fully-open index of scholarly works, authors, venues, institutions, and concepts. ArXiv. https://arxiv.org/abs/2205.01833
- Sourget, T. (2023). TheoSourget/DDSA_Sourget: Repository used during my travel at the ITU of Copenhagen in March 2023 [Computer software]. https://github.com/TheoSourget/DDSA_Sourget
- Szucs, D., & Ioannidis, J. PA. (2020). Sample size evolution in neuroimaging research: An evaluation of highly-cited studies (1990–2012) and of latest practices (2017–2018) in high-impact journals. NeuroImage, 221, 117164. https://doi.org/10.1016/j.neuroimage.2020.117164
- Whitaker Lab Project Management. (2023). [Jupyter Notebook]. Whitaker Lab. https://github.com/WhitakerLab/WhitakerLabProjectManagement (Original work published 2017)