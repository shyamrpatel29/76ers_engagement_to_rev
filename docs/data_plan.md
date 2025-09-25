# Data Plan — 76ers Engagement → Revenue

## 1. Fan Engagement Data
**Source:** Reddit (`r/sixers`), Twitter/X  
**Fields:** post ID, date, author, text, upvotes/likes, comment count  
**Method:** Reddit API (PRAW), Twitter via `snscrape` (if API limits)  
**Messiness:** slang, sarcasm, duplicate posts, deleted threads  
**Storage:** `data/raw/reddit/`, `data/raw/twitter/`

---

## 2. Ticket Market Data
**Source:** StubHub / Ticketmaster resale listings  
**Fields:** listing price, section, row, availability, timestamp  
**Method:** Selenium scraper (dynamic JS rendering)  
**Messiness:** bot listings, rapid price changes, inconsistent seat labeling  
**Storage:** `data/raw/tickets/`

---

## 3. Game + Player Data
**Source:** NBA Stats API (`nba_api` Python package)  
**Fields:** game ID, date, opponent, score, player availability, injuries  
**Method:** API calls (JSON to pandas)  
**Messiness:** delayed injury reports, last-minute roster changes  
**Storage:** `data/raw/nba_api/`

---

## 4. Digital Interest
**Source:** Google Trends (PyTrends library)  
**Fields:** search volume for queries like “76ers tickets”, “Joel Embiid highlights”  
**Method:** API wrapper  
**Messiness:** normalized values (0–100), not raw counts  
**Storage:** `data/raw/trends/`

---

## 5. Transformations Needed
- Convert timestamps to game dates  
- Normalize text → lowercase, remove stopwords, tokenize  
- Map ticket listings → face value vs resale markup  
- Join sentiment/volume to game IDs  
- Create **Hype Index** feature from combined sources

---

## 6. ETL Workflow
- **Extract:** Selenium/API jobs (saved to `data/raw/`)  
- **Transform:** Python scripts → clean and structure data (`data/stage/`)  
- **Load:** Aggregated tables → ready for modeling (`data/mart/`)
