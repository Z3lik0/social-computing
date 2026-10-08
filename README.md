# Social Computing — Course Assignments & Projects

This repository contains assignment notebooks and practical implementations completed as part of the **Social Computing** course (Department of Informatics, University of Zurich).

The course covers computational methods to collect, model, analyze, and audit data from online platforms, social systems, and user interactions. Topics span web scraping, REST APIs, browser automation, algorithmic auditing, agent-based modeling (ABM), natural language processing (NLP), and inter-annotator reliability.

---

## 📚 Overview of Notebooks

| Notebook | Topic | Key Technologies | Description |
| :--- | :--- | :--- | :--- |
| **[Notebook 1](#notebook-1-online-data-collection--web-scraping)** | Online Data Collection & Web Scraping | `requests`, `BeautifulSoup4`, CSS/XPath | Scraping static & dynamic HTML, inspecting HTTP headers, extracting tabular & nested metadata. |
| **[Notebook 2](#notebook-2-working-with-web-apis--algorithmic-auditing)** | REST APIs & LLM Integration | Google Books API, NYT API, Gemini API, `dotenv` | Querying web APIs, handling JSON payloads, rate-limiting, and text generation/auditing with LLMs. |
| **[Notebook 3](#notebook-3-browser-automation--platform-auditing)** | Browser Automation & Platform Audits | `selenium`, `chromedriver`, `pandas`, `plotly` | Automating user flows on dynamic web platforms (Dribbble), scraping user engagement, and measuring algorithmic feed bias. |
| **[Notebook 4](#notebook-4-agent-based-modelling-abm)** | Agent-Based Modeling & Simulation | `numpy`, `matplotlib`, OOP Python | Simulating airplane boarding and deboarding dynamics across various seating strategies and luggage constraints. |
| **[Notebook 5](#notebook-5-data-analysis-nlp--annotation-benchmarking)** | Text Analysis, NLP & Annotation Agreement | `nltk` (VADER), Gemini LLM, `pandas`, Cohen's & Fleiss's $\kappa$ | Rule-based geographic classification, multi-paradigm sentiment analysis on IMDB reviews, and inter-rater reliability. |

---

## 🔍 Detailed Notebook Breakdown

### [Notebook 1: Online Data Collection & Web Scraping](SC_Notebook1_NAME1_NAME2.ipynb)
Focuses on retrieving web pages and parsing structured information directly from HTML trees.

* **HTTP & Request Headers:**
  * Using Python’s `requests` library to fetch web pages (Wikipedia, Weather.gov).
  * Analyzing request and response headers (`User-Agent`, `Accept-Language`, cache controls).
  * Reverse-engineering URL structures and query parameters (Google, Yelp).
* **HTML Parsing with BeautifulSoup:**
  * Navigating the DOM tree using tag hierarchies, CSS classes, and element IDs.
  * Scraping temperature forecasts and multi-period extended forecasts from weather reports.
* **Platform Scraping:**
  * Extracting job postings and hiring company data from job portals (JobScout24).
  * Pagination, session cookies, and rate-limit avoidance for property platforms (ImmoScout24).

---

### [Notebook 2: Working with Web APIs & Algorithmic Auditing](SC_Notebook2_NAME1_NAME2.ipynb)
Explores consuming third-party RESTful APIs, securing credentials, and utilizing Generative AI for data auditing.

* **API Authentication & Secret Management:**
  * Securing API tokens with `.env` files and `python-dotenv` to prevent credential leaks.
* **Google Books API:**
  * Constructing complex query parameters (`intitle`, `inauthor`, `isbn`, categories).
  * Implementing graceful error handling for HTTP status codes (`4xx`, `5xx`).
  * Parsing nested JSON records, extracting book metadata, and handling missing fields (`NaN` imputation).
* **New York Times Article Search API:**
  * Time-series article trend tracking across 12-month spans.
  * Visualizing monthly keyword frequencies using `matplotlib`.
* **Google Gemini API & Algorithm Auditing:**
  * Automated job description generation via LLM prompt templating.
  * Designing audit frameworks to evaluate biases in algorithmic text outputs.

---

### [Notebook 3: Browser Automation & Platform Auditing](SC_Notebook3_NAME1_NAME2.ipynb)
Covers automated browser interactions on JavaScript-heavy platforms using Selenium and analyzing personalization/ranking algorithms.

* **Selenium Webdriver Automation:**
  * Configuring `chromedriver`, managing sessions, and handling privacy consent dialogs.
  * Programmatic login flows with credential injection and interaction simulation.
* **Data Extraction at Scale (Dribbble):**
  * Scraping engagement metrics (views, likes, saves, tags) and comment threads across 50+ posts.
  * Collecting recommendations from the "You might also like" algorithm.
* **Auditing Content Curation Algorithms:**
  * Comparing content distribution across sorting criteria: `Following` (personalized), `Popular`, and `New & Noteworthy`.
  * Measuring overlap coefficients and Jaccard similarity indices across feeds.
  * Identifying frequent comment patterns and engagement decay across rankings.
* **Platform Audit Implementation:**
  * Designing and running an empirical audit testing platform variance (e.g., location, login state).

---

### [Notebook 4: Agent-Based Modelling (ABM)](SC_Notebook4_NAME1_NAME2.ipynb)
Implements an agent-based simulation from scratch to study efficiency and bottleneck dynamics in passenger boarding and deboarding.

* **Airplane Cabin Modeling:**
  * Grid-based spatial model representing an Airbus A320 cabin (rows, seats, aisle, overhead bins).
  * Passenger state machine (`FIND_SEAT`, `LOAD_LUGGAGE`, `GO_TO_SEAT`, `MAKE_SPACE`, `SEATED`).
* **Boarding Strategies Tested:**
  * *Random* — Unstructured passenger entry.
  * *Back-to-Front (BtF)* — Boarding rear rows first.
  * *Window-Middle-Aisle (WMA)* — Seating from exterior columns inward to minimize seat interference.
  * *Precise (Steffen-like)* — Optimized column/row sequence.
* **Sensitivity Analysis:**
  * Evaluating the impact of hand luggage storage time ($T_{luggage} \in \{0, 1, 5\}$).
  * Multi-run Monte Carlo simulations across 100 random seeds reporting mean iterations and standard deviation ($\mu \pm \sigma$).
* **Deboarding Dynamics:**
  * Modeling egress rules comparing *Front Priority* vs. *Aisle Clearance (Back/Luggage Ready Priority)*.

---

### [Notebook 5: Data Analysis, NLP & Annotation Benchmarking](SC_Notebook5_NAME1_NAME2.ipynb)
Covers text processing, geographic feature inference, multi-method sentiment classification, and statistical inter-annotator evaluation.

* **Feature Inference from Email Domains:**
  * Rule-based heuristic classification mapping top-level and academic domain hashes to countries of residence.
  * Measuring coverage vs. precision trade-offs.
* **Multi-Paradigm Sentiment Labeling (IMDB Dataset):**
  * Sampling stratified reviews (`pos`, `neg`, `unsup`).
  * Triple annotation across:
    1. **Human Annotators:** Subjective manual Likert-scale classification.
    2. **LLM Zero-Shot Classifier:** Prompt-based classification using Gemini.
    3. **Lexicon-Based NLP:** Rule-based compound sentiment polarity via NLTK's VADER.
* **Scale Normalization & Inter-Rater Agreement:**
  * Thresholding continuous compound polarity scores to categorical Likert equivalents.
  * Calculating **Cohen's Kappa ($\kappa$)** for pairwise inter-annotator reliability.
  * Calculating **Fleiss's Kappa ($\kappa$)** to assess overall multi-rater agreement across categories and sentiment splits.

---

## 🛠️ Setup & Prerequisites

### 1. Environment Setup
Clone the repository and install the required dependencies:

```bash
git clone <your-repo-url>
cd <your-repo-folder>
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 2. Required Libraries
Key Python packages used throughout the course:
* **Web Scraping & APIs:** `requests`, `beautifulsoup4`, `selenium`, `python-dotenv`
* **Data Processing & Analysis:** `pandas`, `numpy`, `scikit-learn`
* **NLP & Text Mining:** `nltk`
* **Visualization:** `matplotlib`, `plotly`
* **LLM Integration:** `google-generativeai`

### 3. API Keys & Secrets
Create a `.env` file in the project root to store necessary API keys (ensure this file is listed in `.gitignore`):

```env
GOOGLE_BOOKS_API_KEY="your-google-books-api-key"
NY_TIMES_API_KEY="your-nyt-api-key"
GEMINI_API_KEY="your-gemini-api-key"
DRIBBLE_USERNAME="your-username"
DRIBBLE_PASSWORD="your-password"
```

### 4. Browser Automation
For Notebook 3, ensure you have **Google Chrome** installed along with the matching [ChromeDriver](https://googlechromelabs.github.io/chrome-for-testing/) binary added to your system path or project directory.

---

## ⚖️ Academic Integrity & Ethics
All scraping, API queries, and platform audits were executed adhering to research ethics principles, respecting rate limits and terms of service, and ensuring anonymization of personal credentials.
```

The generated `README.md` provides an end-to-end breakdown of the course concepts, a notebook-by-notebook directory of tools and methods, setup instructions, and guidance on API configurations.
