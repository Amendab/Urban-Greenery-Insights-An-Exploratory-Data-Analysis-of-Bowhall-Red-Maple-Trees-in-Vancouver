# Urban-Greenery-Insights: An-Exploratory-Data-Analysis-of-Bowhall-Red-Maple-Trees-in-Vancouver

**Project Description**

This project examines the trends in planting Bowhall Red Maple trees across Vancouver between 2014 and 2024. Using data sourced from the City of Vancouver’s Open Data Portal, the analysis focuses on key metrics such as tree heights, diameters, and their correlations, alongside yearly planting patterns. The study provides actionable insights into urban forestry practices, contributing to the optimization of greenery management strategies for sustainable urban development.

**Objective**

To explore the trends in planting Bowhall Red Maple trees in Vancouver and answer:
What patterns and insights can be derived from the planting activities of Bowhall Red Maple trees over the past decade (2014–2024)?

The analysis also aims to examine the correlation between Height Range ID and Diameter, offering deeper insights into the characteristics of planted trees. This will support recommendations for enhancing future urban forestry initiatives.

**Dataset**

The dataset utilized in this analysis was sourced from the City of Vancouver’s Open Data Portal. It originally contained 21 columns and 429 records, providing detailed information about Bowhall Red Maple trees planted on city boulevards between 2014 and 2024.

Key Columns Used:
- Tree ID: Unique identifier for each tree.
- Civic Number: Specifies the location of each tree.
- Common Name: Identifies the species as Bowhall Red Maple.
- Height Range ID: Categorizes trees into predefined height groups.
- Height Range: Indicates tree height ranges (e.g., 0–10 ft, 10–20 ft).
- Diameter: Measures tree trunk diameter in inches.
- Date Planted: Records the planting date for each tree.

After data cleaning, irrelevant fields were removed, leaving 7 key columns essential for answering the business question and calculating the correlation between Height Range ID and Diameter.

**Methodology**

- Step 1: Data Collection and Storage
Storage in AWS S3:
Raw dataset uploaded to an S3 bucket, organized into a folder structure labeled Street_Trees_Ingestion_Year=2024.
Stored using the “Standard” class for optimal access and minimal latency.

- Step 2: Data Cleaning and Profiling

Profiling with AWS Glue DataBrew:
Identified data quality issues such as missing values, outliers, and inconsistent formats.
Profiling results saved in the Data Profiling folder in S3.

Cleaning Steps:
Handled missing values, standardized formats, and corrected data types.
Removed irrelevant columns, retaining 7 essential fields.
Cleaned data saved in both Parquet and CSV formats for efficient querying and accessibility.

- Step 3: Data Transformation and ETL Pipeline Design

ETL Process:
Data was aggregated by year, and metrics such as the average Height Range ID and average Diameter were calculated.
Correlation between these two metrics was analyzed to determine their relationship.
Output saved in S3 under a folder named Average_Height_Range_ID_and_Diameter_Analysis.

Pipeline Outputs:
System Output: Data stored in Parquet format for efficient querying.
User Output: Data stored in CSV format for interpretation.

- Step 4: Data Analysis and Visualization
Querying with AWS Athena:
SQL queries performed to analyze relationships between metrics like Height Range ID and Diameter.

Height-Diameter Correlation Analysis:
The analysis revealed a direct correlation between Height Range ID and Diameter across years, providing insights into the characteristics of trees planted during specific periods.

**Visualization Tools:**

Generated visualizations through the “Analyze” tab on the Open Data Portal, complemented by Excel-based charts for in-depth analysis.
Examples include yearly planting trends and scatter plots for height-diameter correlations.
Insights and Outcomes

**Key Findings:**

Correlation Between Metrics:
A strong correlation was observed between the Height Range ID and Diameter, indicating that taller trees (higher Height Range ID) were associated with larger diameters.
For example, in 2015, the average Height Range ID (3.81) and Diameter (3 inches) peaked, signifying a preference for planting taller and more mature trees.

Tree Size Preferences:
Trees in the 10–20 ft range (Height Range ID: 1) were the most commonly planted.
Yearly Variations:
Taller trees were planted in years like 2015 and 2018, reflecting potential strategic shifts.

**Actionable Insights:**

Recommendations to align planting strategies with urban forestry goals, such as prioritizing tree height categories suited to urban aesthetics and environmental needs.
Tools and Technologies
AWS S3: Secure storage for raw, cleaned, and transformed datasets.
AWS Glue DataBrew: For profiling and cleaning data.
AWS Athena: SQL-based querying for deriving insights.
City of Vancouver’s Open Data Portal: Sourced dataset and generated additional visualizations.
Microsoft Excel: For creating advanced visualizations and presentation-ready graphs.

**Deliverables**

Planting Trends: Identification of yearly planting patterns.
Height-Diameter Correlation: Analysis of the relationship between Height Range ID and Diameter, highlighting patterns over time.
Tree Size Preferences: Insights into the most frequently planted height categories.
Strategic Recommendations: Suggestions for future planting strategies to enhance urban greenery.
