# AI Researcher Intern - Technical Test

## Introduction

This repository contains two Jupyter notebooks as part of a technical test for the position of **AI Researcher Intern**. The test subject focuses on the **decarbonization of industrial heat**, specifically to create a system that scrapes, classifies, and summarizes case studies related to this topic.

At Entropic, the mission is to decarbonize industrial heat, which contributes significantly to worldwide CO2 emissions. The goal of this test is to demonstrate skills in web scraping, data cleaning, relevance classification, and natural language summarization.

## Case Description

### Task Overview

You are tasked with building a system to:

1. **Scrape case studies** related to "decarbonization of industrial heat" from publicly available sources.
2. **Classify the scraped case studies** based on predefined relevance criteria (e.g., keywords or technologies).
3. **Generate brief summaries** of the relevant case studies using NLP techniques.

### Notebooks

This repository contains the following Jupyter notebooks:

1. `PageScraper.ipynb`: Implements the web scraping task to extract case study data from a website.
2. `SummarizationTask.ipynb`: Processes the scraped content, classifies it based on relevance, and generates summaries using a large pre-trained language model.

### Proof Files
In the ./ProofFiles directory you will find the bases files created when running the notebooks on my local:
- `scraped_articles.csv` : Scraped Articles.
- `cleaned_scraped_articles.csv` : Csv after Cleaning.
- `Relevant_caseStudies.csv` : Final classified relevant articles only.
Finally:
- `Summarized_relevant_casestudies.csv` : Final File Containing Title,Link,Cleaned_Content,Summary .

## Notebooks Overview

### 1. PageScraper.ipynb

**Functionality:**
- This notebook scrapes case studies from the [ISPT Decarbonization of Heat Case Studies](https://ispt.eu/projects/?theme-tag=heat) using **Selenium** with a **Firefox extension** for robust and flexible web scraping.
- The scraper collects all articles on the page, and the scraped data is cleaned by removing redundant sections (e.g., headers, footers) and irrelevant webpage areas.

**Execution Instructions:**
- Ensure `FireFox` and `geckodriver` are properly configured).
- Run the notebook to scrape and clean the case study data from the website.

### 2. SummarizationTask.ipynb

**Functionality:**
- **Memory Optimization**: Implemented with **Anslove** to reduce RAM usage, ensuring the process could run efficiently on **Google Colab** with a **T4 GPU**.
- **Model**: Utilized the **Gamma2-9b parameter model** to perform summarization.
- **Summarization Process**:
  - Prompted the model to summarize relevant case studies based on the output of the classification process.
  - Cleaned and refined the generated summaries to ensure clarity and relevance.
  
**Execution Instructions:**
- Install FireFox and geckodriver extentions on local and copy their paths.
- Run the notebook to generate and clean the summaries for the relevant case studies.

## Requirements

- `selenium`
- `geckodriver`
- `transformers`
- `unsloth`
- `nltk`
- `pandas`

## How to Run the Project

1. Clone the repository:
   ```
   git clone https://github.com/GhaouiYoussef/TestTech
   cd TestTech
   ```

2. Install the required extetsions:

   FireFox and Geckodriver 

3. Execute the notebooks:
   - Start with `PageScraper.ipynb` to scrape and clean the case studies.
   - Follow up with `SummarizationTask.ipynb` for classification and summarization. This notenook uses the final csv file output of the previous one `PageScraper.ipynb`: `Relevant_caseStudies.csv`
4. Final Output File:
   - The Final file would be: `Summarized_relevant_casestudies.csv`

## Summary of Approach

- **Web Scraping**: Scraped content from a targeted website using **Selenium** and processed the HTML data. The scraper collected all articles, and redundant page sections were removed during data cleaning.
- **Relevance Classification**: Developed a hybrid classification approach with two approved hypotheses:
  1. **TF-IDF and cosine similarity** based on decarbonization-related keywords.
  2. **Pre-trained model embeddings and cosine similarity** to judge relevance based on content similarity.
- Combined these methods with a **majority decision model** to finalize the relevance classification.
- **Summarization**: Using **Unsloth** to optimize memory usage, we prompted the **Gamma2-9b model** to generate summaries. The summaries were then cleaned and finalized to ensure concise, clear, and relevant outputs.

## Conclusion

This system automates the extraction, classification, and summarization of case studies related to the decarbonization of industrial heat, demonstrating advanced skills in web scraping, data processing, classification, memory optimization, and NLP-based summarization.

For any inquiries, feel free to reach out to the email mentioned in the test subject.
