# Thesis
This repository contains the code for my thesis on open neuroimaging datasets and dataset re-use.

## **Table of contents**
- [Objective](#objective)
- [Structure](#structure)
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
Each folder contains a readme.md that describes its contents. There are the following folders: 
- Data
- Code
- Legacy
- Resources
- Results
- Weekly updates 


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


- Code/articles_groundtruth_v2.ipynb (investigate a random sample of ten articles) 
- Code/ElsevierAPI/ElsevierAPI.ipynb (get the pdfs from NeuroImage 2022)
- Code/URL_extraction.ipynb (get the URLs and sentences from the articles)
- Code/classifier_SciBERT_v2.ipynb (classify the sentences to get all material/dataset URLs and validate them)
- Code/reuse 



<br>
---
<br>

<a name='referencesandcredits'></a>
# References and credits 
This project is done under the supervision of Veronika Cheplygina (IT University of Copenhagen). 

Each Jupyter Notebook in the **Code** folder contains a cell at the end titled *References', listing all the articles, webpages, software, etc., that were used (as inspiration, directly for implementation, or other) during the implementation of the given file. 