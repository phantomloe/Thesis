# Weekly logs 
- [Week 49-52](#week49-52)
- [Week 48](#week48)
- [Week 47](#week47)
- [Week 46](#week46)
- [Week 45](#week45)
- [Week 44](#week44)
- [Week 43](#week43)
- [Week 42](#week42)
- [Week 41](#week41)
- [Week 40](#week40)
- [Week 39](#week39)
- [Week 38](#week38)
- [Week 37](#week37) 
- [Week 36](#week36)
- [Week 35](#week35)

<a name='week49-52'></a>
*During weeks 49-52 I did not produce weekly updates*.

<a name='week48'></a>
# Week 48
**What helped you this week?**
- N/A

**What did you achieve?**
- I generated graphs for the results/findings portion of the report.
- I wrote the code for mentions of URLs in the articles on OpenAlex
    - I started with and completed the investigation of mentions of HCPs URLs.
    - I attempted to run the code with all of the material URLs found in the NeuroImage articles, but after running the code for two days, I decided to stop it.
- Wrote on the report. 

**What did you struggle with?**
- Writing, as it takes time.

**What would you like to work on next week?**
- Finish and send a draft for introduction, related work, methodology, and results on the 10th. 

**Where do you need help from Veronika?**
- N/A

**What are the agreements after this meeting?** (to fill in after the meeting)
- N/A

******************************For next time******************************
- Finish and send a draft for introduction, related work, methodology, and results on the 10th. 


<a name='week47'></a>
# Week 47 
**What helped you this week?**
- N/A

**What did you achieve?**
- I did a more proper and fair comparison of the fine-tuned SciBERT models (classifier_SciBERT.ipynb)
    - The models performed fairly similarly, with the model fine-tuned using Zhao et al.'s (2019) data performing better (it had a higher recall)
    - The model trained on my data achieved perfect precision and recall scores, which leads me to think it has overfitted.
- I checked the validity of the URLs (classifier_SciBERT.ipynb)
    - For the URLs that did not pass the automatic check, I manually checked them (121 total)
        - I added the URLs that work when manually copying and pasting them into a browser to the list of valid URLs
        - Some URLs that contained a word or character that looked to have been added during the url_extraction, I removed that which had been added to see if the link worked - if it did, I added it to the list (URLs_validated_comments.csv)
- I generated graphs for the groundtruth, URL, and both QA investigations which I forgot to do. 
- I began looking into the reuse (reuse.ipynb)
    - Looking at the NeuroImage 2022 articles, there were some articles that linked to the same datasets
    - The most common URL was a false material URL as it was a link to a piece of software - in the fifteen most common URLs, there were two false hits
    - Among the fifteen most common URLs, some point to the same datasets - and some are not so easily decipherable
        - The most common material URL is 'humanconnectome.org'; a website that hosts multiple HCP datasets (as there are multiple human connectome projects) 


**What did you struggle with?**
- Concerns relating to investigating reuse of datasets (reuse.ipynb)
    - Based on the validated material URLs, I can see that:
        - Some of the websites contain the same datasets (e.g., 'humanconnectome.org' and 'db.humanconnectome.org' both host the Healthy Adult HCP datasets)
        - Some of the URLs do not specify which dataset from the website they worked with (e.g., 'humanconnectome.org')
    - There are 305 unique material URLs that work - some of the URLs link to data repositories and not single datasets, and some are false hits (i.e., the classifier has mistakenly identified some software and other tool URLs as material) 
        - Do I create an overview of the datasets contained within those URLs? Or is it fine to analyse the URLs, e.g., top fifteen and see how many link to the same datasets, and how some researchers specify which dataset from a repository they use and others don't? 
    - I have started working on the code where I search the articles on OpenAlex that has fulltext available for the validated material URLs. 


**What would you like to work on next week?**
- Finish the reuse investigation and start working solely on the report. 


**Where do you need help from Veronika?**
- Coming up with a solution regarding the things I've been struggling with (see above) 


**What are the agreements after this meeting?** (to fill in after the meeting)
- Make a more qualitative investigation of the articles that use HCP (there are different URLs, all of them among the most reused)
    - Investigate the sentences; do they specify which HCP they use? Whom among the subjects they analyse? 

******************************For next time******************************
- Continue analysis and complete code. 


<a name='week46'></a>
# Week 46 
**What helped you this week?**
- The paper by Cao et al. proved to be very useful - they fine-tuned SciBERT using a dataset curated by Zhao et al. (2019) containing URLs and their contexts (i.e., sentences) that would classify sentences as either 'Material', 'Method' or 'Supplement'. 
    - The code accompanying their paper was also very useful; I followed their code to a large extent when fine-tuning SciBERT on Zhao et al.'s (2019) labeled data (caohanch n.d.). 

**What did you achieve?**
- I spent half of the week fine-tuning SciBERT on two sets of data 
    - The manually labeled data
    - The data curated and labeled by Zhao et al. (2019)
    - Overall, using the data by Zhao et al. (2019) resulted in a better performance on the test set compared to the model trained on my small labeled dataset. The size definitely affects the performance, and I remember reading somewhere that having more labels can make classification difficult, because you need more examples. 
- I spent the other half of the week writing the report 

**What did you struggle with?**
- Fine-tuning SciBERT for multi-label text classification was quite tricky
- Figuring out how to get the predicted classes for my dataset proved to be more difficult for me to wrap my head around than anticipated because both notebooks I read for reference inferred on a single sentence.
    - https://huggingface.co/docs/transformers/tasks/sequence_classification#inference
    - https://colab.research.google.com/github/NielsRogge/Transformers-Tutorials/blob/master/BERT/Fine_tuning_BERT_(and_friends)_for_multi_label_text_classification.ipynb#scrollTo=mEkAQleMMT0k

**What would you like to work on next week?**
- I want to work on the code to investigate the reuse of the datasets I've extracted from the NeuroImage articles.
- Continue writing. 

**Where do you need help from Veronika?**
- N/A

**What are the agreements after this meeting?** (to fill in after the meeting)
- Aggregate my labels to match the labels from Zhao et al. (2019) for a fair comparison of the model performance upon fine-tuning
    - Then I can see how much it influences to have more data
- Continue cleaning and checking the URLs to establish the dataset of datasets that I can find on OpenAlex. 

******************************For next time******************************
- Use OpenAlex to see how many other articles have used the datasets.
    - Read https://github.com/TheoSourget/Public_Medical_Datasets_References/blob/main/Code/usage_detection/fulltext_detection.py (Theó's work) 
    - Read https://github.com/TheoSourget/pdf_utilities (Theó's work) 

**References**
- Cao, H., Dodge, J., Lo, K., McFarland, D. A., & Wang, L. L. (2023). The Rise of Open Science: Tracking the Evolution and Perceived Value of Data and Methods Link-Sharing Practices. https://arxiv.org/ftp/arxiv/papers/2310/2310.03193.pdf
- caohanch. (n.d.). Paper_data_method_sharing/link_classification.ipynb at main · caohanch/paper_data_method_sharing [Jupyter Notebook]. Retrieved November 15, 2023, from https://github.com/caohanch/paper_data_method_sharing/blob/main/link_classification.ipynb
- Zhao, H., Luo, Z., Feng, C., Zheng, A., & Liu, X. (2019). A Context-based Framework for Modeling the Role and Function of On-line Resource Citations in Scientific Literature. Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing (EMNLP-IJCNLP), 5205–5214. https://doi.org/10.18653/v1/D19-1524


<a name='week45'></a>
# Week 45
**What helped you this week?**
- N/A

**What did you achieve?**
- I investigated the inter-annotator agreement (in Code/QA/QA_manually_labeled_data.ipynb)
    - I used NLTK to calculate Fleiss' Kappa and Krippendorf's Alpha
    - I investigated the labels that were not similar among the annotators
    - I compiled a labeled_data set, which consists of sentences with labels 2 or more annotators agreed on that will be used to fine-tune SciBert. 
- I began the process of fine-tuning Sci-BERT using the following: https://colab.research.google.com/github/NielsRogge/Transformers-Tutorials/blob/master/BERT/Fine_tuning_BERT_(and_friends)_for_multi_label_text_classification.ipynb#scrollTo=kLB3I4FKZ5Lr
- I started writing a bit on the report. 

**What did you struggle with?**
- I got two wisdom teeth removed early on Tuesday, which made my workdays a bit difficult to get through. 

**What would you like to work on next week?**
- Finalizing the list of datasets based on the sentences that are labeled with 'dataset'. 

**Where do you need help from Veronika?**
- The article cc'ed to me by Cao et al. seemed really relevant, so I will read it. 

**What are the agreements after this meeting?** (to fill in after the meeting)
- Continue working 

******************************For next time******************************
- Read Cao, H., Dodge, J., Lo, K., McFarland, D. A., & Wang, L. L. (2023). The Rise of Open Science: Tracking the Evolution and Perceived Value of Data and Methods Link-Sharing Practices. https://arxiv.org/ftp/arxiv/papers/2310/2310.03193.pdf


<a name='week44'></a>
# Week 44

**What helped you this week?**
- My friend helped manually extract URLs and sentences from ten research papers for my quality control ('Data/URL_extraction_QA/extractor1.csv' and 'Data/URL_extraction_QA/together.csv').
- My supervisor and Théo Sourget helped manually label sentences from 40 research articles for fine-tuning the SciBERT model.

**What did you achieve?**
- I extracted URLs and sentences from ten research papers. 
- I manually labeled the sentences from 40 research articles.
- I wrote and completed the QA of the URL extraction ('Code/URL_extraction_QA.ipynb')

**What did you struggle with?**
- Figuring out how to properly investigate the URL extractions. 

**What would you like to work on next week?**
- Investigate the inter-annotator agreement for the labeling.
- Fine-tune Sci-BERT with the labeled data.
    - For all sentences, if the annotators disagreed on the label, I will pick the label that most annotators picked. If they picked three different labels, but two labels belong to the same label group, I will pick a random label from that label group. If they picked labels from all different label groups, I will pick a random label.
- Generate a csv of the datasets used in NeuroImage that are referenced with URLs. 

**Where do you need help from Veronika?**
- How do I investigate the inter-annotator agreement for the labeling?
    - Cohen’s kappa can only compare two labelers, not three or more.

**What are the agreements after this meeting?** (to fill in after the meeting)
- Work with the inter-annotator agreement investigation once the data is in. 

******************************For next time******************************
- Inter-annotator agreement investigation is done. 
- Clean the datasets (as they are going to be used for searching using OpenAlex API)



<a name='week43'> </a>
# Week 43
**What helped you this week?**
- The following two guides helped me figure out how to fine-tune SciBERT:
  - https://medium.com/mlearning-ai/fine-tuning-bert-for-tweets-classification-ft-hugging-face-8afebadd5dbf
  - https://huggingface.co/docs/transformers/tasks/sequence_classification

**What did you achieve?**
- I completed a labeling guide that two coders will be using to manually label a small portion of my data.
- I implemented the code for the fine-tuning of SciBERT using the following two guides:
    - https://medium.com/mlearning-ai/fine-tuning-bert-for-tweets-classification-ft-hugging-face-8afebadd5dbf
    - https://huggingface.co/docs/transformers/tasks/sequence_classification

**What did you struggle with?**
- Writing the labeling guide; defining all of the labels properly, finding proper examples

**What would you like to work on next week?**
- Start the manual work that needs to be done for quality assurance
    - Manually extract URLs and sentences
    - Manually label extracted URLs and sentences 

**Where do you need help from Veronika?**
- I've found a pre-trained model called *Sci-BERT* that's trained on scientific articles (Beltagy et al. 2019), and it seems like it's a fair strategy to fine-tune such a model to my task of classifying sentences (Han et et al. 2021).
    - To fine-tune the model, I need labeled data. 

**What are the agreements after this meeting?** (to fill in after the meeting)
- Write a labeling guide for the two coders who will help me manually data.
- Read Geiger, R. S., Cope, D., Ip, J., Lotosh, M., Shah, A., Weng, J., & Tang, R. (2021). “Garbage In, Garbage Out” Revisited: What Do Machine Learning Application Papers Report About Human-Labeled Training Data? Quantitative Science Studies, 2(3), 795–827. https://doi.org/10.1162/qss_a_00144
- Explore Taguette (Rampin & Rampin 2021) for annotating the sentences containing URLs, using labels (to be presented in the labeling guide). 

******************************For next time******************************
- Manual extraction of URLs has been started and completed. 
- Manual labeling of data has started.
- Quality assurance of manual extraction of URLs completed.
- Quality assurance of the fine-tuned Sci-BERT started?


References: 
- Beltagy, I., Lo, K., & Cohan, A. (2019). SciBERT: A Pretrained Language Model for Scientific Text (arXiv:1903.10676). arXiv. http://arxiv.org/abs/1903.10676
- Han, X., Zhang, Z., Ding, N., Gu, Y., Liu, X., Huo, Y., Qiu, J., Yao, Y., Zhang, A., Zhang, L., Han, W., Huang, M., Jin, Q., Lan, Y., Liu, Y., Liu, Z., Lu, Z., Qiu, X., Song, R., … Zhu, J. (2021). Pre-trained models: Past, present and future. AI Open, 2, 225–250. https://doi.org/10.1016/j.aiopen.2021.08.002
- Rampin, R., & Rampin, V. (2021). Taguette: Open-source qualitative data analysis. Journal of Open Source Software, 6(68), 3522. https://doi.org/10.21105/joss.03522



<a name='week42'> </a>
# Week 42
**What helped you this week?**
- A blogpost about doing unsupervised text classification using pre-trained word embeddings (Halford 2022). 

**What did you achieve?**
- I redid and finalized the extraction of all URLs and the sentences in which they appear for all the articles. 
- I set aside 30 articles to validate my work. 
    - As soon as the sentences have been classified, I will manually extract the URLs from ten of these thirty, extract the sentences, and classify the sentences. As ten articles might be a lot to ask of other people, I might ask more than two. 
- I have started to read about and implement code to perform text classification using pre-trained word embeddings (seeing as I don't have any labelled data I can train a model with). My thinking is that by seeing how closely connected the sentences are to the class concept of 'data', I can identify the sentences - and thereby the URLs - that point to specific datasets. 
    - E.g., the sentence ""Subjects and data 200 unrelated subjects were selected from the Human Con-nectome Project (HCP) 1200 Subjects Data Release with avail-able resting (task-free) and task fMRI data from a 3T MRI scan-ner (https://db.humanconnectome.org/data/projects/HCP_1200)." are about a dataset, whereas "We used FSL (https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/) and AFNI (https://afni.nimh.nih.gov/) for additional fMRI preprocessing." are not about datasets. 

**What did you struggle with?**
- Downloading a pretrained model for text classification. 
    - **spaCy**: I started out trying to download and use spaCy's "en_core_web_lg" model (because that's what Halford used; see above), but upon downloading the model I checked if it had been properly installed, which it hadn't. The length of the vocabulary was less than 800 words, which was not correct. 
    - **fastText**: For my classification, I want to build a *class concept* (based on the suggestions in Kosar et al. 2022), and I decided to pick a static word embedding to get similar words (Birundi & Devi 2021). However, they offer different pretrained models on their website, and the one I picked returned odd similar words (I used the English word vectors from this website https://fasttext.cc/docs/en/crawl-vectors.html, originally created by Grave et al. 2018. 
- Deciding on the type of pretrained model to use. 
    - Based on some of the literature I've read so far, the recent development is the use of *contextualized word embedding* (exemplified by e.g., ELMo and BERT) as opposed to *static word embedding* (exemplified by e.g., Word2Vec and GloVe) (Birunda & Devi 2021, Kosar et al. 2022). I think the use of static word embedding makes sense to build a *class concept*, whereas contextualized embedding makes sense for classifying the sentences, but I'm not sure. 

**What would you like to work on next week?**
- Continue working on (and ideally completing) classifying the sentences containing the URLs. 

**Where do you need help from Veronika?**
- Discussing the things I've mentioned above in 'What did you achieve?' and 'What did you struggle with?'; i.e., classifying sentences using word embedding and pretrained models. 

**What are the agreements after this meeting?** (to fill in after the meeting)
- 

******************************For next time******************************
- 


**References**
- Birunda, S. S., & Devi, R. K. (2021). A Review on Word Embedding Techniques for Text Classification. In J. S. Raj, A. M. Iliyasu, R. Bestak, & Z. A. Baig (Eds.), Innovative Data Communication Technologies and Application Proceedings of ICIDCA 2020 (Vol. 59, pp. 267–281). Springer Singapore. https://doi.org/10.1007/978-981-15-9651-3
- Grave, E., Bojanowski, P., Gupta, P., Joulin, A., & Mikolov, T. (2018). Learning Word Vectors for 157 Languages (arXiv:1802.06893). arXiv. https://doi.org/10.48550/arXiv.1802.06893)
- Halford, M. (2020, October 3). Unsupervised text classification with word embeddings. https://maxhalford.github.io/blog/unsupervised-text-classification/
- Kosar, A., Pauw, G. D., & Daelemans, W. (2022). Unsupervised Text Classification with Neural Word Embeddings. Computational Linguistics in the Netherlands Journal, 12, 165–181.


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