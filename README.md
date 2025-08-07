# 🎵 Grammys Website User Engagement Analysis

This project analyzes web traffic and user engagement metrics for the Grammys.com and RecordingAcademy.com websites, comparing performance before and after their digital split, and benchmarking against the American Music Awards (AMA) website. It aims to provide insights into visitor behavior and inform strategies to increase year-round user engagement.

## 📌 Project Overview

Using multiple datasets including site traffic, session data, and demographic information, this project focuses on:

- Examining visitor trends and traffic spikes related to Grammy Awards events  
- Comparing key engagement metrics before and after the website split  
- Analyzing user device distribution and demographics  
- Benchmarking against a major competitor (AMA) on key performance indicators (KPIs)  
- Delivering actionable recommendations to improve website performance and user retention

## 💻 Tools & Technologies

- **Python (pandas, plotly.express)**  
- **Data Wrangling & Cleaning**  
- **Time Series Analysis**  
- **Data Visualization**  
- **Basic Statistical Analysis**

## 📊 Key Insights

- **Traffic Concentration**: The Grammy Awards show night drives massive spikes in visitors, with over 40 times more users than average days.  
- **Post-Split Engagement**: After the site split, recordingacademy.com showed improved engagement with a lower bounce rate (~30%) and longer average session durations compared to the combined site.  
- **Device Usage**: Majority of visitors (68%) access the Grammys site via mobile, reflecting modern consumption trends.  
- **Competitor Comparison**: AMA visitors stay longer on their site (~5m 53s) but have a higher bounce rate (~54%), indicating different engagement dynamics.  
- **Age Demographics**: Both sites attract a broad age range, with differences in visitor percentages across groups, informing targeted content strategies.

## ✅ Recommendations

- **Maintain separate sites** to leverage their distinct audiences and engagement strengths.  
- **Develop year-round content** and interactive features to reduce reliance on the annual Awards Night surge.  
- **Optimize mobile experience** given the large share of mobile users.  
- **Explore strategies to increase session duration and reduce bounce rate**, learning from competitor strengths.  
- **Use demographic insights** to tailor marketing and content for key age groups.

## 🔍 Example Python Techniques

```python
# Calculate bounce rate for each dataframe
def bounce_rate(df):
    return 100 * df['bounced_sessions'].sum() / df['sessions'].sum()

# Create pages per session
df['pages_per_session'] = df['pageviews'] / df['sessions']

# Plot pages per session over time
fig = px.line(
    df,
    x='date',
    y='pages_per_session',
    title='Pages per Session Over Time'
)
fig.show()

# Combine desktop and mobile user data and calculate share
segment_df['total_visitors'] = segment_df['desktop_visitors'] + segment_df['mobile_visitors']
desktop_share = 100 * segment_df['desktop_visitors'].sum() / segment_df['total_visitors'].sum()
mobile_share = 100 - desktop_share
