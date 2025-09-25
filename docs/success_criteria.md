# Success Criteria — 76ers Engagement → Revenue

## 1. Technical Success
- ✅ Automated ETL pipeline built with Python + Selenium to scrape fan engagement and ticket market data.  
- ✅ Data stored locally in `data/raw/`, then cleaned into `data/stage/` and transformed into `data/mart/`.  
- ✅ Reproducible workflows (scripts + Jupyter notebooks) that can be rerun without manual tweaks.  
- ✅ Version-controlled repo with clear folder structure and documentation.

## 2. Analytical Success
- ✅ Construct a composite **Hype Index** that blends:
  - Fan sentiment (Reddit/Twitter)  
  - Engagement volume (posts/comments)  
  - Ticket resale markup and availability  
  - Player availability (injuries/suspensions)  
  - Opponent strength / rivalry flags
- ✅ Build predictive models linking hype index + game factors → ticket revenue & attendance.  
- ✅ Target model accuracy: >75% on held-out games (using RMSE/MAE for revenue, accuracy for classification like “sellout vs not”).  
- ✅ Identify at least 3 games where hype was high but revenue underperformed (“hype–revenue gap”).

## 3. Business Success
- ✅ Provide **actionable recommendations** for the Sixers’ business side:
  - Pricing adjustments (dynamic ticketing)  
  - Marketing pushes for high-hype / low-conversion games  
  - Sponsorship valuation tied to hype signals
- ✅ Quantify potential revenue impact if recommendations were applied (e.g., “could have recaptured $450K in missed ticket sales”).  
- ✅ Final deliverables:  
  - Dashboard (Tableau or Streamlit)  
  - Slide deck (executive-ready, pyramid principle)  
  - GitHub repo as a polished case study

---

## 🎯 Definition of Done
The project is successful if:
- The repo shows a **working pipeline** from raw scraping → cleaned data → modeling → visualization.  
- The analysis yields **measurable insights** on hype-to-revenue conversion.  
- The deliverables can be presented to both **technical peers (code, ETL)** and **non-technical stakeholders (dashboards, recommendations)**.  
