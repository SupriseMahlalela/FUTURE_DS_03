📊 Marketing Funnel Analysis Dashboard
Project Overview
This project provides a complete marketing funnel analysis to identify conversion drop-offs, channel performance, and opportunities to improve lead-to-customer conversion using real e-commerce data.

Dataset: 30,000 user sessions with traffic source, device, demographic, and conversion data.

🎯 Key Business Questions Answered.

* Where are users dropping off? >> 81.4% drop between engagement and conversion.
* Which channel performs best? >> Referral (10.4% purchase rate)
* What is lead-to-customer rate? >> 9.97% (2,992 purchases from 30,000 sessions)
* How to improve conversion? >> Cart abandonment emails, mobile optimization, channel reallocation.


## 📊 Key Findings

### 1. Conversion Funnel & Drop-offs

| Stage | Users | Drop-off | Status |
|-------|-------|----------|--------|
| Sessions | 30,000 | - | - |
| Engaged (No Bounce) | 24,327 | 18.9% | ✅ Good |
| Converted | 4,535 | 81.4% | 🔴 Critical |
| Purchased | 2,992 | 34.0% | 🟡 Moderate |

**Critical Finding:** 81.4% of engaged users drop off before converting. This is the biggest opportunity for improvement.

---

### 2. Channel Performance

| Channel | Purchase Rate | Revenue | Rank |
|---------|---------------|---------|------|
| Referral | 10.4% | $80,617 | 🏆 #1 |
| Organic | 10.1% | $412,922 | #2 |
| Paid | 9.8% | $150,138 | #3 |
| Social | 9.6% | $142,580 | #4 |

---

### 3. Device Performance

| Device | Purchase Rate | Sessions |
|--------|---------------|----------|
| Tablet | 10.2% | 3,039 |
| Desktop | 10.0% | 8,953 |
| Mobile | 9.9% | 18,008 |

---

### 4. Demographic Insights

| Segment | Purchase Rate |
|---------|---------------|
| Old Adults | 10.1% |
| Adults | 9.9% |
| Teenage | 9.9% |
| Female | 10.0% |
| Male | 9.9% |

---

📈 Visualizations Included
1. Funnel Chart
* Show drop-off at each stage.
2. Channel Bar Chart
* Compare channel performance.
3. Revenue Pie Chart.
* Revenue distribution by channel.
4. Pages Line Chart
* Pages visited vs conversion.
5. Device Bar Chart
* Performance by device type.
6. Demographic Chart.
* Age & gender comparison.
7. Engagement Heatmap.
* Pages vs bounce relationship.
8. Geographic Chart.
* Top 10 countries performance
9. Complete Dashboard.
* All key visuals combined


## 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| Python | Data cleaning & analysis |
| Pandas | Data manipulation |
| Matplotlib | Static visualizations |
| Power BI | Interactive dashboard |
| DAX | Measures & calculations |

---

## 📦 Setup

**Install dependencies:**

pip install pandas numpy matplotlib jupyter dask[dataframe]

📦 Installation & Setup

Prerequisites

