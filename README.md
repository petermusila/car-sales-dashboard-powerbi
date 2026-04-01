# 🚗 Car Sales Dashboard - Power BI
## The Story Behind This Dashboard

The question I kept hearing: *"What does this chart mean?"*

So I built something different.

A dashboard that doesn't just show numbers—it **tells you what to do.**

## What Makes This Dashboard Different

### 💡 Dynamic Insights Page
When users filter by region, company, or date, the dashboard automatically generates:
- Performance highlights
- Top performers
- Areas of concern
- Actionable recommendations

**No more manual interpretation. No more "what does this mean?"**

## Key Features
### 📊 12 Key Performance Indicators
| Category | Metrics |
|----------|---------|
| Sales Overview | YTD Sales, MTD Sales, YoY Growth, PTYD Difference |
| Price Analysis | YTD Avg Price, MTD Avg Price, YoY Growth, PTYD Difference |
| Volume Metrics | YTD Cars Sold, MTD Cars Sold, YoY Growth, PTYD Difference |

### 📈 6 Interactive Visuals
- YTD Sales Weekly Trend (Line Chart)
- Sales by Body Style (Pie Chart)
- Sales by Color (Pie Chart)
- Cars Sold by Dealer Region (Map Chart)
- Company-Wise Sales Grid
- Detailed Transaction Grid

### 🔧 Technical Implementation
- **DAX Measures:** 24 custom measures for time intelligence and dynamic insights
- **Data Model:** Calendar table with proper relationships
- **Sync Slicers:** Consistent filtering across all pages

---

## Screenshots

### Overview Page
*<img width="1280" height="739" alt="Overview" src="https://github.com/user-attachments/assets/21090822-f6a5-4f70-b258-5ad06111c1af" />*

### Insights Page
*<img width="1275" height="758" alt="Insights" src="https://github.com/user-attachments/assets/45ed9e94-9938-4f22-b3c4-296538e330c8" />*

*Watch how insights change when filters are applied:*

## DAX Highlights
Here's a sample of the dynamic insights logic:

```dax
Performance Highlights = 
VAR SalesGrowth = [YOY Sales Growth]
RETURN
"📈 Total Sales: " & FORMAT([YTD Sales], "$#,##0.0M") & 
" (" & IF(SalesGrowth > 0, "▲", "▼") & " " & 
FORMAT(SalesGrowth, "0%") & " vs last year)"
