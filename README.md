# 📊 Indonesian Stock Market Scraper & Analysis  

### 🧠 Overview  
This project focuses on **extracting, cleaning, and analyzing stock data from TradingView’s Indonesian Stock Market**.  
It scrapes two main sections — **Top Gainers** and **52-Week Highs** — to explore stock performance, sector trends, and analyst ratings.  
The purpose of this project is **purely educational**, and the data was collected on **October 17, 2025**.

---

### 🧰 Tech Stack
- **Language:** Python 3.9  
- **Libraries:** `pandas`, `requests`, `BeautifulSoup4`, `matplotlib`, `datetime`  
- **Tools:** Microsoft Excel (for exporting cleaned datasets)  
- **Visualization:** Matplotlib (for charts and summary insights)

---

### 🕸️ Web Scraping Logic  
The scraping process retrieves HTML table data from **TradingView.com**, specifically from Indonesian market pages like Top Gainers and 52-Week Highs.

Each table row (`<tr>`) represents a single stock, and each data cell (`<td>`) inside it contains detailed information such as ticker, price, change percentage, and more.

When inspecting the HTML, hovering over `<td>` elements highlights specific data blocks in the table — confirming that each piece of information displayed corresponds to an individual `<td>` tag within a `<tr>` row.

#### Extracted Columns:
Symbol, Price, Change %, Volume, Rel Volume, Market cap, P/E,
EPS dilTTM, EPS dil growthTTM YoY, Div yield %TTM, Sector, Analyst Rating


---

### 🧹 Data Cleaning & Processing  
After scraping, several cleaning and transformation steps were performed to make the dataset analysis-ready:

- **Split the `Symbol` column** into two: `Ticker` and `Company`.  
- **Removed unwanted symbols** such as `%`, `IDR`, `M`, `B`, `T`, and non-breaking spaces (`\xa0`).  
- **Preserved minus signs (`-`)** to correctly represent negative values like `−2.71%`.  
- **Converted numeric-like strings** (e.g., `"1,435 IDR"`, `"5.95 M"`) into `float` for accurate computation.  
- **Replaced cells with “–” or blanks** as missing values (`NaN`) to ensure proper handling.  
- **Fixed inconsistent spacing**, e.g., `EPS dil growthTTM YoY` → `EPS dil growth TTM YoY`.  
- Exported both **raw** and **cleaned** versions for transparency and reproducibility.

#### 📂 Exported Files:
| File Name | Description |
|:-----------|:------------|
| `df_gainers_raw_2025-10-17.xlsx` | Scraped Top Gainers data (raw format) |
| `df_gainers_clean_2025-10-17.xlsx` | Cleaned Top Gainers data |
| `df_high_raw_2025-10-17.xlsx` | Scraped 52-Week High data (raw format) |
| `df_high_clean_2025-10-17.xlsx` | Cleaned 52-Week High data |

---

### 💾 Why Use `datetime`?  
The `datetime` module is used to **automatically include the current date in exported filenames**, ensuring traceability for each scraping session.  
Example:
df_gainers_clean_2025-10-17.xlsx

This makes it easy to track when the data was collected and prevents overwriting previous datasets.

---

### 📈 Data Analysis & Visualization  

#### 📊 Combined Insights — Top Stocks Performance
The visual analysis covers both **Top Gainers (%)** and **52-Week High (Price in IDR)** to highlight the best-performing stocks:

- **BLUE** recorded the **highest daily gain (~25%)** among all listed gainers.  
- **SRAJ** achieved a **price of around IDR 11,500**, topping the 52-Week Highs list.  
These results suggest strong short-term growth trends in selective market segments.

#### 🏭 Average % Change per Sector  
Sector-wise performance comparison revealed that:
- The **Distribution Services** sector had the **highest average percentage change**, almost reaching **10%**, indicating strong short-term investor interest.

#### 💬 Analyst Rating Distribution  
Based on scraped analyst data:
| Rating | Percentage |
|:-------|------------:|
| Neutral | 88% |
| Strong Buy | 9% |
| Buy | 3% |

Most stocks are rated **Neutral**, suggesting cautious sentiment in the Indonesian market, while a smaller fraction of “Strong Buy” indicates a few high-confidence opportunities.

---

### 📊 Visualizations  
Three key visualizations were generated using Matplotlib to support the insights above:

1. **Top 10 Gainers (%)**
   Displays the top 10 stocks by daily percentage increase.  

3. **Top 10 52-Week Highs (Price in IDR)**
   Highlights the highest stock prices within the past year.

4. **Average % Change per Sector**
   Summarizes average percentage movement grouped by sector to identify high-performing industries.

### ⚠️ Disclaimer

This project was created solely for educational and portfolio demonstration purposes.
All data was publicly available from TradingView.com and collected on October 17, 2025.
No investment or financial advice is provided or implied.

### 🧩 Author

**Muhammad Alpim Alfa Rolis**
-📍 **Data Engineer | Data Analyst | Data Scientist**
-💼 **LinkedIn Profile**
    https://www.linkedin.com/in/muhammadalpimalfarolis/
-📧 **Email**
    alpimar79@gmail.com
