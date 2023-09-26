# Thesis
This repository contains the code for my thesis on open neuroimaging datasets and dataset re-use.

# Structure of the project

## Data 
### ElsevierAPI 
* *ElsevierAPI* is a Jupyter Notebook. It contains the code to download PDFs hosted on Elsevier's online website. 
* *config.json* is a configuration file that is used in *ElsevierAPI* to access and use Elsevier's API. 
* *downloadedPDFs_info.json* 
* *downloaded_pdfs* is a directory. It contains the PDFs for the 846 articles that were published in NeuroImage in 2022. 
    * *fulltext_articles_doi* is a directory. It contains the PDFs for the 815 research articles that were published in NeuroImage in 2022. The filename is the DOI of the research article. 
    * *fulltext_editorialboard_doi* is a directory. It contains the PDFs for the 19 articles titled 'Editorial board' that were published in NeuroImage in 2022. The filename is the DOI of the article. 

### OpenAlexAPI
* *OpenAlexAPI* is a Jupyter Notebook. It contains the code to get the DOIs of the articles that were published in NeuroImage in 2022. 
* *papers_fulltext* is a directory. It contains the attempted downloaded PDFs for the articles that were published in NeuroImage in 2022. 
    * *articles_pdf* is a directory. It contains the attempted downloaded PDFs for a small sample of research articles that were published in NeuroImage in 2022. However, these PDFs are broken. 
    * *paratext_pdf* is a directory. It was created to contain the PDFs for the articles titled 'Editorial board' published in NeuroImage in 2022. 


## Analysis 
List of the code-files with a brief description of what is in each of them. 


## WeeklyUpdates 
This folder contains a file used throughout the project to describe and keep track of what I am working on and when. The format is implemented using Whitaker Lab Project Management (2023 [2017]). 


# Credits 
This project is done under the supervision of Veronika Cheplygina (IT University of Copenhagen). 

I used the following tools and code: 
- Elsevier B.V. (2023a). Article (Full Text) Retrieval API. Elsevier Developer Portal. https://dev.elsevier.com/documentation/ArticleRetrievalAPI.wadl#d1e52
- Elsevier B.V. (2023b). Article Metadata API. Elsevier Developer Portal. https://dev.elsevier.com/documentation/ArticleMetadataAPI.wadl
- Elsevier B.V. (2023c). ScienceDirect Article Metadata Guide. Elsevier Developer Portal. https://dev.elsevier.com/sd_article_meta_tips.html
- Elsevier B.V. (2023d). ScienceDirect Search API Migration. Elsevier Developer Portal. https://dev.elsevier.com/tecdoc_sdsearch_migration.html
- OpenAlex: Priem, J., Piwowar, H., & Orr, R. (2022). OpenAlex: A fully-open index of scholarly works, authors, venues, institutions, and concepts. ArXiv. https://arxiv.org/abs/2205.01833
- Sourget, T. (2023). TheoSourget/DDSA_Sourget: Repository used during my travel at the ITU of Copenhagen in March 2023 [Computer software]. https://github.com/TheoSourget/DDSA_Sourget
- Whitaker Lab Project Management. (2023). [Jupyter Notebook]. Whitaker Lab. https://github.com/WhitakerLab/WhitakerLabProjectManagement (Original work published 2017)