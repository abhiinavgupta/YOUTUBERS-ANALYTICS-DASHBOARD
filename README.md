# YOUTUBERS-ANALYTICS-DASHBOARD


## 📌 Overview
This project delivers an interactive dashboard to identify and analyse the **Top 100 UK YouTubers in 2024**.  
It helps the Marketing team, especially the Head of Marketing (Sharon), to discover the most effective YouTube channels for collaborations and campaigns, with the aim of maximising ROI.

## 🎯 Objectives
- Identify the top-performing UK YouTube channels by subscribers, videos uploaded and total views.
- Provide key metrics (channel name, subscribers, videos, views, engagement ratios) in an easy-to-filter dashboard.
- Recommend channels best suited for different types of marketing campaigns using data-driven justification.

## 👥 Target Audience
- **Primary:** Head of Marketing (decision maker).
- **Secondary:** Marketing team members executing campaigns.

## 📊 Dashboard Features
- Leaderboard of the **Top 100 UK YouTubers** with sortable/filterable metrics:
  - Channel name  
  - Total subscribers  
  - Total videos uploaded  
  - Total views  
  - Average views per video  
  - Views per subscriber  
  - Subscriber engagement ratio  
- Interactive visuals:
  - Top channels by subscribers and views (bar charts)
  - Scatter plot of Subscribers vs Avg Views per Video
  - Engagement & growth indicators
- Campaign Recommendation Panel:
  - Suggests the most suitable channels for product placement, sponsored video series and influencer marketing.
  - Shows estimated reach, engagement and potential revenue with data-driven justifications.

## 🛠️ Data
### Fields Required
| Field | Type | Description |
|-------|------|-------------|
| Channel Name | String | Name of the YouTube channel |
| Total Subscribers | Integer | Total subscriber count |
| Total Videos Uploaded | Integer | Number of videos uploaded |
| Total Views | Integer | Cumulative views across all videos |
| (Optional) Avg Likes / Comments | Integer | For richer engagement metrics |
| Date Scraped | Date | Snapshot date for time series |

### Data Quality Checks
- **Row count check** (confirm 100 rows per snapshot)
- **Column count check** (validate schema)
- **Data type check** (ensure numeric fields are integers)
- **Duplicate check** (channel name + date_scraped)

## ⚙️ Architecture & Workflow
1. **Ingest**: Pull channel stats from the YouTube API or a third-party dataset.
2. **Transform**: Clean, deduplicate, compute derived metrics (avg views/video, views per subscriber, engagement ratios).
3. **Load**: Store processed data in a BI-friendly table.
4. **Visualise**: Connect the dataset to Power BI to build the dashboard.
5. **Refresh**: Schedule daily/weekly updates to maintain freshness.


## 📐 Metrics & Formulas
- **Average Views per Video** = `Total Views / Total Videos Uploaded`
- **Views per Subscriber** = `Total Views / Total Subscribers`
- **Engagement Ratio (proxy)** = `Average Views per Video / Total Subscribers`
- **30-Day Subscriber Growth %** = `(SubscribersToday - Subscribers30DaysAgo) / Subscribers30DaysAgo * 100`

These measures feed into a weighted score to recommend channels for specific campaign types.

## 🖥️ Technology Stack
- **Data Ingestion**: Python / YouTube API v3  
- **Data Storage**: SQL database / CSV snapshots  
- **Dashboard**: Power BI  
- **Version Control**: GitHub  

## 📂 Repository Structure

