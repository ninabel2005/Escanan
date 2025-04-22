
## Midterm Lab Task 2: Data Cleaning and Transformation Using Power Query

In this task, we worked with a raw dataset titled **Uncleaned_DS_jobs.csv**. The objective was to clean and transform the data using the **Power Query Editor** in Excel.

---

## Step 1: Data Cleaning

- Load the raw dataset into Power Query  
- Adjust the column widths and row heights for better visibility  
- Use the **Trim** function to remove unnecessary spaces  
- Eliminate **NULL** values from the dataset  
- Remove any **duplicate** entries  

---

## Step 2: Data Transformation

1. **Cleaning the Salary Estimate Column:**
   - Select the `Salary Estimate` column  
   - Go to **Transform > Extract > Text Before Delimiter** to remove text after the first parenthesis  

2. **Creating Minimum and Maximum Salary Columns:**
   - Use **Add Column > Column from Examples** to generate `Min Sal` and `Max Sal` based on the Salary Estimate  

3. **Adding Role Type Column:**
   - Navigate to **Add Column > Custom Column**
   - Create logic to classify job titles into categories like *Data Scientist*, *Data Analyst*, *Data Engineer*, etc.  

4. **Splitting the Location Column:**
   - Select the `Location` column  
   - Use **Transform > Split Column by Delimiter (Comma)** to separate city and state  

5. **Correcting Location Values:**
   - Create a **Custom Column** to standardize location names (e.g., converting "New Jersey" to "NJ", "California" to "CA")  

6. **Handling Negative Values:**
   - Filter out rows with negative values in the `Competitors` and `Industry` columns  

7. **Cleaning Company Names:**
   - Use **Transform > Replace Values** or **Remove Text** to eliminate unwanted content in the `Company Name` column  

---

## Step 3: Screenshots

**Before Data Cleaning**  
View of the raw dataset before any transformations:  
<img src="" align="center" height="350" width="600"/>

**After Data Cleaning**  
View of the dataset post-cleaning and transformation:  
<img src="" align="center" height="350" width="600"/>

---

## Step 4: Final Output Queries

- **Salary by Role Type (dup):**  
  A query displaying categorized job roles and their respective salary data  
  <img src="" align="center" height="350" width="600"/>

- **Salary by Company Size (ref):**  
  A query analyzing salaries based on company size or a related metric  
  <img src="" align="center" height="350" width="600"/>

- **Salary by State (ref):**  
  A query that breaks down salary data by geographical location  
  <img src="" align="center" height="350" width="600"/>

- **Original Dataset - Uncleaned DS Jobs:**  
  Snapshot of the raw dataset before any data manipulation  
  <img src="" align="center" height="350" width="600"/>

---

## Physical Data Model

(Insert the physical data model screenshot below)  
<img src="" align="center" height="350" width="600"/>

