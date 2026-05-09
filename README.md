# 📊 Marketing Funnel Analysis Dashboard

## Project Overview

This project provides a complete marketing funnel analysis to identify conversion drop-offs, channel performance, and opportunities to improve lead-to-customer conversion using real e-commerce data.

**Dataset:** 30,000 user sessions with traffic source, device, demographic, and conversion data.

---

## 🎯 Key Business Questions Answered

| Question | Answer |
|----------|--------|
| Where are users dropping off? | 81.4% drop between engagement and conversion |
| Which channel performs best? | Referral (10.4% purchase rate) |
| What is lead-to-customer rate? | 9.97% (2,992 purchases from 30,000 sessions) |
| How to improve conversion? | Cart abandonment emails, mobile optimization, channel reallocation |

---

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

## 📈 Visualizations Included

| # | Visual | Purpose |
|---|--------|---------|
| 1 | Funnel Chart | Show drop-off at each stage |
| 2 | Channel Bar Chart | Compare channel performance |
| 3 | Revenue Pie Chart | Revenue distribution by channel |
| 4 | Pages Line Chart | Pages visited vs conversion |
| 5 | Device Bar Chart | Performance by device type |
| 6 | Demographic Chart | Age & gender comparison |
| 7 | Engagement Heatmap | Pages vs bounce relationship |
| 8 | Geographic Chart | Top 10 countries performance |
| 9 | Complete Dashboard | All key visuals combined |

---

## 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| Python | Data cleaning & analysis |
| Pandas | Data manipulation |
| Matplotlib | Static visualizations |
| Power BI | Interactive dashboard |
| DAX | Measures & calculations |

---

## 📦 Installation & Setup

### Prerequisites

```bash
Python 3.8+
Power BI Desktop (free)
