# Amazon India Dashboard

A single-page, interactive management dashboard built by Arka Bhattacharya to present to Ravi (non-technical manager). It follows the Sapphire IQ business requirements and answers four business questions in one place.

**Live demo:** `https://chronos07-bit.github.io/amazon-india-dashboard/`

## What it shows
| Section | Business question | Content |
|---|---|---|
| 1. Overall Sales & Profit | How is the business performing? | Total Sales, Profit, Orders, Units, Average Order Value, Profit Margin %, monthly sales & profit trend |
| 2. Category & Product | What drives the business? | Category-wise sales, profit, units; Top 10 products by sales |
| 3. Order Status & Revenue Loss | How many orders are lost? | Delivered / Shipped / Returned / Cancelled counts, return rate %, cancellation rate %, revenue lost, category-wise returns & cancellations |
| 4. Payment, Fulfillment & Geography | Which channels and markets perform? | Sales and profit by payment method and fulfillment method; state-wise sales, profit and orders |

Each section ends with auto-generated "Expected insight" bullets that update with the filters.
Filters: Year, Category, State, Payment method, Fulfillment, Sales basis.

## Data
`data/amazon_sales_data_india.csv` — 10,000 orders (Jan 2024 – Aug 2026), 13 columns. The same data is embedded in `index.html`, so the page needs no server.

## Metric definitions
- **Total Sales** = sum of `Total_Sales_INR` (after discount) for the filtered orders. Default basis is *All orders (as booked)*; the *Sales basis* filter can exclude cancelled and returned orders.
- **Total Profit** = sum of `Profit_INR` (the data records ₹0 for cancelled and returned orders).
- **Profit Margin %** = Profit ÷ Sales.
- **Average Order Value** = Sales ÷ number of orders.
- **Return / Cancellation Rate** = returned (or cancelled) orders ÷ total orders.
- **Revenue Lost** = order value of returned + cancelled orders.

## Run locally
Open `index.html` in a browser (needs internet for the Chart.js CDN script).

## Publish on GitHub Pages
1. Create a repo and upload `index.html`, `README.md` and the `data` folder.
2. Settings → Pages → Deploy from a branch → `main` / `(root)` → Save.
3. Submit the repo link (and the Pages link).

## Tech
HTML, CSS, vanilla JavaScript, Chart.js 4.4.1.
