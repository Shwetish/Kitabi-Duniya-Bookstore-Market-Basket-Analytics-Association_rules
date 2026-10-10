# Kitabi-Duniya-Bookstore-Market-Basket-Analytics-Association_rules
Implements Association Rule Mining (Apriori algorithm) for Kitabi Duniya, a heritage bookstore, to discover cross-selling book bundles, optimize in-store promotions, and counter online retail competition.


# 📚 Kitabi Duniya: Heritage Bookstore Revival & Association Mining Suite

## 1. Business Problem

### 1.1. What is the business objective?
* **Reviving a Heritage Brand:** Help *Kitabi Duniya*, a historical pre-Independence bookstore in India, overcome sharp revenue declines caused by widespread internet access and e-commerce platforms.
* **Increasing Customer Footfall:** Identify cross-selling opportunities, bundle complementary book genres, and curate in-store promotional packages to draw physical customers back into the store.
* **Exponential Growth Strategy:** Implement data-driven market basket analysis to recommend targeted reading lists and optimize physical counter displays.

### 1.2. Are there any constraints?
* **Data Sparsity:** Transactional datasets often contain sparse binary matrices where most items are unpurchased in a single basket.
* **Threshold Tuning:** Balancing minimum support and confidence parameters to avoid generating too few rules (missing key combinations) or combinatorial explosions (unreliable or trivial rules).
* **Historical vs. Modern Shift:** Adapting a traditional brick-and-mortar business model to modern analytical consumer insights without losing its heritage charm.

---

## 2. Data Dictionary (`Books.csv`)

| Feature Name | Data Type | Description |
| :--- | :--- | :--- |
| **Transaction_ID / Basket_ID** | Integer / String | Unique identifier for each customer purchase instance. |
| **Book_Item / Genre** | Categorical | Names or categories of the books purchased together in a single transaction. |
| **Purchase_Quantity** | Integer | The count of individual copies or titles bought per transaction. |

---

## 3. Data Pre-processing

### 3.1. Data Cleaning & Feature Engineering
* **Handling Missing Values:** Checked for null transactions or blank entries in the dataset and cleaned formatting discrepancies in book titles.
* **One-Hot Encoding:** Converted the transactional book list into a boolean matrix (True/False or 1/0 flags for each book/genre per transaction) required by the Apriori algorithm using `mlxtend`.

---

## 4. Model Building

### 4.1. Application of Apriori Algorithm
* Implemented the Apriori algorithm to discover frequent itemsets based on a defined minimum support threshold.
* Filtered rules using confidence and lift metrics to extract strong, meaningful associations between different book genres.

### 4.2. Build Most Frequent Itemsets and Plot Rules
* Extracted top frequent itemsets (pairs and triplets of books frequently bought together).
* Generated network and scatter plots (Support vs. Confidence, Support vs. Lift) using `matplotlib` and `seaborn` to visually display rule strengths.

### 4.3. Work on Codes
* The complete implementation code can be found in the `scripts/Book.py` file.

---

## 5. Deployment

### 5.1. Deploy Solutions
* **Dashboard / Recommendation Engine:** The model can be integrated into a lightweight web app (e.g., Streamlit) for store staff to look up recommendations, or embedded into a Point-of-Sale (POS) system to suggest bundle discounts at checkout.

---

## 6. Business Impact & Benefits
* **Enhanced Cross-Selling:** Enables staff to bundle slow-moving titles with high-demand bestsellers, improving overall inventory turnover.
* **Revitalized Customer Footfall:** Curated in-store "Book Lover Bundles" and special display sections attract niche readers and casual visitors alike.
* **Data-Driven Merchandising:** Transitions *Kitabi Duniya* from traditional intuition-based stock management to a modern, analytics-backed heritage enterprise.
