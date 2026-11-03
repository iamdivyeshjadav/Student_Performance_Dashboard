<div align="center">

# -- ! Student Performance Dashboard ! --
### *Interactive Power BI Dashboard for Academic & Behavioral Analytics*

[![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Measures%20%26%20KPIs-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](https://learn.microsoft.com/en-us/dax/)
[![Data Model](https://img.shields.io/badge/Data%20Model-6%20Tables-4CAF50?style=for-the-badge&logo=databricks&logoColor=white)](https://powerbi.microsoft.com/)
[![Analytics](https://img.shields.io/badge/Analytics-Academic%20%2B%20Behavioral-9C27B0?style=for-the-badge&logo=googleanalytics&logoColor=white)](https://powerbi.microsoft.com/)

<br/>

> *"Data tells the story of every student — a good dashboard makes sure someone listens."*

</div>

---

## 📋 Table of Contents

- [📌 Overview](#-overview)
- [🎯 Problem Statement](#-problem-statement)
- [✨ Key Features](#-key-features)
- [🏗️ Project Structure](#️-project-structure)
- [🔄 Project Workflow](#-project-workflow)
- [🎓 Part A — Academic Page](#-part-a--academic-page)
- [🧭 Part B — Behavioral Page](#-part-b--behavioral-page)
- [🛠️ Tech Stack](#️-tech-stack)
- [📈 Results & Insights](#-results--insights)
- [🏆 Advantages](#-advantages)
- [📄 License](#-license)
- [👤 Author](#-author)
- [🙏 Acknowledgements](#-acknowledgements)

---

## 📌 Overview

The **Student Performance Dashboard** is an interactive, two-page **Power BI** report built for school administrators. It combines exam scores, attendance and behavior records into one view, so staff can see how students, classes and subjects are performing without writing a single query. The report is designed at **1920 × 1080** with a light theme, gold icons, KPI cards and a side navigator for switching pages.

This project is designed to:
- Track **academic performance** by subject, class, term and exam type
- Monitor **attendance** and **behavior** patterns across classes and months
- Identify **top and bottom performing students** with rank and category
- Practice **data modeling**, **DAX measures** and **dashboard design** in Power BI

---

## 🎯 Problem Statement

> **Objective:** Build an interactive dashboard that gives school administrators a single view of student academic results, attendance and behavior.

School data usually sits in separate sheets for scores, attendance and discipline, which makes it hard to spot struggling students or problem trends early. This dashboard brings them together in one data model, with slicers so any view can be narrowed down by class, section, subject or term.

| 📂 Table | 📄 Type | 🔍 Description |
|----------|---------|----------------|
| Students | Dimension | Student name, class, section and class group |
| Scores | Fact | Exam records by subject, term, exam type and grade |
| Attendance | Fact | Daily attendance used to compute attendance % |
| Behavior | Fact | Behavior records with type and sentiment |
| Calendar | Dimension | Date table for monthly trend analysis |
| MeasureTable | Measures | Holds all DAX measures and KPIs |

The goal is to demonstrate **end-to-end BI skills** — from data model to measures to a clean, navigable report.

---

## ✨ Key Features

| Feature | Description |
|--------|-------------|
| 📑 **2 Report Pages** | Academic and Behavioral pages with a shared layout and page navigator |
| 🎛️ **4 Slicers per Page** | Filter by Class, Section, Subject and Term |
| 🔢 **KPI Cards** | Total Students, Pass Rate, Avg Score %, Attendance %, Behavior Count, Positive Behavior %, Behavior Alerts |
| 📊 **Subject vs Class Comparison** | Clustered column chart of average score by subject and class group |
| 📈 **Term Trend** | Line chart of average score by term, split by exam type |
| 🏅 **Top & Bottom Students** | Table with student rank, average %, and performance category |
| 🍩 **Distribution Donuts** | Grade distribution (Academic) and behavior type distribution (Behavioral) |
| 🗓️ **Monthly Behavior Trend** | Area chart of positive vs negative behavior over time |
| 💡 **Key Insights Panel** | Written takeaways placed beside the behavior charts |
| 🔒 **Focused Interactions** | Charts do not cross-filter the KPI cards, so headline numbers follow the slicers only |

---

## 🏗️ Project Structure

```
📦 student-performance-dashboard/
│
├── 📄 Student_Perfromance_Dashboard.pbix   ← Power BI report (data model + 2 pages)
│
└── 📄 README.md                            ← Project documentation
```

---

## 🔄 Project Workflow

```
Raw Student Data
      │
      ▼
┌─────────────────────────────┐
│   Load Tables               │  ← Students / Scores / Attendance / Behavior / Calendar
└────────────┬────────────────┘
             │
             ▼
┌─────────────────────────────┐
│   Build Data Model          │  ← Relationships + MeasureTable (DAX)
└────────────┬────────────────┘
             │
     ┌───────┴────────┐
     ▼                ▼
┌─────────────┐   ┌──────────────────┐
│  Page 1     │   │     Page 2       │
│  Academic   │   │   Behavioral     │
└──────┬──────┘   └────────┬─────────┘
       │                   │
       ▼                   ▼
┌─────────────────────────────┐
│  Slicers: Class · Section   │
│  Subject · Term             │
└────────────┬────────────────┘
             │
             ▼
   KPI Cards + Charts Update
             │
             ▼
   Insights for School Admin ✅
```

---

## 🎓 Part A — Academic Page

### 📝 1. What does this page show?

The **Academic Analytics** page answers: *how are students performing, in which subjects and classes, and who needs attention?* It opens with four KPI cards and three charts, followed by a student ranking table.

---

### 🗺️ 2. Visuals — Overview

| Visual | Type | Fields Used |
|--------|------|-------------|
| 🔢 Total Students | KPI Card | `Total Students` |
| ✅ Pass Rate | KPI Card | `Pass Rate` |
| 📊 Avg Score % | KPI Card | `Avg Score %` |
| 🗓️ Attendance % | KPI Card | `Attendance %` |
| 📊 Average Score by Subject and Class | Clustered Column | `Subject`, `Class Group`, `Avg Score %` |
| 🍩 Grade Distribution | Donut | `Grade`, `Exam Records` |
| 📈 Trend by Term | Line Chart | `Term`, `ExamType`, `Avg Score %` |
| 🏅 Top & Bottom Students | Table | `Student Rank`, `Name`, `Class`, `Student Avg %`, `Performance Category` |

---

### 🎛️ 3. Slicers

> Four slicers sit along the top and filter every visual on the page.

| Slicer | Source Column |
|--------|---------------|
| Class | `Students[Class]` |
| Section | `Students[Section]` |
| Subject | `Scores[Subject]` |
| Term | `Scores[Term]` |

---

### 🏅 4. Top & Bottom Students

> Ranks students by their average percentage and labels each with a performance category.

**Columns shown:**
```
Student Rank | Name | Class | Student Avg % | Performance Category
```

---

## 🧭 Part B — Behavioral Page

### 🔍 5. What does this page show?

The **Behavioral Analytics** page answers: *how often do behavior incidents occur, which classes are affected, and is the trend improving?* It uses the same four slicers as the Academic page.

---

### 🗺️ 6. Visuals — Overview

| Visual | Type | Fields Used |
|--------|------|-------------|
| 🔢 Behavior Count | KPI Card | `Behavior Count` |
| 👍 Positive Behavior % | KPI Card | `Positive Behavior %` |
| 🚨 Behavior Alerts | KPI Card | `Behavior Alerts` |
| 🗓️ Attendance % | KPI Card | `Attendance %` |
| 📊 Behavior Count by Class | Clustered Column | `Class Label`, `Sentiment`, `Behavior Count` |
| 🍩 Behavior Type Distribution | Donut | `BehaviorType`, `Behavior Count` |
| 📈 Monthly Behavior Trend | Area Chart | `Date` (Calendar), `Sentiment`, `Behavior Count` |
| 💡 Key Insights | Text Panel | Written summary of the findings |

---

### 💡 7. Key Insights Panel

> Findings written on the dashboard itself:

```
• 39.9% of records are positive; 60.1% need attention.
• Disruptive is the most frequent type (20.5% of records).
• Class 1 has the most records (692); Class 7 the fewest (428).
• Best month ... Apr 25 (43% of that month).
• Attendance averages 90.0% with 9,952 absent days.
```

---

## 🛠️ Tech Stack

| Tool | Version | Purpose |
|------|---------|---------|
| 📊 **Power BI Desktop** | Latest | Report authoring and data modeling |
| 🧮 **DAX** | Built-in | Measures such as Pass Rate, Avg Score %, Attendance %, Student Rank |
| 🗃️ **Data Model** | 6 tables | Students, Scores, Attendance, Behavior, Calendar, MeasureTable |
| 🎨 **Fluent 2 Theme** | Built-in | Base theme with a light `#EEF1F6` page background |
| 🧭 **Page Navigator** | Built-in | Switching between Academic and Behavioral pages |
| 🖼️ **Custom Icons** | PNG | Gold and white icons for the header and sections |

---

## 📈 Results & Insights

After opening the report, the following outputs are available:

- ✅ **Academic Overview** — Pass rate, average score and attendance at a glance
- 📊 **Subject & Class Comparison** — Average scores by subject for each class group
- 📈 **Term Trend** — Score movement across terms for each exam type
- 🏅 **Student Ranking** — Top and bottom students with rank and category
- 🧭 **Behavior Monitoring** — Behavior count, positive share and alerts by class and month
- 🗓️ **Attendance** — Average attendance of **90.0%** with **9,952** absent days

---

## 🏆 Advantages

| Advantage | Detail |
|-----------|--------|
| 🎓 **Single View** | Scores, attendance and behavior in one report |
| 🎛️ **Easy Filtering** | Class, Section, Subject and Term slicers on both pages |
| 🔄 **Reusable Model** | A dedicated MeasureTable keeps all DAX measures in one place |
| 👀 **Early Warning** | Top/bottom ranking and behavior alerts highlight students who need support |
| 🖥️ **Clean Layout** | Consistent 1920 × 1080 design with KPI cards and a page navigator |
| 🧪 **Extensible** | Easy to add new pages, such as Attendance or Teacher analysis |
| 📖 **Readable Insights** | Key insights written directly on the dashboard |
| 🛡️ **Stable KPIs** | Headline cards respond to slicers only, not to chart clicks |

---


## Academic page
<img src="Icons/Academic page.png">

---

## Behavioral page

<img src="Icons/Behavioral page.png">

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for full details.

```
MIT License — Free to use, modify, and distribute with attribution.
```

---

## 👤 Author

<div align="center">

### Divyesh Jadav

[![GitHub](https://img.shields.io/badge/GitHub-yourhandle-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yourhandle)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/your-profile/)

> *"Every dashboard starts with a question — and ends with a better decision."*

**🎓 Role:** Data Analyst | Power BI Enthusiast \
**📍 Location:** India\
**🛠️ Skills:** Power BI · DAX · Data Modeling · Dashboard Design · Data Visualization

</div>

---

## 🙏 Acknowledgements

Special thanks to the following resources and communities that made this project possible:

- 📚 [Power BI Documentation](https://learn.microsoft.com/en-us/power-bi/) — Official Power BI reference
- 🧮 [DAX Guide](https://dax.guide/) — Complete DAX function reference
- 🎨 [Power BI Report Design Guidance](https://learn.microsoft.com/en-us/power-bi/guidance/) — Layout and design best practices
- 🖥️ [Microsoft Learn — Power BI](https://learn.microsoft.com/en-us/training/powerplatform/power-bi) — Beginner to advanced courses
- 💬 [Power BI Community](https://community.fabric.microsoft.com/) — Problem-solving support
- 📖 [Kaggle Learn](https://www.kaggle.com/learn) — Data and analytics courses

---

<div align="center">

---

*Made with ❤️ and ☕ — Last updated: 3 November, 2026*

</div>
