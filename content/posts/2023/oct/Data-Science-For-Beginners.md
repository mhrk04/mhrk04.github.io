---
title: "Data Science for Beginners - A Curriculum"
date: 2023-10-05T08:06:08+08:00
tags: ["Data Science","Python","Machine Learning","Data Analysis","Data Visualization","Data Enginee"]
author: ["Microsoft","Jasmine Greenaway", "Dmitry Soshnikov", "Nitya Narasimhan", "Jalen McGee", "Jen Looper", "Maud Levy", "Tiffany Souterre", "Christopher Harrison"]
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: true
draft: false
hidemeta: false
hideSummary: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "/2023/oct/Data-Science-For-Beginners/00-Title.png" # image path/url
    alt: "<alt text>" # alt text
    # caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/mhrk04/mhrk04.github.io/edit/main/content/"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

Azure Cloud Advocates at Microsoft are pleased to offer a 10-week, 20-lesson curriculum all about Data Science. Each lesson includes pre-lesson and post-lesson quizzes, written instructions to complete the lesson, a solution, and an assignment. Our project-based pedagogy allows you to learn while building, a proven way for new skills to 'stick'.

> This website content is from Microsoft Github Repo:
> [Data-Science-For-Beginners](https://github.com/microsoft/Data-Science-For-Beginners)
>> ***All the content in this site is stripped down from the original repo and I only copy the relevant info for me to this site.***



|![ ](/2023/oct/Data-Science-For-Beginners/00-Title.png)|
|:---:|
| Data Science For Beginners - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

## Are you a student?

Get started with the following resources:

- [Student Hub page](https://docs.microsoft.com/en-gb/learn/student-hub?WT.mc_id=academic-77958-bethanycheum) In this page, you will find beginner resources, Student packs and even ways to get a free cert voucher. This is one page you want to bookmark and check from time to time as we switch out content at least monthly.
- [Microsoft Learn Student Ambassadors](https://studentambassadors.microsoft.com?WT.mc_id=academic-77958-bethanycheum) Join a global community of student ambassadors, this could be your way into Microsoft

## Getting Started
> **[Students](https://aka.ms/student-page)**: to use this curriculum on your own, fork the entire repo and complete the exercises on your own, starting with a pre-lecture quiz.  Then read the lecture and complete the rest of the activities. Try to create the projects by comprehending the lessons rather than copying the solution code; however, that code is available in the /solutions folders in each project-oriented lesson. Another idea would be to form a study group with friends and go through the content together. For further study, we recommend [Microsoft Learn](https://docs.microsoft.com/en-us/users/jenlooper-2911/collections/qprpajyoy3x0g7?WT.mc_id=academic-77958-bethanycheum).

## Meet the Team

{{< youtube 8mzavjQSMM4 >}}

## Pedagogy

We have chosen two pedagogical tenets while building this curriculum: ensuring that it is project-based and that it includes frequent quizzes. By the end of this series, students will have learned basic principles of data science, including ethical concepts, data preparation, different ways of working with data, data visualization, data analysis, real-world use cases of data science, and more.

In addition, a low-stakes quiz before a class sets the intention of the student towards learning a topic, while a second quiz after class ensures further retention. This curriculum was designed to be flexible and fun and can be taken in whole or in part. The projects start small and become increasingly complex by the end of the 10 week cycle.

## Each lesson includes:

- Optional sketchnote
- Optional supplemental video
- Pre-lesson warmup quiz
- Written lesson
- For project-based lessons, step-by-step guides on how to build the project
- Knowledge checks
- A challenge
- Supplemental reading
- Assignment
- Post-lesson quiz

> **A note about quizzes**: All quizzes are contained [in this app](https://purple-hill-04aebfb03.1.azurestaticapps.net/), for 40 total quizzes of three questions each. They are linked from within the lessons, but the quiz app can be run locally; follow the instruction in the [quiz-app](https://github.com/microsoft/Data-Science-For-Beginners/tree/main/quiz-app) folder. They are gradually being localized.

## Lessons

|![](/2023/oct/Data-Science-For-Beginners/00-Roadmap.png)|
|:---:|
| Data Science For Beginners: Roadmap - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

### Introduction

| Lesson Number | Topic | Learning Objectives | Linked Lesson | Author |
| :-----------: | :----------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------: | :----: |
| 01 | Defining Data Science | Learn the basic concepts behind data science and how it’s related to artificial intelligence, machine learning, and big data. | [lesson](1-introduction/01-defining-data-science/defining-data-science/) [video](https://youtu.be/beZ7Mb_oz9I) | [Dmitry](http://soshnikov.com) |
| 02 | Data Science Ethics | Data Ethics Concepts, Challenges & Frameworks. | [lesson](1-Introduction/02-ethics/README.md) | [Nitya](https://twitter.com/nitya) |
| 03 | Defining Data | How data is classified and its common sources. | [lesson](1-Introduction/03-defining-data/README.md) | [Jasmine](https://www.twitter.com/paladique) |
| 04 | Introduction to Statistics & Probability | The mathematical techniques of probability and statistics to understand data. | [lesson](1-Introduction/04-stats-and-probability/README.md) [video](https://youtu.be/Z5Zy85g4Yjw) | [Dmitry](http://soshnikov.com) |

### Working with Data

| Lesson Number | Topic | Learning Objectives | Linked Lesson | Author |
| :-----------: | :----------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------: | :----: |
| 05 | Working with Relational Data |  Introduction to relational data and the basics of exploring and analyzing relational data with the Structured Query Language, also known as SQL (pronounced “see-quell”). | [lesson](2-Working-With-Data/05-relational-databases/README.md) | [Christopher](https://www.twitter.com/geektrainer) | | |
| 06 | Working with NoSQL Data |  Introduction to non-relational data, its various types and the basics of exploring and analyzing document databases. | [lesson](2-Working-With-Data/06-non-relational/README.md) | [Jasmine](https://twitter.com/paladique)|
| 07 | Working with Python |  Basics of using Python for data exploration with libraries such as Pandas. Foundational understanding of Python programming is recommended. | [lesson](2-Working-With-Data/07-python/README.md) [video](https://youtu.be/dZjWOGbsN4Y) | [Dmitry](http://soshnikov.com) |
| 08 | Data Preparation |  Topics on data techniques for cleaning and transforming the data to handle challenges of missing, inaccurate, or incomplete data. | [lesson](2-Working-With-Data/08-data-preparation/README.md) | [Jasmine](https://www.twitter.com/paladique) |

### Data Visualization

| Lesson Number | Topic | Learning Objectives | Linked Lesson | Author |
| :-----------: | :----------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------: | :----: |
| 09 | Visualizing Quantities | Learn how to use Matplotlib to visualize bird data 🦆 | [lesson](3-Data-Visualization/09-visualization-quantities/README.md) | [Jen](https://twitter.com/jenlooper) |
| 10 | Visualizing Distributions of Data | Visualizing observations and trends within an interval. | [lesson](3-Data-Visualization/10-visualization-distributions/README.md) | [Jen](https://twitter.com/jenlooper) |
| 11 | Visualizing Proportions | Visualizing discrete and grouped percentages. | [lesson](3-Data-Visualization/11-visualization-proportions/README.md) | [Jen](https://twitter.com/jenlooper) |
| 12 | Visualizing Relationships | Visualizing connections and correlations between sets of data and their variables. | [lesson](3-Data-Visualization/12-visualization-relationships/README.md) | [Jen](https://twitter.com/jenlooper) |
| 13 | Meaningful Visualizations | Techniques and guidance for making your visualizations valuable for effective problem solving and insights. | [lesson](3-Data-Visualization/13-meaningful-visualizations/README.md) | [Jen](https://twitter.com/jenlooper) |

### Data Science Lifecycle

| Lesson Number | Topic | Learning Objectives | Linked Lesson | Author |
| :-----------: | :----------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------: | :----: |
| 14 | Introduction to the Data Science lifecycle | Introduction to the data science lifecycle and its first step of acquiring and extracting data. | [lesson](4-Data-Science-Lifecycle/14-Introduction/README.md) | [Jasmine](https://twitter.com/paladique) |
| 15 | Analyzing | This phase of the data science lifecycle focuses on techniques to analyze data. | [lesson](4-Data-Science-Lifecycle/15-analyzing/README.md) | [Jasmine](https://twitter.com/paladique) | | |
| 16 | Communication | This phase of the data science lifecycle focuses on presenting the insights from the data in a way that makes it easier for decision makers to understand. | [lesson](4-Data-Science-Lifecycle/16-communication/README.md) | [Jalen](https://twitter.com/JalenMcG) | | |

### Data Science in the Cloud

| Lesson Number | Topic | Learning Objectives | Linked Lesson | Author |
| :-----------: | :----------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------: | :----: |
| 17 | Data Science in the Cloud | This series of lessons introduces data science in the cloud and its benefits. | [lesson](5-Data-Science-In-Cloud/17-Introduction/README.md) | [Tiffany](https://twitter.com/TiffanySouterre) and [Maud](https://twitter.com/maudstweets) |
| 18 | Data Science in the Cloud | Training models using Low Code tools. |[lesson](5-Data-Science-In-Cloud/18-Low-Code/README.md) | [Tiffany](https://twitter.com/TiffanySouterre) and [Maud](https://twitter.com/maudstweets) |
| 19 | Data Science in the Cloud | Deploying models with Azure Machine Learning Studio. | [lesson](5-Data-Science-In-Cloud/19-Azure/README.md)| [Tiffany](https://twitter.com/TiffanySouterre) and [Maud](https://twitter.com/maudstweets) |

### Data Science in the Wild

| Lesson Number | Topic | Learning Objectives | Linked Lesson | Author |
| :-----------: | :----------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------: | :----: |
| 20 | Data Science in the Wild | Data science driven projects in the real world. | [lesson](6-Data-Science-In-Wild/20-Real-World-Examples/README.md) | [Nitya](https://twitter.com/nitya) |

## GitHub Codespaces

Follow these steps to open this sample in a Codespace:
1. Click the Code drop-down menu and select the Open with Codespaces option.
2. Select + New codespace at the bottom on the pane.
For more info, check out the [GitHub documentation](https://docs.github.com/en/codespaces/developing-in-codespaces/creating-a-codespace-for-a-repository#creating-a-codespace).

## VSCode Remote - Containers
Follow these steps to open this repo in a container using your local machine and VSCode using  the VS Code Remote - Containers extension:

1. If this is your first time using a development container, please ensure your system meets the pre-reqs (i.e. have Docker installed) in [the getting started documentation](https://code.visualstudio.com/docs/devcontainers/containers#_getting-started).

To use this repository, you can either open the repository in an isolated Docker volume:

**Note**: Under the hood, this will use the Remote-Containers: **Clone Repository in Container Volume...** command to clone the source code in a Docker volume instead of the local filesystem. [Volumes](https://docs.docker.com/storage/volumes/) are the preferred mechanism for persisting container data.

Or open a locally cloned or downloaded version of the repository:

- Clone this repository to your local filesystem.
- Press F1 and select the **Remote-Containers: Open Folder in Container...** command.
- Select the cloned copy of this folder, wait for the container to start, and try things out.

## Offline access

You can run this documentation offline by using [Docsify](https://docsify.js.org/#/). Fork this repo, [install Docsify](https://docsify.js.org/#/quickstart) on your local machine,  then in the root folder of this repo, type `docsify serve`. The website will be served on port 3000 on your localhost: `localhost:3000`.

> Note, notebooks will not be rendered via Docsify, so when you need to run a notebook, do that separately in VS Code running a Python kernel.

## Other Curricula

- [Machine Learning for Beginners](https://aka.ms/ml-beginners)
- [IoT for Beginners](https://aka.ms/iot-beginners)
- [Web Dev for Beginners](https://aka.ms/webdev-beginners)
- [AI for Beginners](https://aka.ms/ai-beginners)