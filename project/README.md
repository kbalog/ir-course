# Group project

## Objectives

The objective of project work is to apply the knowledge gained in the course, in a group setting, to a selected (open) information retrieval problem.
Specifically, you'll first need to establish a reasonable baseline, then develop one or multiple advanced methods aiming to improve over the baseline. Using a standard test collection, you'll need to experimentally compare the baseline and advanced solutions.

## Weekly meeting slots

Each group will be allocated a dedicated 15mins slot (during what would normally be lecture/class hours on Tue/Wed) to discuss their progress. It is expected that at least one member of the group is present in person.

*Teams and weekly meeting slots are published on [Canvas](https://stavanger.instructure.com/courses/8838/pages/group-project).*


## Deadlines

  * **October 27 (Wed) 16:00** Registration of groups by filling out [this form](https://forms.gle/DQNUr2vbNfsRPWSH7). If you don't register, you'll be "randomly" assigned with other people.
  * **Nov 12 (Fri) 12:00** Delivery of draft project report for feedback. Feedback will be given during the Tue/Wed meeting the week after.
  * **Nov 22 (Mon) 12:00** Delivery of final project report. 

## Projects

You may choose one from the following projects:

  * **[MS Marco Document re-ranking](https://microsoft.github.io/msmarco/)**
    - Given a candidate top-100 document as retrieved by BM25, re-rank documents by relevance. This task has also run as part of the TREC 2019 Deep Learning track.
    - Document collection: MS MARCO document corpus (3.2M documents, 22GB)
    - Resources
      - [Task GitHub repo](https://github.com/microsoft/MSMARCO-Document-Ranking)
      - [Relevance judgments for evaluation topics](https://trec.nist.gov/data/cast/2019qrels.txt)
      - [TREC 2019 Deep Learning track overview](https://arxiv.org/abs/2003.07820)
    - [Discussion group (on Canvas)](https://stavanger.instructure.com/courses/8838/discussion_topics/120134)
  * **[TREC 2020 Conversational Assistance](http://www.treccast.ai/)**
    - Given a series of conversational utterances, identify relevant passages for each user utterance that satisfies the user's information need.
    - Document collection: MARCO Ranking passages and Wikipedia (TREC CAR)
    - Resources
      - [Task GitHub repo](https://github.com/daltonj/treccastweb/tree/master/2020)
      - [TREC 2020 Conversational Assistance track overview](https://trec.nist.gov/pubs/trec29/papers/OVERVIEW.C.pdf)
      - [TREC 2020 Conversational Assistance judgments for evaluation topics](https://trec.nist.gov/data/cast2020.html)
    - [Discussion group (on Canvas)](https://stavanger.instructure.com/courses/8838/discussion_topics/120142)
  * **[Semantic Answer Type Prediction 2020](https://smart-task.github.io/2020/)**
    - Given a question in natural language, the task is to predict type of the answer using a set of candidates from a target ontology (DBpedia).
    - Document collection: DBpedia ([dump 2016-10](http://downloads.dbpedia.org/2016-10/)) and/or Wikidata ([dump](https://dumps.wikimedia.org/wikidatawiki/entities/))
    - Resources
      - [Task GitHub repo](https://github.com/smart-task/smart-dataset)
      - Papers: [Balog & Neumayer (2012)](https://krisztianbalog.com/files/cikm2012-querytypes.pdf), [Garigliotti et al. (2017)](https://krisztianbalog.com/files/sigir2017-qt.pdf), [Setty & Balog (2020)](https://krisztianbalog.com/files/iswc2020-smart.pdf)
    - [Discussion group (on Canvas)](https://stavanger.instructure.com/courses/8838/discussion_topics/120145)


## Workflow and rules

  * You'll need to hand in a report using the specified project template. The page limit for the report is 4 A4 pages (in double column format).
  * You'll also need to submit your code and the generated output files so that we can verify your solution and results.
  * There are no restrictions on the programming language, toolkits/libraries used, etc. with the default choice being Python and the packages used in the exercises/assignments.
  * You are free to use any external data collections or resources (e.g., pre-trained embeddings) in addition to the 'official' problem datasets.
  * Some of the problems involve working with large datasets. If you need server access, you'll need to contact the Unix system administrator.
  * While you are expected to work independently as a group, you'll have the possibility to get feedback on your ideas in a regular weekly basis. For each group, there will be a weekly dedicated 15 mins slot to discuss the project with the lecturer and student assistant. Also, there is an internal intermediate deadline for getting feedback on the draft of your report.

## Timeline

While the following is merely a recommendation, it may help you to stay on course.

  * **Week 1**
    - Understand the problem, identify and read related literature (and ideally complete the corresponding sections of the report)
    - Preprocess and index the document collection
    - Implement a baseline method
  * **Week 2**
    - Run and evaluate the baseline method
    - Implement an advanced method
    - Write up your progress so far and submit the report for feedback    
  * **Week 3**
    - Run and evaluate your advanced method
    - Experiment with additional methods or refinements of your advanced method
    - Finalize your report

## Report

  * Use the [ACM two-column template](https://www.acm.org/publications/proceedings-template) for the report.
  * It is highly recommended that you use LaTeX.  A template made specifically for the project report is made available on [Overleaf](https://www.overleaf.com/read/sqhpmsfdpdxh).
  * **NB: Include the Team ID assigned to you in the report title or subtitle.**

### Structure

Structure your paper according to the following sections:

  * **Introduction** - Explain the context of the problem that you are tackling, including references to relevant literature.
  * **Problem Statement** - Formalize the task (in terms of input and output) and specify important details about the data collection.
  * **Baseline Method** - Explain what you are taking as your baseline method, as well as why this is a reasonable baseline, and why you are making specific implementation choices.
  * **Advanced Method** - Explain what you are taking as your advanced method(s), as well as why this is a promising attempt to outperform the baseline method, and why you are making specific implementation choices.
  * **Results** - With tables and graphs, make a clear, concise, and digestible presentation of the data produced by your experiments. This includes describing the key facts and trend from your results.
  * **Discussion and Conclusions** - Summarize and discuss different challenges you faced and how you solved those. Include interpretations of the key facts and trends you observed and pointed out in the Results section. Which method performed best, and why? Speculate: What could you have done differently, and what consequences would that have had?

You also need to attach a section on **Division of Work During the Project** as an appendix, with a short paragraph describing the contributions of each student in the project, and a statement on how you split the task and the workload between team members. This section does not count towards the 4-page limit.

## Evaluation

  * **Problem understanding** (8 points)
    - Demonstrating your understanding of the chosen project, by clearly explaining the problem at hand and the challenges involved.
    - Identifying the main families of approaches developed for the task at hand (i.e., literature review).
  * **Baseline method** (10 points)
    - Selecting a sensible baseline, implementing and evaluating it using the given benchmark dataset.    
  * **Advanced method(s)** (12 points)
    - Selecting an interesting or performant advanced method or developing a novel approach from scratch, implementing and evaluating it experimentally.
    - Points are awarded for convincing motivation, creativity, overall performance (improvements over the baseline).
  * **Report** (15 points)
    - Reporting the problem, methods, key decisions, and results in a clear and structured manner.
    - The report should contain sufficient details for one to be able to reproduce the results based on the provided description. It should properly attribute and reference related work as well as use visual tools (such as illustrations, plots and tables) to support and communicate the findings effectively.
  * **Code quality** (5 points)
    - Producing clearly structured, well-documented, and readable code.
