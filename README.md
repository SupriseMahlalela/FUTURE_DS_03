# 📊 Marketing Funnel Analysis Dashboard

## Project Overview

This project provides a complete marketing funnel analysis to identify conversion drop-offs, channel performance, and opportunities to improve lead-to-customer conversion using real e-commerce data.

**Dataset:** 30,000 user sessions with traffic source, device, demographic, and conversion data.

---

# 🎯 Key Business Questions Answered

| Question | Answer |
|----------|--------|
| Where are users dropping off? | 81.4% drop between engagement and conversion |
| Which channel performs best? | Referral (10.4% purchase rate) |
| What is lead-to-customer rate? | 9.97% (2,992 purchases from 30,000 sessions) |
| How to improve conversion? | Cart abandonment emails, mobile optimization, channel reallocation |

---

# 📊 Key Findings

## 1. Conversion Funnel & Drop-offs

| Stage | Users | Drop-off | Status |
|-------|-------|----------|--------|
| Sessions | 30,000 | - | - |
| Engaged (No Bounce) | 24,327 | 18.9% | ✅ Good |
| Converted | 4,535 | 81.4% | 🔴 Critical |
| Purchased | 2,992 | 34.0% | 🟡 Moderate |

### 🔍 Critical Finding

81.4% of engaged users drop off before converting. This is the biggest opportunity for improvement.

---

## 2. Channel Performance

| Channel | Purchase Rate | Revenue | Rank |
|---------|---------------|---------|------|
| Referral | 10.4% | $80,617 | 🏆 #1 |
| Organic | 10.1% | $412,922 | #2 |
| Paid | 9.8% | $150,138 | #3 |
| Social | 9.6% | $142,580 | #4 |

---

## 3. Device Performance

| Device | Purchase Rate | Sessions |
|--------|---------------|----------|
| Tablet | 10.2% | 3,039 |
| Desktop | 10.0% | 8,953 |
| Mobile | 9.9% | 18,008 |

---

## 4. Demographic Insights

| Segment | Purchase Rate |
|---------|---------------|
| Old Adults | 10.1% |
| Adults | 9.9% |
| Teenage | 9.9% |
| Female | 10.0% |
| Male | 9.9% |

---

# 📈 Visualizations Included

| # | Visualization | Purpose |
|---|---------------|---------|
| 1 | Funnel Chart | Show drop-off at each stage |
| 2 | Channel Bar Chart | Compare channel performance |
| 3 | Revenue Pie Chart | Revenue distribution by channel |
| 4 | Pages Line Chart | Pages visited vs conversion |
| 5 | Device Bar Chart | Performance by device type |
| 6n| Geographic Chart | Top 10 countries performance |
| 7 | Complete Dashboard | Combined executive dashboard |

---

# 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| Python | Data cleaning & analysis |
| Pandas | Data manipulation |
| Matplotlib | Static visualizations |
| Power BI | Interactive dashboard |
| DAX | Measures & calculations |

---

# 📦 Installation & Setup

## Prerequisites

- Python 3.8 or higher
- Power BI Desktop (Free)
- Jupyter Notebook

### Download Links

