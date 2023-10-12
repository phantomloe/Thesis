# Weekly logs 
- [Week 41](#week41)
- [Week 40](#week40)
- [Week 39](#week39
- [Week 38](#week38)
- [Week 37](#week37) 
- [Week 36](#week36)
- [Week 35](#week35)

<a name='week41'></a>
# Week 41 

I was sick for the entire duration of week 41 with a painful stomach flu, so I did not do any work. 

******************************For next time******************************
- Extract and process all URLs from the articles. 
- Plan the exploration of dataset reuse using OpenAlex 


<a name='week40'></a>
# Week 40 

**What did you achieve?**
- I added a 10th article to my groundtruth sample ('Code/articles_groundtruth_v2.ipynb' and 'articles_groundtruth.csv')
- I worked in 'Code/datasets_v2.ipynb', but I don't feel like I got very far. 

**What did you struggle with?**
- Extracting the datasets (URLs and capitalized words, e.g., 'Human Connectome Project') from the text sections. 
    - I've been working on writing regex expressions to split text sections into sentences, extract capitalized words, and URLs - the expressions work well with the groundtruth sample now, but scrolling through the extracted text for other articles, I can see it is not working properly. Late Thursday, I decided to see if there exist any libraries I can use, and I found one called 'urlextract' (https://pypi.org/project/urlextract/) that I will try Friday. 
- Personal issues. 

**What would you like to work on next week?**
- Extracting the datasets from the text sections that match the 'availability' pattern. 
    - Group the sentences that mention 
        - **data**, e.g., data(base, set), image(s), (neuro)map(s), DOI(s), atlas, (freely available)
        - **code**, e.g., Code, code(s)
        - **other**, e.g., tool(kit, box), scripts, results, algorithm, software, package, plugin, function, analysis 
    - Separate the articles without any URLs or capitalized words or mentions of **data** that instead make mentions of 'request' (or similar).      
- Make a plan for investigating the reuse of the datasets I extract 

**Where do you need help from Veronika?**
- I'm not really sure. I'm not sure if I've approached this problem properly, or if I just need to sit with it for longer and explore different possible solutions. 

******************************For next time******************************
- The goal for week 41 and 42: 
    - Draft for introduction, state-of-the-art, and the methodology (what I can currently put down) 


<a name='week39'></a>
# Week 39

**What did you achieve?**
- I finalized my initial exploration of the random sample of papers and put the ground truth into a csv file (see data/articles_groundtruth.csv and code/articles_groundtruth.ipynb)
- I extracted the text sections from all articles that should contain the dataset(s) (or information about the dataset(s)) used in the article. The majority (500+/834) of the text sections are pulled from a 'Data availability' (or similar title) section in the articles, and I'm going to start extracting the datasets from these texts. 

**What did you struggle with?**
- Finalizing the code for the text extraction - I'm unsure if I've picked the proper way to do it. 
- Figuring out how to extract the datasets from the text sections. 

**What would you like to work on next week?**
- Extracting the datasets from the text sections - preferably, I'll have the datasets from the 500+ articles. 

**Where do you need help from Veronika?**
- Regarding the type of research paper 
    - I'm unsure if the studies that are reviewed in this paper (https://doi.org/10.1016/j.neuroimage.2022.119646) should be considered and counted as a dataset or not. As of now, I included all 12 studies as datasets, but I don't think they should be considered as such, especially since the authors write in the "Data & Code Availability" section: "Not applicable."
    - I think that review or commentary (or similar) articles are different from articles that analyse data, build models, hypothesize etc., and I feel that the distinction is important for my assignment, as I'm focusing on dataset re-use. When extracting the datasets from the random sample of articles (see data/articles_groundtruth.csv and code/articles_groundtruth.ipynb), a large number of the extractions are not datasets per se, but articles used for analysis (10.1016/j.neuroimage.2022.119646 analyses articles whereas 10.1016/j.neuroimage.2022.119443 analyses and links datasets) - but I don't know how and where to draw the line. 
- Where can I share the articles I've downloaded with you?
- Proper plan for extracting the datasets from the text sections. 

**What are the agreements after this meeting?** (to fill in after the meeting)
- Plan annotation scheme - Veronika and Amelia can help annotate and classify documents and extract datasets based on my scheme. 
- Rework 'articles_groundtruth.ipynb' 
    - Check if the datasets from the sample set are all correct.  
    - Classify the dataset usage (is it being presented? used in an experiement? discussed or analysed? mentioned as an example? other?) 

******************************For next time******************************
- Annotation scheme 
- Continue working on extracting the datasets from the text sections 
- Classify the documents? 


<a name='week38'> </a>
# Week 38
**What helped you this week?**
- The git repositories from Veronika's previous students! Seeing how they approached downloading the PDFs, reading the PDFs, and getting text from the PDFs has been immensely helpful. 
    - Akkoç, A. (2023). PublicDatasets [Jupyter Notebook]. https://github.com/madprogramer/PublicDatasets (Original work published 2022)
    - Sourget, T. (2023). TheoSourget/DDSA_Sourget: Repository used during my travel at the ITU of Copenhagen in March 2023 [Computer software]. https://github.com/TheoSourget/DDSA_Sourget

**What did you achieve?**
- I downloaded all articles published in NeuroImage 2022. 
    - I tried using OpenAlex first, but the PDFs were corrupted upon downloading (see git: Data/OpenAlexAPI). 
    - The Institution token that I was given from Elsevier seems to have been the key to giving me access to using their API, so I've downloaded the papers using it (see git: Data/ElsevierAPI.  
- I have started the process of extracting the datasets from the articles. I'm currently working on step 2 (see git: Data/Datasets.ipynb). 
    - Step 1: Understand which section might mention the dataset. 
    - Step 2: Isolate the section and extract the text (and make sure this isolation works properly). 
    - Step 3: Isolate the dataset within the section 
        - Some only mention the title and others mention both title and have a link. Sometimes, there are multiple links, not all of which point to the code. 

**What did you struggle with?**
- Writing the code (figuring on how to read the PDF, get text sections from the PDF - getting the right section that hopefully contains a mention of the dataset)
- I feel like I've fallen behind, and I'm afraid to find out that that's true. 
    - I've not yet written anything for the report itself yet, which is stressing me out. I have taken notes for the methodology section of what I've done so far, and I have taken notes for all the texts I've read and made some considerations regarding what's important to mention, but nothing is on paper yet. 

**What would you like to work on next week?**
- Continuing - and preferably finishing - the extraction of the datasets from the articles. 
- Settling on a strategy for the next step of tracking how many research papers have used the datasets used in the NeuroImaging articles. 

**Where do you need help from Veronika?**
- I have a couple of methodological questions and issues that arose this week: 
    - One of the random articles I skimmed ( to investigate where they mention the datasets) was not actually OA, despite Elsevier mentioning that NeuroImage is OA (I opened it in another browser, and I could only read the abstract and references). 
    - QUESTION: How do we treat reviews that summarizes data but does not contain new data? Is the reuse of a dataset not also the same as not containing new data?
        - In 10.1016/j.neuroimage.2022.119110, it says: "The review summarizes data but does not contain new data." - other reviews might mention the datasets they reviewed in a 'Data availability statement', so how do I approach this? 

**What are the agreements after this meeting?** (to fill in after the meeting)
- Implement a way to test and validate my methods and approach 
    - Have someone else test my criteria and results 
- Think of a way to categorize the papers based on how they work with the data 
    - Present datasets
    - Use datasets in reviews
    - Use datasets for modeling 
    - Is a dataset mentioned for a different reason? 
    - Etc.
- Deepen understanding of how the datasets are referenced in the articles - this is closely tied to the idea of using my work on articles from other journals. 

******************************For next time******************************
- Continue work on extracting the datasets from the articles 
- Study the repository and take note of the csv's: Sourget, T. (2023). TheoSourget/DDSA_Sourget: Repository used during my travel at the ITU of Copenhagen in March 2023 [Computer software]. https://github.com/TheoSourget/DDSA_Sourget


<a name='week37'> </a>
# Week 37 
**What helped you this week?**
- ChatGPT helped me explore lots of different pieces of code to try and extract the articles from NeuroImage.

**What did you achieve?**
- So far, I’ve only performed a lot of unsuccessful experiments, using Scrapy and Elsevier's API - none of which has lead me to get the metadata from the 2022 articles. 

**What did you struggle with?**
- My primary focus has been on gathering a comprehensive list of NeuroImage articles published in 2022. I initially attempted to obtain this data from the Elsevier website, where the papers are openly accessible available. Unfortunately, the website cannot be scraped using Scrapy. While looking for other alternatives, I found that Elsevier has numerous APIs freely available for non-commercial use. I generated an API key for this purpose, however, I have not been able to establish communication with Science Direct through the generated API key. I wrote to Elsevier's support team today, and the automated response says they'll be back within 24 hours.

**What would you like to work on next week?**
- My initial plan was to compile all the 2022 papers by this Friday, so that I can extract the datasets from the papers in an automated manner next week. 
- During next week, I also need to come up with a plan for how to find all the articles that have used the public datasets that are mentioned in the NeuroImage articles. 

**Where do you need help from Veronika?**
- I need some guidance regarding extracting the datasets from the papers in an automated manner.
- However, if the API-related issues have not been solved by Friday, I would like to talk with you about alternative approaches (e.g., downloading the relevant issues manually and subsequently extracting the datasets).

**What are the agreements after this meeting?** (to fill in after the meeting)
- Get a minimum solution working with the pdf's I can get from OpenAlex 
    - Look through and use Théo's code to download the pdf's from OpenAlex 
- In parallel to OpenAlex, try and get any missing papers from Elseviser (using their API) 
- Go through some papers to build an understanding of how the datasets are referenced in the papers 
- For the dataset extraction be mindful of 
    - Where is the dataset mentioned (abstract, figure text, in-text, elsewhere) - see point above 
    - Is the dataset actually used for analysis or is it just mentioned? 
    - NB! Whatever code I end up writing may not pick up on all datasets - mention this as a weakness! 

******************************For next time******************************
- Continue working on state of the art
- All articles downloaded (preferably) 
- Code begun for the dataset extraction 


<a name='week36'> </a>
# Week 36 
**What helped you this week?**
- Veronika really helped a lot by sending a proposal by email on how to narrow in the scope. Her suggestion on investigating tools/software to make dataset reviews live outside of the published papers is an excellent idea, and I think it could be a good project.

**What did you achieve?**
- I read a lot of papers to find a way to narrow down the scope of my thesis.
- I think I’ve discovered the more narrow direction of the thesis (i.e. data re-use)

**What did you struggle with?**
- Taking proper notes for the texts, so that I can more easily write the state-of-the-art later on.
- Finding a way to narrow the scope of the project.

**What would you like to work on next week?**
- It would be nice to do two things
    - Start writing state-of-the-art (as I’ve read a lot that’ll go in there)
    - I’m going to pull all the papers published in NeuroImage from 2022 and hopefully extract all the different datasets that are mentioned.
        - Right now, I’m not sure if I can figure out a way to automate this, or if I need to search the papers manually (which is most likely the case), but we’ll see.

**Where do you need help from Veronika?**
- Narrowing down, settling on the direction for the project, and pointing me to where I can start gathering data.
    - Going forward with the current direction of data re-use, it’s important that my project isn’t too small.

**What are the agreements after this meeting?** (to fill in after the meeting)
- I’m going to pull the papers from NeuroImage published in 2022.
    - Of the four journals that Szucs & Ioannidis (2020) investigated in their article (Nature Neuroscience, The Journal of Neuroscience, NeuroImage, and Cerebral Cortex) for the years 2017 and 2018, Veronika suggested that I start with NeuroImage, as editors from NeuroImage and NeuroImage: Reports decided to resign from their collaboration with Elsevier and start a new journal hosted by MIT Press as a response to high article-processing changes (Sanderson 2023). NeuroImage was also the journal with the highest number of occurrences in the papers gathered by Szucs & Ioannidis.
        - Szucs, D., & Ioannidis, J. PA. (2020). Sample size evolution in neuroimaging research: An evaluation of highly-cited studies (1990–2012) and of latest practices (2017–2018) in high-impact journals. *NeuroImage*, *221*, 117164. https://doi.org/10.1016/j.neuroimage.2020.117164
        - Sanderson, K. (2023). Editors quit top neuroscience journal to protest against open-access charges. *Nature*, *616*(7958), 641–641. https://doi.org/10.1038/d41586-023-01391-5
- Look into [Taguette](https://www.taguette.org/about.html) (this is a tool for performing qualitative research alá NVIVO)

******************************For next time******************************
- Draft for state of the art has begun
- Draft for methodology has begun
- Journals from NeuroImage 2022 has been pulled - preferably the datasets have been located and listed as well.

<a name='week35'></a>
# Week 35 
**What helped you this week?**
- I asked everyone in my life what project to pick.
- 10-hour sound of rain videos on YouTube.

**What did you achieve?**
- I picked a project and a supervisor.
- I found lots of literature, and started reading and taking notes.
- I got both Notion and Obsidian set up.

**What did you struggle with?**
- Picking a project.
- Mentally preparing for narrowing down the project and finding the right problem to solve with the project.
- Finding literature.

**What would you like to work on next week?**
- Finish reading most of the papers and start organising my notes, so I can plan writing the state of the art.
- Finding and settling on the right angle for the project (narrowing it down).
    - This depends on the literature.

**Where do you need help from Veronika?**
- Figuring out how to make sure the project is of the appropriate size and difficulty. I am very insecure and worried about that.

**What are the agreements after this meeting?** (to fill in after the meeting)
- Figure out how to narrow the scope.
    - Find more overview papers on neuroimaging - what are their key points?
        - What do they say are common?
        - What are the gaps?
        - What do they say about the datasets?
        - What datasets are used to explain, to observe - how are they used?
            - Relate to concept of *burden of disease versus life satisfaction*.
    - Focus on ‘dataset decay’ (mentioned in both Horien and Madan texts)
        - Dataset decay: Thompson, W.H., Wright, J., Bissett, P.G., Poldrack, R.A. (2020). Dataset decay and the problem of sequential analyses on open datasets. eLife, 9, 53498. https://doi.org/10.7554/elife.53498.
            - See how some datasets are used. That makes the search space smaller.
    - Assigning credit to scientific datasets using article citation networks
    - https://grand-challenge.org/
        - See neuroimaging datasets here - they might be underrepresented.
- Comment on: collecting neuroimaging data is more difficult - there’d be more efforts across countries to collaborate because there are fewer scanners. for dermatology, it’s simpler. For chest x-rays, it’s probably in between.
- NB! Distinction between data banks and datasets extracted from banks - some datasets contain images from a larger study.

******************************For next time******************************

Scientific publications - measure of what people research versus what people die from. 
Neuroimaging - are the modalities used for ML representative of MRI CT scans that are done worldwide. 
Finding the datasets 
- Outset in the two papers I found and start with a list of those
- As Wen et al.: using google datasets, medline
- As your previous student: using OpenAlex
- Other?


---------------------------------------------------------------------------------

<a name='weekXX'> </a>
# Week XX
**What helped you this week?**
- 

**What did you achieve?**
- 

**What did you struggle with?**
- 

**What would you like to work on next week?**
- 

**Where do you need help from Veronika?**
- 

**What are the agreements after this meeting?** (to fill in after the meeting)
- 

******************************For next time******************************
- 
