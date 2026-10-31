# Daily Scrum KPI App (Power Apps + embedded Power BI)

A Power Apps canvas app that replaced an Excel-based red/green KPI review for a manufacturing site's daily leadership meeting. Division leaders rate each KPI category, add comments and drill into the matching Power BI reports, **already filtered to their division**, without leaving the app.

Built at **3M** for the San Luis Potosí (Mexico) site team, where it was used in their daily scrum meetings. Sensitive data has been removed from the screenshots.

![Power Apps](https://img.shields.io/badge/Power%20Apps-742774?logo=powerapps&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black)

## The problem

Before each meeting, division leaders checked KPIs across several Power BI reports and then typed a red/green status into a shared Excel sheet for the site leader. The sheet had no comments, no history and no link back to the numbers behind each rating.

**Requirements:** keep the familiar red/green rating, add comments, show the past weeks' status, and put the supporting reports one click away.

## Solution

| Screen | What it does |
|---|---|
| **Home** | Today's red/green summary across all divisions and categories, with navigation to each division or category |
| **Division** | The division leader rates each category against criteria shown on screen, adds comments, and sees an embedded Power BI dashboard with historical status |
| **Category** | Embedded Power BI reports for that metric, filtered to the selected division (or unfiltered for the whole site) |

<p align="center"><img src="https://github.com/GianottiLeo/Power-Apps-Scrum-App/assets/164948682/42ddbe47-a81c-41f1-9705-ca09c275042a" width="640" alt="Home screen with red/green summary per division and category"></p>
<p align="center"><img src="https://github.com/GianottiLeo/Power-Apps-Scrum-App/assets/164948682/5f176359-4eaf-4204-9c9e-60690fed653c" width="640" alt="Division screen with rating inputs, criteria and embedded history dashboard"></p>
<p align="center"><img src="https://github.com/GianottiLeo/Power-Apps-Scrum-App/assets/164948682/ef0cdabf-4b82-48f3-9204-65a16e77bb28" width="640" alt="Category screen with an embedded Power BI report filtered by division"></p>

## The hard part: dynamic filters on embedded reports

Power Apps can embed a Power BI report, but it can't pass it a filter based on which button the user clicked. The filter has to go in the report URL instead (`?filter=Table/Field eq 'Value'`), using Power BI's URL-encoded names for tables, fields and values.

I built formulas in Power Apps that map the selected button's text (for example "Division 1") to the matching field name in the report, URL-encode it, and assemble the filtered embed URL at runtime. One report then serves every division, with no duplicate pages to maintain.

## Outcome

- Ratings, comments and history in one place instead of a spreadsheet.
- Leaders could open the numbers behind each red/green call during the meeting itself.
- The site team used it in their daily meetings for a period. It has since been retired, which is why the screenshots show empty inputs.
