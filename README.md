# 🛒 Predictive Sales Data Intelligence Project  
<br>  

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Poppins&size=32&pause=1000&color=36BCF7&center=true&vCenter=true&width=900&lines=Predictive+Sales+Data+Intelligence+Project;End-to-End+Python+%2B+SQL+ETL+Pipeline"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/PROJECT-Data%20Analytics-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/DOMAIN-Retail%20%26%20E--Commerce-blueviolet?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/LEVEL-Professional-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/STATUS-Completed-brightgreen?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Python-Data%20Prep-blue?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/SQL-PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white"/>
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
</p>

---

# 📈 Project Overview  
This project replicates an enterprise retail data environment. Starting with an unclean dataset pulled via Kaggle's API, Python handles the core heavy lifting of parsing types, dropping duplicates, and engineering financial columns. The processed source data is subsequently exported to `walmart_clean_data.csv` and systematically injected into an RDBMS server environment for high-powered SQL business querying.  
<br>  

## Project Data Architecture Layout  
Refer to `Predictive Sales Data Intelligence-piplelines.jpg` below for the full visual data flow diagram mapping out this exact sequence:  
<br>
![Project_Pipeline](https://github.com/RajayJain/Predictive-Sales-Data-Intelligence/blob/badd8d43bd7877b8d1eef766839155e848698fa0/Resources/Predictive%20Sales%20Data%20Intelligence-piplelines.png)

```mermaid
%%{init: {'theme': 'dark'}}%%
graph TB
    A[☁️ Kaggle API] -->|Raw Stream| B(🐍 Python / Pandas ETL)
    B -->|1. Drop Duplicates <br> 2. Cast Price & Total Float| C[💾 walmart_clean_data.csv]
    C -->|SQLAlchemy Core / PyMySQL / Psycopg2| D{🗄️ Relational DBs}
    D -->|RDBMS Target 1| E[🐬 MySQL Server]
    D -->|RDBMS Target 2| F[🐘 PostgreSQL Engine]
    E & F -->|Analytical Window Functions| G[📊 Enterprise Business Insights]
```
<br>  

# 📂 Repository File Blueprint
``` 
├── Predictive Sales Data Intelligence-piplelines.jpg  # Core architectural layout & visualization pipeline
├── project.ipynb                    # Ingestion, cleansing, data-type casting & processing script
├── SQL_File.sql                     # Advanced business analytics analytical query engine
├── Predictive Sales Data Intelligence Business Problems.pdf    # Business objective problem statement matrix
└── walmart_clean_data.csv          # Sanitized database production-ready export distribution
```
<br>  


# 🛠️ Tech Stack & Library Toolkit
- Data Ingestion & Cleaning: `Pandas` (v3.0.3 Core engine parsing)

- DB Engine & Adapters: `SQLAlchemy` (Universal Object-Relational abstraction Layer)

- Database Client Middleware: `PyMySQL` (MySQL interface) & `Psycopg2-binary` (PostgreSQL interface)

- Interactive Testing Development Environment: `IPython` / Jupyter Kernel notebooks
<br>

# ⚙️ Data Pipeline Processing Steps (ETL Blueprint)  
## 🧹 Phase 1: Exploration & Sanitization
- **Duplicate Stripping:** Detected and eliminated 51 exact row duplicates, scaling dataframe boundaries accurately down to a balanced 10,000 baseline items.
- **Null Treatment:** Programmatically purged rows bearing missing item details via `.dropna()`.
- **Data Cleaning & Feature Engineering:**
    - Cleaned monetary strings by stripping character flags (`$`) from raw values and modifying strings into high-precision floating numbers (`df['unit_price'].astype(float)`).
    -* Synthesized financial columns using standard multipliers:
  
         &nbsp;&nbsp;&nbsp;&nbsp; ***Total = Unit Price × Quantity***  
  - Transformed table attributes by implementing uppercase formatting (`df.columns.str.upper()`) to ensure absolute schema compatibility before executing target database migrations.  
  - **Output Snapshot Generation:** Compiled 9,969 completely structured rows straight into the pristine system distribution target asset file titled `walmart_clean_data.csv`.
  <br>

# 🚀 Phase 2: Database Storage Loading  
Using Python connection string engines, the optimized operational metrics mapping engine moves files dynamically:  
```python
# PostgreSQL pipeline link setup
engine_psql = create_engine("postgresql+psycopg2://postgres:******@localhost:5432/walmart_db")

# Rapid batch append execution array mapping 
df.to_sql(name='walmart', con=engine_psql, if_exists='replace', index=False)
print(f"Successfully inserted {len(df)} rows into PostgreSQL!")
```
<br>  

*The business problems to be solved via SQL can be found here [Business Problems](https://github.com/RajayJain/Predictive-Sales-Data-Intelligence/blob/badd8d43bd7877b8d1eef766839155e848698fa0/Resources/Predictive%20Sales%20Data%20Intelligence.pdf)* and solutions here [Solutions](Resources/SQL_File.sql).
<br>  

# 💼 Core Business Querying Challenges Resolved  
The repository houses advanced analytical workflows resolving 9 strategic business objectives utilizing **Window Functions** (`RANK() OVER`), **Group By Aggregations, Date Manipulations, and CTEs** inside the database engine: 
| # | Business Analytical Metric Objective | SQL Architecture Tactic |
| :--- | :--- | :--- |
| **1** | **Payment Methods & Sales Volumes** | Comprehensive transactional volume indexing. |
| **2** | **Highest-Rated Product Category per Branch** | `RANK()` PARTITION BY Branch ORDER BY AVG(Rating) DESC |
| **3** | **Branch Operational Peak Busiest Days** | Volume analysis leveraging `TO_CHAR(date, 'Day')` mappings. |
| **4** | **Total Quantity Sold per Payment Sub-Type** | Aggregated usage density summaries across sales methods. |
| **5** | **Regional Category Rating Spreading by City** | Extremum rating distribution spreads using `MIN()`, `MAX()`, and `AVG()`. |
| **6** | **Category Net Profit Contribution** | Ranked product margins $\sum (\text{Total} \times \text{Profit Margin})$ |
| **7** | **Dominant Branch Payment Method System Preferences** | Common customer payment gateways via partitioned ranking CTEs. |
| **8** | **Daily Operational Sales Shifts Analysis** | Temporal parsing split into `Morning`, `Afternoon`, and `Evening`. |
| **9** | **Top 5 Year-Over-Year (YoY) Revenue Declines** | Multi-year comparative analysis using dual-joining dynamic CTE sets. |  
<br>  

# 🏃 Setup & Verification Sequence  
1. Clone this retail pipeline repo:🏃 Setup & Verification Sequence
``` bash
git clone https://github.com/yourusername/Predictive Sales Data Intelligence.git
```
2. Clone this retail pipeline repo:
``` bash
pip install pymysql psycopg2-binary sqlalchemy pandas
```
3. Run the interactive notebook to execute the cleaning mechanism pipeline, outputting the clean asset file (`walmart_clean_data.csv`).

4. Import your SQL query structures into your database engine to unlock enterprise retail insights!
   - *The file can be found here [Project SQL File](Resources/SQL_File.sql)*


<br>  

# 💡Future Improvements  
🔹 **1. 🏎️ Advanced Predictive Modeling & Forecasting**:  
<br>  
        - **Idea:** Transition the repository from a historical data analysis engine into a predictive analytics platform.  
<br>
        - **Implementation:** Integrate a machine learning module using `scikit-learn` inside our Python workflow to forecast sales volumes for upcoming weeks or predict which category will                   dominate a specific branch based on seasonal trends.  
<br>
        - **Value Add:** Demonstrates your capability to cross over from data analysis into data science and predictive analytics.  
<br>  

🔹 **2. 🎛️ Dynamic Business Intelligence (BI) Dashboard Integration:**  
<br>  
        - **Idea:** Connect the processed database layer directly to an interactive visual dashboard layer.
<br>  
        - **Implementation:** Provide an extension using Streamlit (in Python) or export connection files for Power BI / Tableau to turn your 9 core SQL business query solutions into live,                   interactive charts, graphs, and KPIs that executives can filter by City or Branch in real time.
<br>  
        - **Value Add:** Highlights your ability to translate raw database outputs into stakeholder-friendly visual assets.  

# 🤝 Connect With Me  

## 👨‍💻 Author  

**Rajay Jain**

* **📧 Email**: jainrajay2001@gmail.com  
* **💼 LinkedIn**: [www.linkedin.com/in/rajay-ajay-jain-a3abb4168](https://www.linkedin.com/in/rajay-ajay-jain-a3abb4168)  
* **🐙 GitHub**: [https://github.com/RajayJain](https://github.com/RajayJain)  

---

## ⭐ Support  

If you find this analysis framework resourceful or helpful for your retail applications, please consider giving this project repository a ⭐ on GitHub!

---

<p align="center">
  Made with ❤️ using Python, SQL & Power BI
</p>
