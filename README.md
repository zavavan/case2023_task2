# case2023_task2
A repository for data and evaluation code for the Task 2 of the CASE2023@RNLP workshop


# Collecting and Geocoding Armed Clash Events in Russian Ukrainian Conflict at CASE @ RANLP 2023

Nowadays the unprecedented quantity of easily accessible data on social, political, and economic processes offers ground-breaking potential in guiding data-driven analysis of socio political phenomena: Armed conflicts, political movements, fights for economic and social rights, and various related socio-political happenings are reported in news articles and social media posts and recorded in curated databases. On the other hand, automatic event detection from texts and  event geocoding has long been a challenge for the natural language processing (NLP) community. It requires sophisticated methods and resources, such as Machine Learning models, linguistic rules and dictionaries, geographic gazetteers.

## Task definition

The task Collecting and Geocoding Armed Clash Events in Russo-Ukrainian Conflict  is being held as a sub-task of the 6th Workshop on Challenges and Applications of Automated Extraction of Socio-political Events from Text (CASE 2023). The task will use data from the Russo-Ukrainian  Conflict to test the capabilities of event detection systems to extract, geocode and de-duplicate armed clashes in news and social media postsл Evaluation will be based on the  correlation between the spatio-temporal distribution and number of the extracted events and those which are in the ground truth data set. 
We invite contributions from researchers in  NLP, ML, Deep Learning, and AI. The call is directed also towards socio-political scientists, researchers in conflict analysis and forecasting, peace studies, and computational social science.
All participating teams will be able to publish their system description paper in the workshop proceedings published by ACL. For more information on the workshop, 

please visit the Workshop website https://emw.ku.edu.tr/case-2023/ and the conference website https://ranlp.org/ranlp2023/.

## Data

Gold Standard and Text Input Data for the participant systems for the time range 24.02.2022-24.08.2022 has been prepared and will be shared with the applicants on the Task website.
1.1 Training Data
No training data are provided for this Task. The data utilized for CASE 2023 Task 1, which is described in Hürriyetoğlu, A. et al. (2022, 2020b), can be used for training systems for this task (Task 2). Additionally data can be used to build systems/models that can detect protest events in tweets and news articles. 

## Input Data
The participant systems will be evaluated on raw data collections including Telegram messages, the New York Times and Ukrainian-Russian official news channels. 
Namely, the data collections comprise:

• English  language social media massage and news corpus comprising. 48.007 Telegram Message and The New York Times News about Ukraine.

• Ukrainian language social media collection comprising 102.135 Telegram Message and Ukraine News Agency News.

• Russian language social media collection comprising 8.534 Telegram Message and Russian News Agency News.

Further details on the text collections and sampling methods are provided in the folders news and Social Media of the github repo for the Task (https://github.com/zavavan/case2023_task2). 


## Gold Standard Data

The Russo-Ukrainian Conflict ground truth data primarily consists of data coming from the Armed Conflict Location & Event Data Project (ACLED). We will be adding alternative ground-truth datasets in order to prevent the bias that may be introduced by using a single definition and interpretation of an event. Full details on the manually curated data used as Gold Standard for the correlation analysis will be disclosed at the end of the evaluation period. Please check documentation on the folder gold_standard of the Task github repo.


## Evaluation

The systems which participate in this shared task will be required to detect news articles and Telegram posts which contain description of ongoing armed clashes. The time and place of each armed clash should be detected at date level (regarding the time) and precise geographic coordinates (latitude and longitude). The systems should ideally extract event times, based on multiple text reports. 
In order to evaluate the ability of automatic event-coders to reproduce the gold standard armed clash event dataset, we adapt two correlation methods originally used in micro-level analysis of political violence by Hammond and Weidmann (2014), based on aggregation of event counts uniform grid geographical cells and 1-day time spans and apply a number of standard correlation coefficients and error measures.
For each of the input text corpora in1.2, each participant may submit up to 3 different system responses. Each system response will consist of a csv file with the following naming pattern: 
“submission.<team-name>.<corpus>.<response-number>.csv”
where <corpus> is either “social_media” or “news”.
For instance: “submission.MyTeam.news.3.csv” for the 3rd submission of team “MyTeam” on the news corpus.
Each system response file will have one line per event, where each line will have the following format:
<id>,<City>,<Region>,<Country>,<Date>
where <id> is a numerical event identifier, <City>,<Region>,<Country> are canonical English names of the City,State/Region and Country, respectively, of the detected event location. While only the <country> attribute is mandatory, systems are expected to assign a description of the event location at the finest grained level possible, as otherwise geographical coordinate conversion may penalize the correlation score on geographical cell aggregation. <Date> is the assigned date of the event in the format YYYY-MM-DD.
A sample system response file line:
0,Kharkiv,Kharkiv Oblast,Ukraine,2022-05-02
A sample system output file can be downloaded from the Task repo at:
https://github.com/zavavan/case2023_task2/blob/main/submission.myteam.news.3.csv


## Important Dates (AoE time)

Sample Text archive is available: May 22, 2023 

Text archive for evaluation is available: July 1, 2023 

Evaluation period starts: July 1, 2023

Evaluation period ends: July 24, 2023 

System Description Paper submissions due: July 31, 2023 

Notification to authors after review: August 7, 2023 

Camera-ready: August 25, 2023
  
Workshop period @ RANLP: Sep 7-8, 2023


## Organization

Hristo Tanev (Joint Research Centre (JRC), European Commission, Italy)
  
Onur Uca, Sociology (Sociology, Mersin University, Turkey)
  
Vanni Zavarella (University of Cagliari, Italy)
  
Ali Hürriyetoğlu (KNAW Humanities Cluster DHLab, the Netherlands)
  
Please contact the organizers at  hristo.tanev@ec.europa.eu or onuruca@mersin.edu.tr  for your questions. 




## References
Jesse Hammond and Nils B Weidmann. Using machine-coded event data for the micro-level study of political violence. Research & Politics, 1(2):2053168014539924, 2014.

 Hürriyetoğlu, A., Mutlu, O.,  Duruşan, F.,  Uca, O,.  Gürel, A.,S.,  Radford, B., Dai, Y., Hettiarachchi, H., Stoehr, N., Nomoto, T., Slavcheva, M.,  Vargas, F.,  Javid, A.,  Beyhan, F., Yörük, E. (2022). Extended Multilingual Protest News Detection Shared Task1,CASE2021 and 2022. arXiv preprint arXiv:2211.11360. Url: https://arxiv.org/abs/2211.11360

 Hürriyetoğlu, A., Yörük, E., Yüret, D., Mutlu, O., Yoltar, Ç., Duruşan, F., & Gürel, B. (2020b). Cross-context news corpus for protest events related knowledge base construction. arXiv preprint arXiv:2008.00351. In Automated Knowledge Base Construction (AKBC). URL: https://www.akbc.ws/2020/papers/7NZkNhLCjp


