Project Title: Global Travel Trends & Resilience Analysis ✈️🌍
This project delivers key insights into global tourism resilience and flight price seasonality using Python for robust data transformation and Power BI for impactful visualization.

1. Project Goal: Key Questions Answered
This analysis directly addresses the two critical business questions defined at the start of the project:

Country Resilience: Which economic and societal factors correlate with a country's tourism resilience or recovery after a major disruption (e.g., the 2020 global events)?

Travel Seasonality: What is the seasonal trend of international flight prices, and when are the most and least expensive times to travel?

2. Tools & Technologies Used
Tool/Technology,Used For
Google Colab (Python/Pandas),"Data Acquisition, Cleaning, Transformation, & Merging (ETL). This was the primary tool for cleaning and combining raw data into two final CSV files."
Microsoft Power BI,"Data Modeling, DAX, & Visualization. Used for dashboard creation, final data modeling, and creating the Visitor_Tier column."
Generative AI (ChatGPT & Gemini),Troubleshooting & Debugging. Used to assist in resolving complex coding and syntax errors encountered during the data cleaning phase.

3. Data Sources, Preparation, & Final Outputs
The project used three raw data files, which were processed and merged in Google Colab (Python/Pandas) to create the two clean output files (data/cleaned folder):

Final Output File,Raw Source Files Used,Key Transformations in Colab
travel_master_country_data.csv = world_tourism_economy_data.csv and World-happiness-report-updated_2024.csv,Merged on Country. Verified latest complete data year (2020) and cleaned columns.
flights_seasonal_cleaned.csv = Scraped_dataset.csv,"Aggregated by Travel_Month to calculate Avg_Flight_Price, significantly reducing data volume."

4. Technical Challenges & Solutions (Showcasing Problem-Solving)
The data pipeline presented several significant real-world challenges, which required specialized solutions:

A. Initial Data Loading & Cleaning Errors (Python/Colab)
Challenge,Issue Description,Solution Implemented
Unicode Decode Error,"Attempting to use pd.read_csv() to view the head of the raw files resulted in a UnicodeDecodeError, preventing data inspection.",Resolved by specifying the correct encoding: added the parameter encoding = 'latin-1' to the pd.read_csv() function.
Data Integrity Verification,"The tourism data documentation was misleading (claimed data up to 2023, but was only complete through 2020).",Had to run a preliminary query on the raw file to accurately determine the last complete year (2020) before running the final data transformation script.
Date/Format Mismatch & Kernel Issue,"After initial cleaning, the flights_seasonal_cleaned file displayed 0 rows due to a date format mismatch. This was followed by an unrelated AttributeError when converting a string to a numeric type.","Required professional debugging assistance (from ChatGPT/Gemini), a manual correction of the date format logic, and finally, restarting the Colab kernel to clear memory and cache before rerunning all scripts to successfully merge and export."

B. Visualization Challenge (Power BI)

Challenge,Issue Description,Solution Implemented
Faded Map Colors,"The Filled Map visualization lacked a dedicated color saturation field, causing the default colors to appear faded and indistinct when mapping a numerical measure (like Visitors_2020).","Created a custom "Visitor_Tier" column using a DAX formula in Power BI to categorize resilience into nominal measures (e.g., 'High Resilience', 'Low Resilience'). Used this new categorical column as the Legend, allowing the manual selection of bright, high-contrast color palettes for a clearer visual analysis."

5. Project Findings (Questions Answered)
Key Question,Finding/Conclusion,Visual Confirmation
Country Resilience,"The Scatter Plot shows a strong relationship, where countries exhibiting a higher Happiness Score also demonstrated greater resilience (higher Tourism Revenue) during the 2020 disruption.",Scatter Plot (Tourism Revenue vs National Happiness)
Travel Seasonality,"The Line Chart clearly identifies periods of peak and trough travel cost, concluding that international flight prices are typically lowest in March(3), among Jan(1), Feb(2) and March(3).",Line Chart (Average Flight Price Seasonality)