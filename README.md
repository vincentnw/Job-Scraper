# Job Scraper

A Python and Streamlit app that scrapes LinkedIn job postings and uses an LLM to rank them against your resume, producing a shortlist sorted by how well each job fits your background.

**Status:** Early personal project. Built when GPT-3.5 first came out, as my first time working with an LLM in my own project. It works end to end but is rough around the edges and not production-ready.

## What it does

- Scrapes LinkedIn job postings by position, location, and experience level using Selenium and the `linkedin_jobs_scraper` library
- Accepts a resume upload (PDF), with text extracted via `pdfplumber`
- Sends the resume and scraped jobs to an LLM, which ranks the postings from most to least relevant and removes duplicates
- Runs through a simple Streamlit interface

## Built with

- Python
- Streamlit (UI and resume upload)
- Selenium and `linkedin_jobs_scraper` (job scraping)
- pdfplumber (resume text extraction)
- LLM API via the OpenAI client, pointed at the Perplexity endpoint (relevance ranking)

## Getting started

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Create a `.env` file in the project root:
   ```
   GENAI_API_KEY=your_api_key_here
   MODEL=your_model_name_here
   ```

3. Make sure you have a matching ChromeDriver (`chromedriver.exe`) for your installed version of Chrome.

4. Run the app:
   ```bash
   streamlit run main.py
   ```

5. In the browser, upload your resume, enter a position and location, choose an experience level, and click Search. Log in to LinkedIn in the window that opens; scraping begins once you reach your feed.

## Notes and limitations

- This is an early experiment, not a polished or production-ready tool.
- LinkedIn scraping can break when the site changes and may be subject to LinkedIn's terms of service. Use responsibly and at your own risk.
- Requires a manual LinkedIn login during the run.
- Scraped results are also written to a local `jobs.txt` file.

## License

© 2024 Vincent Wirawan. All rights reserved.
