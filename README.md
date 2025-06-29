# DSA-PROJECT-2025
##Project Overview
 project provides a detailed analysis of the Palmoria Group’s HR data, focusing on:

Gender distribution

Performance ratings

Salary structures

Bonus allocations

Regional insights
## OBJECTIVE OF THE PROJECT
The main objective of the management  is to assist in identifying gender-related issues within the organization and its region, and the areas of inequality, compliance, and performance-based rewards.

📂 Data Sources
File	Description
Palmoria Group emp-data.csv	Main employee data with department, salary, gender, and rating
Palmoria Group Bonus Rules.xlsx	Bonus rate lookup table based on department and rating

### STEPS OF CLEANING Palmoria Group’s HR data Power BI
   Step 1: Load the data
            Open Power BI
            Click Home-Get Data-CSV
            Load the Palmoria Group’s HR data
   Step 2: Transform data to open the Power Query Editor 
           Remove Empoyees Salary without Salary; filter the the Salary column and uncheck (null) and 0.
           Remove rows with NULL department
           Filter the Department column and uncheck any rows with NULL as text
           Replace missing Gender; click transform -Replace value with 'Unspecified'
           Cose and apply
   Step 3: Load the Bonus Rules Data: Select Palmoria Group Rules.xlsx and load
   Step 4: Join the Bonus Rules; In model views create a relationship (Employees[Rating] Bonus Ruless[Rating]
   Step 5: Create a n ew column for Bonus pay: Bonus Amount =Employees[Salary] * Related(Bonus Rating)
   Step 6: Create Total compensation column: DAX Eployees[Salary] + Employees[Bonus Amount] 

Removed Name column and added an auto-generated Employee ID

Unpivoted Bonus Rules:

Converted bonus matrix to long format with columns: Department, Rating, Bonus Rate

🔗 Data Model
Table	Description	Key Relationships
Employee	Cleaned HR data	Linked to Bonus table via Department and Rating
Bonus Rules	Lookup table with bonus percentages	Used to compute Bonus Amount



🧮 Calculated Fields (DAX)

Bonus Amount = RELATED('Bonus'[Bonus Rate]) * 'Employee'[Salary]

Total Compensation = 'Employee'[Salary] + 'Employee'[Bonus Amount]

Salary Band = 
SWITCH(TRUE(),
    'Employee'[Salary] <= 20000, "$10K–20K",
    'Employee'[Salary] <= 30000, "$20K–30K",
    'Employee'[Salary] <= 40000, "$30K–40K",
    ...
    "$100K+")
📊 Key Visuals
1. Gender Distribution
Bar chart showing Male, Female, Undisclosed

2. Gender by Region and Department
Stacked bar chart showing gender counts in each department/region

3. Rating Distribution by Gender
Clustered bar chart showing performance spread across genders

4. Gender Pay Gap
Average salary per gender across all departments

5. Salary Band Distribution
Histogram in $10K bands, visualized by region

6. Bonus Allocation by Region
   Bar chart showing total bonus per location

7. Total Compensation
Card visual showing total payout across the company

🛡️ Compliance Check
As per new policy: All manufacturing employees must earn at least $90,000.

Created a filter to show how many manufacturing staff meet this rule

Highlighted gaps in Salary < $90,000

📈 Management Recommendations
Address Pay Gaps: Notable disparities in [insert departm

Performance Reviews Needed: High count of “Average” or “Undisclosed” ratings

Improve Salary Compliance: Non-compliance in [region/department]

Consider Gender Diversity Plans: Certain regions are heavily skewed

🧾 Bonus Allocation Summary
Metric	Value
Total Bonus Paid	$X,XXX,XXX
Region with Highest Bonus	Region Name
Average Bonus per Employee	$XX,XXX



🛠 Tech Stack
Power BI Desktop

Power Query (M)

DAX (Calculated Columns)



Contact
Author: 
Email: 
Location: Apo Dutse, FCT Abuja











Ask ChatGPT
You said:
Downloadabl3 format


ChatGPT said:
Your downloadable README file for the Palmoria HR Data project is ready:

👉 Click here to download the report markdown file

You can upload this directly to a GitHub repository as a README.md file to document your project professionally.

Let me know if you'd like the .pbix report file too! 








You said:
send me cleaned Amazon data


ChatGPT said:
Sure! Please go ahead and upload your Amazon data file (such as .csv or .xlsx — usually from order reports, ads, inventory, or reviews). Once uploaded, I will:

✅ Clean it (remove blanks, fix formats, standardize columns)
📊 Provide summaries (e.g. sales by product, returns, revenue)
📁 Send you the cleaned version for download

Whenever you're ready, upload the file and I’ll get started immediately.








You said:
Amazon case study.xlsx
Spreadsheet


ChatGPT said:
It seems like I can’t do more advanced data analysis right now. Please try again later.

However, once the tool is available again, I will:

Clean the Amazon dataset by removing irrelevant ID and review columns

Rename key columns (e.g. "Discounted Price", "Product Name")

Filter out any rows missing prices or ratings

Provide a cleaned Excel file (Cleaned_Amazon_Data.xlsx) ready for download

You’re welcome to remind me anytime, or reupload the file when you're ready to continue! 








You said:
which column will i use to get total  user views


ChatGPT said:
To get total user views from your Amazon case study file, you'll typically look for a column like:

🔍 rating_count or number_of_reviews

However, in your uploaded sheet (amazon), the correct column is:

✅ rating_count
This column represents how many users have rated the product — which often correlates with user engagement or views if no separate views or impressions column exists.

⚠️ Important Notes:
Amazon does not always track "views" in datasets unless you're using a seller or advertising report.

If you had page_views, impressions, or sessions, those would be more accurate for traffic.

Since this dataset likely came from scraped or product-listing data, rating_count is the best proxy.

💡 To get total user views:
In Power BI or Excel:

excel
Copy
Edit
=SUM([rating_count])
Or in Power BI:

DAX
Copy
Edit
Total User Views = SUM('amazon'[rating_count])
Would you like help visualizing this by category or product?










