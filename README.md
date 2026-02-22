# 🏋️ Fitness Dashboard — Power BI



> A fully interactive Power BI dashboard to track Fitness Activities, Memberships, Finances, and Client Performance — built with AI-assisted DAX queries using the **Power BI MCP (Model Context Protocol) Server**.

---

## 📊 Dashboard Preview

![Fitness Dashboard](https://github.com/user-attachments/assets/3f07a463-36a0-4c34-87ff-d622209b4e36)

---

## 🚀 About This Project

This Fitness Dashboard was built in **Power BI** to help gym owners and managers monitor their business at a glance. What makes this project unique is the use of the **Power BI MCP Server**, which allowed AI to generate, test, and optimize all the DAX queries — drastically reducing development time and improving accuracy.

Instead of manually writing complex DAX measures from scratch, the MCP Server bridged the gap between AI and Power BI, enabling production-ready queries to be built through natural language interaction with AI.

---

## ✨ Features

- 💰 **Finances Overview** — Monthly Revenue, Expenses & Profit trends with line and bar charts
- 🏅 **Membership Tracking** — Breakdown of Platinum, Gold & Silver memberships (Active vs Expired)
- 👥 **Client & Trainer Summary** — Quick stats on total Clients (100) and Trainers (20)
- 📈 **Monthly Members Trend** — Bar chart showing member growth across months
- 📋 **User Performance Table** — Individual membership utilization with progress bars
- 🕒 **Real-time Last Updated Timestamp** — Dashboard shows the last refresh time

---

## 🧠 AI-Assisted DAX Queries (MCP Server)

The following DAX measures were generated and optimized using the **Power BI MCP Server**:

| Measure | Description |
|--------|-------------|
| `Revenue` | Total revenue aggregated across all payment records |
| `Expenses` | Total expenses calculated from the Expenses table |
| `Profit` | Revenue minus Expenses |
| `Distinct User Count` | Count of unique active users |
| `Active Memberships` | Count of memberships with Active status |
| `Expired Memberships` | Count of memberships with Expired status |

---

## 🗂️ Data Model

The dashboard is powered by the following tables:

- **Users** — Client and Trainer details
- **Payments** — Revenue and transaction records
- **Expenses** — Monthly expense records
- **Date** — Custom date table built with `ADDCOLUMNS` and `CALENDAR()` DAX function
- **ColorCodes** — Used for conditional formatting in visuals

### Date Table DAX
```dax
Date = ADDCOLUMNS(
    CALENDAR(DATE(2024,1,1), DATE(2024,12,31)),
    "Year", YEAR([Date]),
    "Month", FORMAT([Date], "MMM"),
    "MonthNumber", MONTH([Date]),
    "Quarter", "Q" & QUARTER([Date]),
    "Day", DAY([Date]),
    "Weekday", FORMAT([Date], "dddd"),
    "YearMonth", FORMAT([Date], "YYYY-MM")
)
```

---

## 🔧 Setup & Usage

### Prerequisites
- Power BI Desktop (latest version)
- Access to the source data (CSV / Excel / Database)

### Steps to Run
1. Clone this repository
   ```bash
   git clone https://github.com/yash966/GYM_Dashboard.git
   ```
2. Open the `.pbix` file in **Power BI Desktop**
3. Update the **data source path** if needed under `Transform Data > Data Source Settings`
4. Refresh the data and explore the dashboard

---

## 📁 Project Structure

```
GYM_Dashboard/
├── GYM_Dashboard.pbix       # Main Power BI file
├── README.md                # Project documentation
├── dashboard_preview.png    # Dashboard screenshot
└── Data/
    ├── users.csv
    ├── payments.csv
    └── expenses.csv
```

---

## 🛠️ Tools & Technologies

- **Power BI Desktop** — Dashboard development
- **DAX** — Data Analysis Expressions for all measures
- **Power BI MCP Server** — AI-assisted DAX query generation
- **Power Query (M Language)** — Data transformation

---

## 📬 Connect

Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/yash966) or raise an issue if you have suggestions or questions!

---

⭐ If you found this project useful, consider giving it a star!
