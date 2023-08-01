# Smart Document Analyzer

![Demo](https://github.com/JeffC25/smart-document-analyzer/blob/main/documents/demo.gif.gif)

## Instructions:

1. Run `git clone git@github.com:JeffC25/smart-document-analyzer.git` to clone the repository
2. Create a `.env` file in the cloned directory and populate it with `SECRET_KEY=<your secret key>`
3. Run `pip install -r requirements.txt` to install Python dependencies
4. Run `apt-get install sqlite3` to install SQLite3
5. Run `python3 main.py` to launch the Flask application

## Overview

This project is a serverside-rendered application that allows users to generate summaries, keywords, and sentiment from PDF files, news article URLs, or manual text input. It consists of the following major componenst: a SQL database, PDF uploader, news article ingester, NLP sentiment module, and a frontend UI created with Bootstrap.
## PDF Uploader

The PDF uploader module uses the PyPdf library to read a PDF file and output its text contents.

## News Article Ingester

The news article ingester module uses the newspaper3k to load an article specified by its URL. The module is responsible for parsing the article and outputting its text contents.

## NLP Sentiment

The NLP sentiment module implements a Content() class that takes in an input string. It consists of methods that generate for the text a summary, list of keywords, and sentiment.

It uses a simple extractive text algorithm that generates its analysis by utilizing stopwords, word frequencies, and sentence weights in conjunction with the NLTK, TextBlob, and Yake libraries.

## Database Overview 

The database is implemented with SQLAlchemy and SQLite3 and manages users and uploaded documents/articles.

## UI

The project frontend was created using Bootstrap CSS. It currently features sign up, login, and sign out functionalities for authentication. Once signed in, the user may access the navbar to analyze text in 3 ways: 
1. Input an article URL
2. Upload a PDF document
3. Manually input text

## API

The project currently supports endpoints for analysis via article url and manual text input. 

For analyzing via article url, request the endpoint `/api/article=<article url>`

For analyzing via text input, request the endpoint `/api/text=<text>`
