# 📊 Superstore Profit Analysis — Tableau Dashboard

An interactive Tableau workbook analyzing sales and profitability for a retail "Superstore" dataset — covering profit trends over time, category-level profitability, worst-performing products, and a geographic sales/profit map.

## 📂 Files

| File | Description |
|---|---|
| `sales_tableau.twb` | Tableau workbook (open with Tableau Desktop or Tableau Public/Reader) |
| `Superstore.xlsx` | Source dataset (connect/relink if the path doesn't resolve automatically) |

## 📁 Dataset

The workbook connects to a **Superstore sales** dataset (a well-known retail benchmark dataset) via an Excel connection, containing order-level records with fields including:

## 🖥️ Dashboard: "Profit Dashboard"
<img width="1489" height="809" alt="image" src="https://github.com/user-attachments/assets/9bd3bb41-f377-4050-82c5-f209471bece7" />

| Field | Type | Description |
|---|---|---|
| `Order Date` / `Ship Date` | Date | Order and shipping dates |
| `Customer ID` / `Customer Name` / `Customer Segment` | String | Customer details |
| `Category` / `Department` / `Item` / `Item ID` | String | Product hierarchy |
| `Region` / `State` / `City` / `Postal Code` | Numeric | Geographic location |
| `Order Priority` / `Ship Mode` / `Days to Ship` | Numeric | Fulfillment details |
| `Sales` / `Profit` / `Profit Ratio` / `Discount` | Numeric | Financial performance metrics |
| `Order Quantity` / `Unit Price` / `Shipping Cost` / `Product Base Margin` | Numeric | Order economics |

A single combined dashboard (sized for a 1500×860 range layout) bringing together four worksheets:

### 1. Profit Trend
<img width="1376" height="710" alt="image" src="https://github.com/user-attachments/assets/8768d1ef-4a4f-49b7-b35a-e68535e5d7a0" />

A time-series line chart plotting **SUM(Profit)** across **Order Date**, used to track how profitability moves month-to-month / year-to-year.

### 2. Profit by Category
<img width="1143" height="470" alt="image" src="https://github.com/user-attachments/assets/ad8d753a-c9d4-4a1c-9070-ced74014cbc7" />

A bar chart of **SUM(Profit)** broken down by **Category**, showing which product categories drive (or drag down) overall profitability.

### 3. Bottom 10 (bot 10)
<img width="1159" height="365" alt="image" src="https://github.com/user-attachments/assets/ae2ebc81-21d5-4110-8d29-b59df867bea4" />

A filtered view showing the **10 lowest-profit items**, ranked by `SUM(Profit)` in ascending order. This sheet is cross-filtered by an **action filter** tied to the Category chart — clicking a category on the "Profit by Category" chart updates this view to show that category's worst-performing items.

### 4. Sales/Profit Map (swpm)
<img width="1380" height="721" alt="image" src="https://github.com/user-attachments/assets/c8474c7c-09d1-4ec9-92d3-6b5ecd0357dc" />

A geographic map plotting generated **Latitude/Longitude**, visualizing sales and profit distribution by location (state/city).

**Interactivity:** Selecting a category in the "Profit by Category" chart filters the "Bottom 10" worksheet, letting you drill from a high-level category view straight down to the specific underperforming products within it.

## 🚀 How to Open

1. Install **Tableau Desktop** (or use the free **Tableau Public**/Tableau Reader) if you don't already have it.
2. Download `sales_tableau.twb` and the source `Superstore.xlsx` file.
3. Open `sales_tableau.twb` in Tableau. If prompted to locate the data source, browse to wherever you've saved `Superstore.xlsx`.
4. Click the **Profit Dashboard** tab to view the combined interactive dashboard.

> ⚠️ Note: `.twb` files store the workbook logic but not the data itself — make sure the source Excel file is available and correctly linked, or the sheets will show a "cannot connect to data source" error.

## 🔮 Possible Next Steps

- Add KPI cards for headline metrics (Total Sales, Total Profit, Profit Ratio)
- Add filters for Region / Customer Segment / Ship Mode for deeper drill-down
- Add a discount-vs-profit scatter plot to investigate margin erosion from discounting
