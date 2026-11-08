# Music_streaming_plateform
# 🎵 Music Streaming Platform Analytics Dashboard

An interactive **Power BI** dashboard that explores how listeners around the world use music streaming platforms: who they are, what they listen to, when they listen, and how engaged they are.

> **File:** `Music_streaming_plateform.pbix`

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Dataset](#-dataset)
- [Dashboard Pages](#-dashboard-pages)
- [Key Metrics (KPIs)](#-key-metrics-kpis)
- [Data Preparation](#-data-preparation)
- [Tools & Technologies](#-tools--technologies)
- [How to Use](#-how-to-use)
- [Repository Structure](#-repository-structure)
- [Insights You Can Explore](#-insights-you-can-explore)
- [Future Improvements](#-future-improvements)
- [Author](#-author)

---

## 📖 Project Overview

This project analyses a global dataset of **5,000 music streaming users** across **10 countries** and **6 streaming platforms**. The report is split into four themed pages with a consistent dark theme, so stakeholders can move from a high-level summary to demographics, listening habits and engagement.

**Goals**

- Understand the user base by age group and country
- Compare subscription types (Free vs Premium) across platforms and countries
- Identify popular genres and artists
- Discover when users listen (Morning / Afternoon / Night)
- Measure engagement through repeat-listening and Discover Weekly metrics

---

## 🗂 Dataset

**Source file:** `Global_Music_Streaming_Listener_Preferences.csv` (loaded through Power Query)
**Size:** 5,000 rows × 12 source columns (+ 1 derived column, `Age Group`)

| Column | Type | Description |
|---|---|---|
| `User_ID` | Text | Unique user identifier (e.g. `U1006`) |
| `Age` | Integer | User age (13 – 60) |
| `Country` | Text | User's country (10 countries) |
| `Streaming Platform` | Text | Platform used (Amazon Music, Tidal, Deezer, Spotify, YouTube, Apple Music) |
| `Top Genre` | Text | User's favourite genre (10 genres) |
| `Minutes Streamed Per Day` | Integer | Daily listening time in minutes (10 – 600) |
| `Number of Songs Liked` | Integer | Count of liked songs (1 – 500) |
| `Most Played Artist` | Text | User's most played artist (10 artists) |
| `Subscription Type` | Text | `Free` or `Premium` |
| `Listening Time (Morning/Afternoon/Night)` | Text | Preferred time of day to listen |
| `Discover Weekly Engagement (%)` | Decimal | Engagement with recommended playlists (10 – 90%) |
| `Repeat Song Rate (%)` | Decimal | Share of repeat plays (5 – 80%) |
| `Age Group` | Text | Derived bucket: `<= 18`, `18 - 30`, `31 - 45`, `46 - 60` |

**Categories in the data**

- **Countries:** Australia, Brazil, Canada, France, Germany, India, Japan, South Korea, UK, USA
- **Genres:** Classical, Country, EDM, Hip-Hop, Jazz, Metal, Pop, R&B, Reggae, Rock
- **Artists:** Adele, Bad Bunny, Billie Eilish, BTS, Dua Lipa, Drake, Ed Sheeran, Post Malone, Taylor Swift, The Weeknd

---

## 📊 Dashboard Pages

The report has **4 pages** (1280 × 720, dark theme).

### 1. Overview
A summary page with KPI cards and headline charts.

| Visual | Description |
|---|---|
| KPI cards | User count, total minutes streamed, repeat song rate, Discover Weekly engagement |
| Pie chart | Users by **Subscription Type** |
| Bar chart | Users by **Streaming Platform** |
| Column chart | Users by **Top Genre** |

### 2. Users Demographics
Who the listeners are and where they are from.

| Visual | Description |
|---|---|
| Column chart | Users by **Age Group** |
| Donut chart | Minutes streamed by **Country** |
| Clustered column chart | Users by **Country**, split by **Subscription Type** |

### 3. Listening Behavior of Users
What people listen to and when.

| Visual | Description |
|---|---|
| Column chart | Minutes streamed by **Top Genre** |
| Clustered column chart | Users by **Most Played Artist**, split by **Subscription Type** |
| Pie chart | Users by **Listening Time** (Morning / Afternoon / Night) |

### 4. Engagement and Preferences
How engaged listeners are, with a country filter.

| Visual | Description |
|---|---|
| **Country slicer** | Filters every visual on the page |
| Clustered column chart | Users by **Listening Time**, split by **Top Genre** |
| Column chart | Repeat Song Rate by **Streaming Platform** |

---

## 📈 Key Metrics (KPIs)

| Metric | Calculation |
|---|---|
| Total users | Count of `User_ID` |
| Total minutes streamed | Sum of `Minutes Streamed Per Day` |
| Repeat song rate | `Repeat Song Rate (%)` |
| Discover Weekly engagement | `Discover Weekly Engagement (%)` |

> **Note:** The report currently uses implicit aggregations (Sum / Count) on columns rather than explicit DAX measures. See [Future Improvements](#-future-improvements).

---

## 🧹 Data Preparation

Data is loaded and typed in **Power Query**:

1. Import the CSV (`Csv.Document`, comma delimiter, 12 columns)
2. Promote the first row to headers
3. Set data types (text, whole number, decimal)
4. Add an `Age Group` column to bucket users into `<= 18`, `18 - 30`, `31 - 45` and `46 - 60`

The model is a **single flat table** (`Global_Music_Streaming_Listener_Preferences`) with no relationships.

---

## 🛠 Tools & Technologies

- **Microsoft Power BI Desktop**: report design and visuals
- **Power Query (M)**: data loading and type conversion
- **CSV**: source data format



## 📁 Repository Structure

```
.
├── Music_streaming_plateform.pbix                      # Power BI report
├── Global_Music_Streaming_Listener_Preferences.csv     # Source dataset (add this)
├── screenshots/                                        # Dashboard images (add these)
└── README.md
```

---

## 🔍 Insights You Can Explore

The dashboard helps answer questions such as:

- Which streaming platform has the most users?
- Is the Free / Premium split balanced? (It is close to 50/50 in this dataset.)
- Which age group is the largest, and which countries stream the most minutes?
- Which genres and artists are most popular, and do Premium users differ from Free users?
- Do users prefer to listen in the morning, afternoon or at night?
- Which platform shows the highest repeat-listening rate?

---

## 🔮 Future Improvements

- Replace implicit aggregations with explicit **DAX measures** (e.g. `Avg Minutes per User`, `Premium %`)
- Use **averages** instead of sums for percentage fields such as Repeat Song Rate and Discover Weekly Engagement
- Add cross-page slicers (Platform, Subscription Type, Age Group)
- Add tooltips, drill-through pages and bookmarks
- Add a dedicated page for Free vs Premium conversion analysis

---

## 📸 Screenshots

_Add screenshots of each page here, for example:_

```md
![Overview](screenshots/overview.png)
![Users Demographics](screenshots/demographics.png)
![Listening Behavior](screenshots/listening_behavior.png)
![Engagement and Preferences](screenshots/engagement.png)
```


⭐ If you found this project useful, consider giving it a star!
