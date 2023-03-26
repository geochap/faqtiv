# About FAQtiv

FAQtiv is an exploratory project with a goal of making it easier to build trustworthy question answering experiences against your structured data. 
It operates by exposing your data through a set of easily configured apis and using OpenAI services to generate programs against those apis to answer user questions.
It supports an interface to review, improve, and curate those programs leading to better and more trusted answers over time. 
The mechanism for this is that when you add a question, similar verified questions and their programs are included as examples in the prompt to OpenAI.

It initially consists of:

- A node + angular based tool that lets users ask questions and curate the generated answer scripts
- A java based framework for configuring parameterized queries and entity indexers against the data in your database

Note that the system operates by generating javascript programs against APIs, not by generating SQL. There are various reasons for this:

- Answering queries typically involves other non-sql services. E.g. entity resolution is better done via elastic/opensearch/etc. than in sql. 
- Databases can be tuned to answer specific query patterns instead of getting hit with arbitrarily generated sql.
- API as abstraction layer is far more general purpose and lends itself better to composability.


# Getting Started
...

# Installation

# Usage - Application

The FAQtiv application has these pages:

- The home page which shows a top list of questions
- A search results page which shows you the questions similar to one you asked
- A question page that shows you a question and its answer
- A question edit page that shows you the generated answer program, allows you to edit it, and mark it as verified

## Home
The home page shows you a list of top questions (currently just reverse chronological order).

![image](https://user-images.githubusercontent.com/740118/227785337-2e21a334-1807-42f3-9446-cc2c67c590d9.png)

## Search Results
Entering a question in the search bar will show you similar questions that have been asked. You can select from one of those, or click "Add" to add a new question. 
Adding a question will cause a program to be generated against the available apis to answer that question.

![image](https://user-images.githubusercontent.com/740118/227785565-8338406f-c69d-48aa-b551-896f49956448.png)

## Question

If a user clicks on a question on the home page or the search results page or adds a new question, they will be taken to the question page to see the results.

![image](https://user-images.githubusercontent.com/740118/227786531-2a614c35-d3e4-4bc3-8754-a59918de1664.png)

The user can click on the edit icon to edit the question.

## Edit a Question

The edit question page lets the user update the question, review and modify the generated answer script, and mark a question as verified.

![image](https://user-images.githubusercontent.com/740118/227786706-08d96f5e-f0d8-4a73-87d1-969c89033533.png)

# Usage - SQL Agent
The FAQtiv SQL Agent is a java/dropwizard application that serves two purposes:

- It lets you configure and peridiocally run entity index operations (entities are indexed in opensearch by default).
- It lets you configure and host a set of parameterized queries with well defined inputs and outputs against a SQL database. 

YAML is used to configure the overall project, the individual entity index queries, and the parameterized queries. 

# Roadmap



