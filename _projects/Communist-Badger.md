---
title: Communist Badger
date: 2018-12-26
header:
  image: /assets/images/ProjectAssets/CommunistBadger/CommunistBadgerLogo.png
categories:
  - Project
tags:
  - Python
toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---

**Language Used**: Python3

**Source Code**: [GitHub Link](https://github.com/kjanjua26/CommunistBadger)

## Goal
The goal of this product, CommunistBadger, is to provide users with a platform where they can see stocks of different companies and can check live trends of where the stock market is going. The successful prediction of a stock's future could yield significant profit.

## Tools & Libraries
- Pickle
- MongoDB
- Tensorflow
- Python tkinter (GUI)
- Numpy
- Matplotlib
- Fuzzy Testing
- Sentiment Analysis
- Web Scraping
- Twitter API

## Description
CommunistBadger is a stock predictor tool which provides user with an insight of how the stock market is doing and how it would do in the future. The product was trained on data sources from "News Articles", "Tweets" & "Stock Prices". The news articles were scraped and saved in csv file format and Twitter dataset was used csv files for multiple csv files are used for the different stock prices.

## Results
### Google
Here is a sentiment bar graph of "Google - GOOGL" versus Tweets data (20 Tweets):
![GOOGL Sentiment Tweet](/assets/images/ProjectAssets/CommunistBadger/sentiment_results_tweets_Google.png)

Similarly, this is what News vs sentiment bar graph looks like for "Google - GOOGL" (20 News Articles):
![GOOGL Sentiment News](/assets/images/ProjectAssets/CommunistBadger/sentiment_results_news_Google.png)

### Apple
This is a fitted RBF Kernel Graph for "Apple - AAPL":
![APPL RBF fit](/assets/images/ProjectAssets/CommunistBadger/Apple_stock_rbf.png)

Candlestick Graph for "Apple - APPL":
![APPL Candlestick](/assets/images/ProjectAssets/CommunistBadger/candlestick_aapl.png)

### EBay
Candlestick Graph for "EBay":
![EBAY Candlestick](/assets/images/ProjectAssets/CommunistBadger/stock_prediction_EBAY.png)

### Interfaces
#### Initial Interface
![Initial Interface](/assets/images/ProjectAssets/CommunistBadger/InitialInterface.png)

#### Search "View Graph" Interface
![Search "View Graph" Interface](/assets/images/ProjectAssets/CommunistBadger/SearchViewGraphInterface.png)

#### Market "Company Name" Interface
![Market "Company Name" Interface](/assets/images/ProjectAssets/CommunistBadger/MarketCompanyNameInterface.png)

#### Interface Levels
![Interface Levels](/assets/images/ProjectAssets/CommunistBadger/InterfaceLevels.png)

### Subsystem Diagrams
#### Web Scraper Subsystem Diagram
![Web Scraper Subsystem Diagram](/assets/images/ProjectAssets/CommunistBadger/WebscraperSubsystemDiagram.png)

#### Model Training Subsystem Diagram
![Model Training Subsystem Diagram](/assets/images/ProjectAssets/CommunistBadger/ModelTrainingSubsystemDiagram.png)

### Sequence Diagrams
#### Application Launch Sequence Diagram
![Application Launch Sequence Diagram](/assets/images/ProjectAssets/CommunistBadger/InitialSequenceDiagram.png)

#### Update Sequence Diagram
![Update Sequence Diagram](/assets/images/ProjectAssets/CommunistBadger/UpdateSequenceDiagram.png)

#### Search Sequence Diagram
![Search Sequence Diagram](/assets/images/ProjectAssets/CommunistBadger/SearchSequenceDiagram.png)

### Activity Diagrams
#### Update Activity Diagram
![Update Activity Diagram](/assets/images/ProjectAssets/CommunistBadger/UpdateActivityDiagram.png)

#### Search Activity Diagram
![Search Activity Diagram](/assets/images/ProjectAssets/CommunistBadger/SearchActivityDiagram.png)

## References
To read Software Requirement Specification (SRS) Document about this product please click this [link](https://github.com/kjanjua26/CommunistBadger/blob/master/Documentation/Project%20Deliverable%201.pdf).

To read the Software Design Specification (SDS) Document about this product please click this [link](https://github.com/kjanjua26/CommunistBadger/blob/master/Documentation/Project%20Deliverable%202-SDS.pdf).

SRS References
- [Krazy Tech](https://krazytech.com/projects/sample-software-requirements-specificationsrs-report-airline-database)
- [VCE IT](http://www.vceit.com/p/SRS-sample.htm)
- [Belitsoft](https://belitsoft.com/custom-application-development-services/software-requirements-specification-document-example-international-standard)

Stock Market Explanation
- [How The Stock Exchange Works (For Dummies) - YouTube Video](https://www.youtube.com/watch?v=F3QpgXBtDeo)
- [How the Stock Market Works in 5 Minutes - YouTube Video](https://www.youtube.com/watch?v=_-dD416-cqw)
- [STOCK EXCHANGE EXPLAINED IN 2 MINUTES - YouTube Video](https://www.youtube.com/watch?v=l3t406oTmss)

Stock Prediction
- [Predict Stock Market with Daily Top News - Hackernoon](https://hackernoon.com/predict-stock-market-with-daily-top-news-8c8db25bef8d)

Others
- [20 Python libraries you can’t live without](https://yasoob.me/2013/07/30/20-python-libraries-you-cant-live-without/)

You can fork the project on [GitHub](https://github.com/ShahzaibWaseem/Project-DSA) to add more features to the project.