- [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/)
- [Python](https://www.python.org/downloads/)
- [Jupyter Notebook Guide](https://jupyter.org/install)

---

## 📥 Install Python Libraries

```bash
pip install pandas numpy matplotlib jupyter dask[dataframe]
```

---

## 📂 Clone Repository

```bash
git clone https://github.com/SupriseMahlalela/FUTURE_DS_03

```

---

## ▶️ Run Analysis

```bash
jupyter notebook
```

Then open and run:

- `MarkettingFunnel EDA.ipynb`
- `FunnelVisualisation.ipynb`

---

# 📊 Power BI Dashboard

## Steps

1. Download and install Power BI Desktop
2. Open `ConversionDashboard.pbix`
3. Refresh data connection
4. Use slicers to filter dashboard insights

### Available Filters

- Traffic Source
  - Organic
  - Paid
  - Social
  - Referral

- Device Type
  - Desktop
  - Mobile
  - Tablet

- Location
- Country

---

# 📐 Key DAX Measures Used in Power BI

```dax
// Basic Metrics
Total Sessions =
COUNTROWS(CleanedSpeakerData_fixed)

Total Revenue =
SUMX(
    CleanedSpeakerData_fixed,
    VALUE(CleanedSpeakerData_fixed[revenue_$])
)

Total Purchases =
CALCULATE(
    COUNTROWS(CleanedSpeakerData_fixed),
    CleanedSpeakerData_fixed[conversion_type] = "Purchase"
)


// Conversion Rates
Purchase Rate =
DIVIDE([Total Purchases], [Total Sessions])

Bounce Rate =
DIVIDE(
    CALCULATE(
        COUNTROWS(CleanedSpeakerData_fixed),
        CleanedSpeakerData_fixed[bounce_flag] = 1
    ),
    [Total Sessions]
)


// Drop-off Rates
Drop Engaged to Converted =
DIVIDE(
    [Engaged Sessions] - [Converted Sessions],
    [Engaged Sessions]
)


// Channel Performance
Channel Purchase Rate =
VAR CurrentChannel =
    SELECTEDVALUE(CleanedSpeakerData_fixed[traffic_source])

RETURN
DIVIDE(
    CALCULATE(
        [Total Purchases],
        CleanedSpeakerData_fixed[traffic_source] = CurrentChannel
    ),
    CALCULATE(
        [Total Sessions],
        CleanedSpeakerData_fixed[traffic_source] = CurrentChannel
    )
)


// Device Performance
Device Purchase Rate =
VAR CurrentDevice =
    SELECTEDVALUE(CleanedSpeakerData_fixed[device_type])

RETURN
DIVIDE(
    CALCULATE(
        [Total Purchases],
        CleanedSpeakerData_fixed[device_type] = CurrentDevice
    ),
    CALCULATE(
        [Total Sessions],
        CleanedSpeakerData_fixed[device_type] = CurrentDevice
    )
)
```

---

# 💡 Recommendations

## Priority 1: Fix Engagement → Conversion Drop (81.4%)

| Action | Expected Impact |
|--------|----------------|
| Add exit-intent popups | +10% |
| Improve CTAs on product pages | +5% |
| Implement cart abandonment emails | +15% |

---

## Priority 2: Optimize Channel Strategy

### Increase Investment
- Referral channel (+30% budget)

### Maintain
- Organic channel performance

### Optimize
- Paid channel through A/B testing

### Investigate
- Social channel targeting and landing pages

---

## Priority 3: Mobile Optimization

- Simplify mobile checkout flow
- Add mobile-specific CTA buttons
- Improve mobile page load speed
- Optimize responsive design experience

---

# 📈 Projected Impact

| Metric | Current | Target | Improvement |
|--------|---------|---------|-------------|
| Lead-to-Customer Rate | 9.97% | 12.97% | +30% |
| Cart Abandonment | 81.4% | 65% | -20% |
| Revenue | $786,256 | $936,000 | +$150K |

---

# 📁 Project Structure

```text
FUTURE_DS_03/
│
├── data/
│   └── CleanedSpeakerData_fixed.csv
│
├── notebooks/
│   ├── 01_complete_analysis.ipynb
│   └── 02_visualizations.ipynb
│
├── powerbi/
│   └── ConversionDashboard.pbix
│
├── images/
│   └── dashboard_screenshot.png
│
└── README.md
```

---

# 📝 Author

## Suprise Mahlalela

- GitHub: https://github.com/SupriseMahlalela
- Repository: https://github.com/SupriseMahlalela/FUTURE_DS_03

### Project Purpose
Marketing Analytics Portfolio Project

### Date
May 2026

---

# 🙏 Acknowledgments

- Dataset provided for marketing analytics learning purposes
- Built as a complete end-to-end analytics portfolio project
- Special thanks to the open-source community and analytics ecosystem

---

# 📧 Contact

For questions, suggestions, or feedback, please open an issue on the GitHub repository or email  mahlalelasuprise57@gmail.com.


---

# 🔗 External Resources

- [Power BI Desktop Download](https://powerbi.microsoft.com/en-us/desktop/)
- [Python Download](https://www.python.org/downloads/)
- [Jupyter Notebook Installation Guide](https://jupyter.org/install)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [DAX Reference Guide](https://learn.microsoft.com/en-us/dax/)

---

<div align="center">

## ⭐ If this project helped you, please give it a star on GitHub! ⭐

### Built with Python, Power BI, and Data Analytics

</div>
