
## OVERVIEW
 project provides a detailed analysis of the Palmoria Group’s HR data, focusing on:

   -Gender distribution

   -Performance ratings

   -Salary structures

   -Bonus allocations

   -Regional insights
## 🔥 Highlights
- Analyzed  874 Employees records with 430 males 406 females and 38 unspecified genders, also with three regions(kaduna,Abuja and Lagos using Power BI
- Delivered HR insights using Power BI and DAX measures
- Clean, reusable datasets for reproducibility
##  Objective
Identify gender equality issues and salary distribution trends in the Palmoria Group’s workforce, with focus on:
- Gender distribution by department and region
- Pay gap detection
- Minimum wage compliance ($90,000)
- Bonus distribution based on performance
  ## Data Sources
    File	Description
    palmoria Group emp-data.csv	Main employee data with department, salary, gender, and rating
    Palmoria Group Bonus Rules.xlsx	Bonus rate lookup table based on department and rating

     ### STEPS OF CLEANING Palmoria Group’s HR data Power BI
  
    -Step 1: Load the data
           - Open Power BI
           - Click Home-Get Data-CSV
           - Load the Palmoria Group’s HR data
  
   -Step 2: Transform data to open the Power Query Editor 
          - Remove Empoyees Salary without Salary; filter the
   the Salary column and uncheck (null) and 0.
  
           -Remove rows with NULL department
          -Filter the Department column and uncheck any rows with NULL as text
   Replace missing Gender; click transform -Replace value with 'Unspecified'
           Close and apply
  
   -Step 3: Load the Bonus Rules Data: Select Palmoria Group Rules.xlsx and load
  
  -Step 4: Join the Bonus Rules; In model views create a relationship (Employees[Rating] Bonus Ruless[Rating]
  
   -Step 5: Create a n ew column for Bonus pay: Bonus Amount =Employees[Salary] * Related(Bonus Rating)
  
   -Step 6: Create Total compensation column: DAX Eployees[Salary] + Employees[Bonus Amount]

### Unpivoted Bonus Rules:

    -Converted bonus matrix to long format with columns: Department, Rating, Bonus Rate

   ### Data Model
    Table	Description	Key Relationships
    Employee	Cleaned HR data	merged to Bonus table via Department and Rating
    Bonus Rules	Lookup table with bonus percentages	Used to compute Bonus Amount.



### Calculated Fields (DAX)

     - Bonus Amount = [Bonus Rules]) * [Salary]

    -Total Compensation = 'Employee'[Salary] + 'Employee'[Bonus Amount]

-Salary Band = 
-SWITCH(TRUE(),
    -'Employee'[Salary] <= 20000, "$10K–20K",
    -'Employee'[Salary] <= 30000, "$20K–30K",
    -'Employee'[Salary] <= 40000, "$30K–40K",
    -...
   - "$100K+")
#### Insights based on the Analysis
  -1. Gender Distribution
    -Bar chart showing Male, Female, Undisclosed

  -2. Gender by Region and Department
     -Stacked bar chart showing gender counts in each department/region

  -3. Rating Distribution by Gender
     -Clustered bar chart showing performance spread across genders

   -4. Gender Pay Gap
       -Average salary per gender across all departments

   -5. Salary Band Distribution
    -Histogram in $10K bands, visualized by region

   -6. Bonus Allocation by Region
   Bar chart showing total bonus per location

   -7. Total Compensation
   
     ## some outcome of the Analysis
- **Gender imbalance** Most of departments have gender imbalance 
- **Pay gap** observed Unspeciied genders have higher average of salary pay than others.
- 68.54% of employees are  **below $90,000** threshold and Mr.Gamma cannot meet up with the minimum wage.
- Bonus payments align well with performance ratings
- Most valuable performers found in

### Recommendations
         -Review Salary Equity: Ensure compensation is perform and role-driven, not biased by gender or region

       -Performance Reviews Needed: High count of “Average” or “Undisclosed” ratings

       -Improve Salary Compliance

       -Local review: Assess productivityto head count ratio  in Kaduna vs Lagos/Abuja.

        -Consider Gender Diversity Plans: Certain regions are heavily skewed

 ## Bonus Allocation Summary
  -Metric	Value
   -Total Bonus Paid =$1.19m
   
    -Region with Highest Bonus Amount	Region= Kaduna($810.23k)
    
     -Average Bonus per Employee= $1361.55 
https://github.com/elisharot/DSA-PROJECT-2025/blob/61ac20ac9c5351d341147a7ca352fee73ace5f9b/palmoria%20pc.png
     ####  Tools Used
- Power BI (Data Cleaning, Relationships, Visualizations)
- GitHub (Project documentation)



  -Contact: 08100561918
  
  Author: Rotdang Yilgen Elisha
  
Email: rotdangelisha@gmail.com

Location: Apo Dutse, FCT Abuja

https://www.linkedin.com/posts/rotdang-elisha-5b916a2b7_i-want-to-express-my-heartfelt-gratitude-activity-7343671369345216512-2uPp?utm_source=share&utm_medium=member_android&rcm=ACoAAEwFKN0B7zgJJz3F9bXm1SKBWE4CANXhmYQ
























