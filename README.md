# Saskatoon Payroll Ledger

An interactive dashboard of the City of Saskatoon's published Public Accounts, 2020–2025.

Open `index.html` in a browser, or see the hosted site.

## What it shows

- **Overview:** total pay, headcount, overtime and retro pay by year, plus flagged department spikes with the driver behind each one: hiring, pay per person, overtime or retro.
- **Departments:** a year-over-year heatmap (% change or total $). Each department page shows pay by component, what drove the changes, people joining and leaving, title families, and every employee's pay by year.
- **Employees:** normalized job-title families with headcount and pay trends, and a year-by-year employee table (total, regular salary, retro, overtime, other).
- **Payments:** third-party payments and grants by vendor and category, with charts or a trend heat table.
- **Council and boards:** council remuneration and expenses, board remuneration, and business improvement districts.
- **Data quality:** extraction checks, source discrepancies, and how departments were assigned.

The page works on desktop and phones, in light and dark themes.

## Privacy

Employees are identified only by normalized title, department, section and an anonymous ID (e.g. `P01234`). Employee names from the source documents are removed from this page. Names of council members, board members, business improvement district directors and payees are kept as published.

## Method notes

- **Source:** the City of Saskatoon Public Accounts PDFs for 2020–2025. Employees appear only if they were paid over $50,000.
- **Departments:** the PDFs list only a section for each employee (General Municipal, Police, Fire, Library, and so on). Departments are inferred from job titles, unit hints and the same person's other years. Rows with no evidence are grouped as "Other".
- **People:** employees are matched across years by name, estimated at about 99.5% accurate.
- **Spikes:** a department-year is flagged when total pay moves more than 15%, or when the move is unusual for that department (z > 2) and at least 8%. Departments with fewer than 5 people and changes under $250k are excluded.
- **The $50k cut-off:** the cut-off is fixed in dollars, so raises move people on and off the list. Switch the threshold to "Constant ≥ $60k" for a like-for-like comparison.

This is an independent analysis, not an official City of Saskatoon product.

## Hosting

The site is a single static `index.html`, with charts drawn by d3 7.9.0 from cdnjs. It needs no build step to host.
