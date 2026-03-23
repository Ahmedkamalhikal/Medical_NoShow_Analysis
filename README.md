# 🏥 Medical Appointment No-Show Analysis
### Power BI Dashboard · Brazil 2016 · KaggleV2 Dataset

![Dashboard Preview](https://github.com/Ahmedkamalhikal/Medical_NoShow_Analysis/blob/main/Rec1.gif)

---

## 📌 Overview

Analysis of **110,000+ medical appointments** from Brazil (2016) to uncover the key factors behind patient no-shows. Built end-to-end in **Power BI** — covering Power Query data cleaning, DAX measures, and a 3-page interactive report.

**Dataset Source**: [KaggleV2 — Medical Appointment No Shows](https://www.kaggle.com/datasets/rohitrox/healthcare-provider-fraud-detection-analysis)

---

## 🔧 Data Preparation

Key engineered columns added in Power Query:

| Column | Purpose |
|---|---|
| `LeadDays` | Days between booking and appointment |
| `AppointmentDayOfWeek` | Weekday pattern analysis |
| `IsWeekend` / `IsWeekendLabel` | Weekend vs weekday segmentation |
| `AgeGroup` / `AgeGroupOrder` | Demographic segmentation with correct sort |
| `NoShowBinary` | Numeric target (1 = no-show) for DAX |
| `ComorbidityCount` | Sum of patient health condition flags |
| `ScholarshipLabel` | Readable legend labels |

---

## 📊 Key DAX Measures

```dax
No-Show Rate = DIVIDE([Total No-Shows], [Total Appointments], 0)

Avg Lead Days (No-Shows) = CALCULATE(AVERAGE(Appointments[LeadDays]), Appointments[NoShowBinary] = 1)

No-Show Rate (Male) = CALCULATE([No-Show Rate], Appointments[Gender] = "M")

SMS Impact = [No-Show Rate (No SMS)] - [No-Show Rate (SMS)]

% With Comorbidity = DIVIDE(CALCULATE([Total Patients], Appointments[HasComorbidity] = 1), [Total Patients], 0)
```

---

## 📋 Report Pages

- **Page 1 — Overview**: KPI cards, no-show rate by day of week, over time, by age group, donut chart
- **Page 2 — No-Show Analysis**: No-show rate by lead days, gender, neighbourhood (Top 10), weekday vs weekend
- **Page 3 — Patient Demographics**: Age distribution, gender split, patient count by neighbourhood, scholarship breakdown

---

## 💡 Key Insights

- **20.2% overall no-show rate** — 1 in 5 appointments is missed
- **Longer lead days = higher no-show rate** — same-day bookings have the lowest rates
- **Saturday has the highest no-show rate** among all weekdays
- **SMS reminders measurably reduce no-shows**
- **Female patients make up ~65%** of all appointments

---

## 🚀 How to Use

1. Download the `.pbix` file from this repository
2. Open with **Power BI Desktop** (free from Microsoft)
3. All data is embedded — no additional setup needed

---

## 👤 Author

**Ahmed Kamal Hikal** · [@Ahmedkamalhikal](https://github.com/Ahmedkamalhikal)

*Dataset credit: [Kaggle — KaggleV2 Medical Appointment No Shows](https://www.kaggle.com/datasets/rohitrox/healthcare-provider-fraud-detection-analysis)*
