# AI Web Scraper

An AI-powered web scraping tool built with Python and Streamlit. Enter a website URL,
describe what data you want, and the app scrapes the page and extracts exactly that
information using a local large language model.

## Features

- **Simple web interface:** built with Streamlit, no coding needed to use it
- **Captcha handling:** uses Bright Data's Scraping Browser to detect and solve captchas automatically
- **Smart content cleaning:** removes scripts and styles with BeautifulSoup and keeps only readable text
- **AI-based parsing:** uses Ollama (local LLM) with LangChain to extract data based on your plain-English description
- **Large page support:** splits long pages into chunks so the model can process them
- **Private and free to run:** the LLM runs locally on your machine

## How it works

1. Enter a website URL in the app.
2. The app connects to Bright Data's Scraping Browser (Selenium) and loads the page, solving captchas if needed.
3. The HTML is cleaned and split into smaller chunks.
4. Each chunk is sent to an Ollama model with your description, for example
   "Extract the post titles and links into a table."
5. The results are combined and shown in the app.

## Tech stack

Python, Streamlit, Selenium, BeautifulSoup, LangChain, Ollama, Bright Data Scraping Browser

## Setup

1. Clone the repo and create a virtual environment:
   python -m venv ai
   ai\Scripts\activate
2. Install dependencies:
   pip install -r requirements.txt
3. Install Ollama from ollama.com and pull a model:
   ollama pull llama3.1
4. Create a .env file (see sample.env) and add your Bright Data credentials:
   SBR_WEBDRIVER=https://YOUR_USERNAME:YOUR_PASSWORD@brd.superproxy.io:9515
5. Run the app:
   streamlit run main.py

## Note

Never commit your .env file. Only scrape websites you are allowed to scrape and
follow their terms of service.
