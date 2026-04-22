# Personal Budget Tracker 2026 - Vasuki


A personal finance budget tracker in Excel with 314 dynamic formulas, auto-calculating dashboards, and a Spending Insights tab that tells you exactly where your money is going and where to cut.

## What's Inside

- Dashboard: 4 KPI cards (Total Income, Total Expenses, Total Savings, Net Balance), income vs expenses bar chart, net balance trend line, and savings rate trend. Everything updates automatically.
- Monthly Tracke: 25 budget categories across Income (5), Expenses (15), and Savings (5) for all 12 months with auto-calculated totals.
- Spending Insights (the magic tab): Automatically analyzes your spending and tells you:
  - Your top 3 highest expenses every month
  - Which category is costing you the most (and what % of your total expenses)
  - Whether your spending is going up or down month over month (color-coded verdicts)
  - A recommendation for each expense category: HIGH (review for savings), MODERATE (look to trim), WATCH (small but adds up), or OK (reasonable)
  - A pie chart showing exactly where your money goes annually
- How To Use- Step-by-step instructions built into the file.

Formulas and Functions Used:
This tracker uses 314 formulas across 4 sheets. Here is the complete breakdown:
Basic Aggregation

SUM - Calculates totals for each category across all 12 months and totals for each month across all categories. Used in Monthly Tracker (row/column totals) and Dashboard (annual totals).

Statistical:

AVERAGE - Computes monthly averages for expense categories in the Spending Insights tab, giving you a realistic view of your typical monthly spending per category.
MAX - Identifies the single highest expense amount for each month, powering the "What category is costing you the most?" section.
LARGE - Ranks your top 3 highest expenses per month. LARGE(range, 1) returns the biggest, LARGE(range, 2) returns second biggest, LARGE(range, 3) returns third.

Lookup and Reference

INDEX/MATCH - The engine behind the Spending Insights tab. INDEX/MATCH dynamically looks up which expense category name corresponds to the highest spending amount each month. Example: if your MAX expense in January is $1,500, INDEX/MATCH returns "Housing/Rent" automatically.

Logic and Decision

IF - Powers the savings rate calculation (avoids divide-by-zero errors when income is $0), the month-over-month spending verdict ("SPENDING UP" vs "SPENDING DOWN"), and the percentage-of-total calculations.
Nested IF - Drives the recommendation engine in the "Where to Reduce" section. Each expense category gets an automatic recommendation based on what percentage of your total expenses it represents:

Greater than 20%: "HIGH: Major expense. Review for savings."
10% to 20%: "MODERATE: Look for ways to trim."
5% to 10%: "WATCH: Small but adds up over time."
Less than 5%: "OK: Reasonable spending."



Error Handling

IFERROR - Wraps around LARGE and INDEX/MATCH formulas to gracefully handle months where you haven't entered data yet. Instead of showing errors, empty months show 0 or "No data."

Counting

COUNTA - Counts how many months have actual data entered, so the monthly average calculation divides by the correct number of months (not 12) if you've only filled in a few months so far.

Conditional Formatting (Visual Logic)

Color-coded verdicts - The "Verdict" row in Spending Insights turns red with bold text when spending goes up and green when spending goes down, so you can spot trends at a glance.
Color-coded recommendations - The "Recommendation" column highlights HIGH categories in red and MODERATE in yellow, drawing your eye to where you should focus.

Cross-Sheet References

Dashboard pulls KPI values directly from Monthly Tracker totals using cross-sheet formulas
Spending Insights pulls raw expense data from Monthly Tracker for analysis
All sheets are connected. Change one number in Monthly Tracker and every dashboard, chart, insight, and recommendation updates instantly.

#How to Use

1. Download `Personal_Finance_Budget_Tracker_2026.xlsx`
2. Open in Excel or Google Sheets
3. Go to the Monthly Tracker tab
4. Replace the sample data with your own numbers
5. Switch to the Dashboard tab and watch it update automatically
6. Check the Spending Insights tab to see where you're spending the most and where to reduce

#Built With

Microsoft Excel (SUM, AVERAGE, MAX, LARGE, INDEX/MATCH, IF, Nested IF, IFERROR, COUNTA, Conditional Formatting, Charts)
Python (openpyxl) for programmatic file generation

Who This Is For

Anyone trying to get their finances organized
People who prefer spreadsheets over budgeting apps
Students, freelancers, families, and anyone watching their spending
People who want to see exactly where their money goes and where to cut
Excel learners who want to study real-world formula usage

Author
Vasuki Balasubramanian

Portfolio: vasuki123.github.io/vasuki-s-portfolio
LinkedIn: linkedin.com/in/vasuki-balasubramanian31
Email: vasukib31@gmail.com