bash
Python 3.8+
Power BI Desktop (free)
Python Setup
bash
# Clone repository
git clone [your-repo-link]
cd marketing-funnel-analysis
git clone [https://github.com/SupriseMahlalela/FUTURE_DS_03]


# Install dependencies
pip install -r requirements.txt
requirements.txt:
- pandas==2.0.3
- numpy==1.24.3
- matplotlib==3.7.1
- jupyter==1.0.0
- dask[dataframe]==2023.6.0
# Run Analysis
bash

txt
pandas==2.0.3
numpy==1.24.3
matplotlib==3.7.1
matplotlib==3.7.1 
jupyter==1.0.0
dask[dataframe]==2023.6.0
Run Analysis
bash
# Launch Jupyter Notebook
jupyter notebook

# Run notebooks in order:
01_complete_analysis.ipynb
01_complete_analysis.ipynb||
02_visualizations.ipynb
Power BI Dashboard
Download Power BI Desktop (free)

Open powerbi/funnel_dashboard.pbix
Open powerbi/ConversionDashboard.pbix

Refresh data connection

Use slicers to filter:

Traffic Source (Organic, Paid, Social, Referral)

Device Type (Desktop, Mobile, Tablet)

Age Group (Teenage, Adult, Old)
Location (Tokyo, Beijing, Moscow, Lyon)

Country

📊 Key DAX Measures Used in Power BI
dax
/Basic Metrics7/
Total Sessions = COUNTROWS(CleanedSpeakerData_fixed)
Total Revenue = SUMX(CleanedSpeakerData_fixed, VALUE(CleanedSpeakerData_fixed[revenue_$]))
Total Purchases = CALCULATE(COUNTROWS(CleanedSpeakerData_fixed), CleanedSpeakerData_fixed[conversion_type] = "Purchase")

// Conversion Rates (returns decimal, format as Percentage)
Purchase Rate = DIVIDE([Total Purchases], [Total Sessions])
Bounce Rate = DIVIDE(CALCULATE(COUNTROWS(CleanedSpeakerData_fixed), CleanedSpeakerData_fixed[bounce_flag] = 1), [Total Sessions])

// Drop-off Rates
Drop Engaged to Converted = DIVIDE([Engaged Sessions] - [Converted Sessions], [Engaged Sessions])

// Channel Performance
Channel Purchase Rate = 
VAR CurrentChannel = SELECTEDVALUE(CleanedSpeakerData_fixed[traffic_source])
RETURN
DIVIDE(
CALCULATE([Total Purchases], CleanedSpeakerData_fixed[traffic_source] = CurrentChannel),
CALCULATE([Total Sessions], CleanedSpeakerData_fixed[traffic_source] = CurrentChannel)
)
💡 Recommendations
Priority 1: Fix Engagement → Conversion Drop (81.4%)
Action	Expected Impact
Add exit-intent popups	+10%
Improve CTAs on product pages	+5%
Implement cart abandonment emails	+15%
Priority 2: Optimize Channel Strategy
text
Budget Reallocation:
├── Increase: Referral (+30% budget)
├── Maintain: Organic (current spend)
├── Optimize: Paid (A/B test creatives)
└── Investigate: Social (audit targeting)
Priority 3: Mobile Optimization
Mobile converts at 9.9% vs Desktop 10.0%

Simplify mobile checkout flow

Add mobile-specific CTAs

📈 Projected Impact
Metric	Current	Target	Improvement
Lead-to-Customer Rate	9.97%	12.97%	+30%
Cart Abandonment	81.4%	65%	-20%
Revenue	$786,256	$936,000	+$150K

📁 Generated Reports (CSV Files)
After running notebooks, these files are created:

File	Content
channel_performance.csv	Purchase rate & revenue by channel
demographic_analysis.csv	Conversion by age & gender
funnel_analysis_final_report.csv	Complete metrics summary
funnel_summary_final.csv	Key KPIs
🔧 Data Types Used (Critical for Accuracy)
Column	Data Type	Why
user_id, session_id	Text	IDs, not math
demographic_age	Whole Number	For calculations
revenue_$	Decimal Number	Money values
conversion_flag	Whole Number (0/1)	Flags for counting
bounce_flag	Whole Number (0/1)	Flags for counting
pages_visited	Whole Number	Counts
traffic_source	Text	Categories
device_type	Text	Categories
timestamp	Date/Time	Time analysis
Important: Rate measures return decimal (0.0997), then format as Percentage in Power BI (shows 9.97%). Never multiply by 100 in DAX.


📝 Author
[Suprise Mahlalela]

Purpose: Marketing Analytics Portfolio Project

Date: May 2026

🙏 Acknowledgments
Dataset provided for marketing analytics learning

Built as complete end-to-end analytics project

📧 Contact
For questions or feedback: [mahlalelasuprise57@gmail.com]

🔗 Quick Navigation
Analysis Notebook

Visualizations Notebook

Power BI Dashboard

⭐ If you find this project helpful, please give it a star!

📝 Author
Suprise Mahlalela

GitHub: https://github.com/SupriseMahlalela

Project Repository: https://github.com/SupriseMahlalela/FUTURE_DS_03

Purpose: Marketing Analytics Portfolio Project

Date: May 2026

🙏 Acknowledgments
Dataset provided for marketing analytics learning purposes

Built as a complete end-to-end analytics portfolio project

Special thanks to open-source tools and community

📧 Contact
For questions or feedback, please open an issue on the GitHub repository.

🔗 External Resources
Power BI Desktop Download

Python Download

Jupyter Notebook Installation Guide

Pandas Documentation

DAX Reference Guide

<div align="center">
⭐ If this project helped you, please give it a star on GitHub! ⭐

Built with Python, Power BI, and Data Analytics

</div> ```
