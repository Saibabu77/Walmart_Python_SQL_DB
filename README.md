# Walmart_Python_SQL_DB(Mysql and Postgre)

![WALMART DB](https://github.com/user-attachments/assets/cb30b8ca-be28-4df7-a881-43cebcb174d7)

This project focuses on cleaning Netflix data using Python and Pandas, handling missing values, duplicates, and formatting inconsistencies. The cleaned dataset is then structured and uploaded to an SQL database for efficient querying and analysis

# Netflix Data Cleaning and SQL Integration

## Project Overview
This project involves cleaning a Netflix dataset using Python and Pandas to remove inconsistencies, missing values, and duplicates. The cleaned data is then structured and uploaded to an SQL database for efficient querying and analysis.

## Technologies Used
- **Python** (Pandas, NumPy, SQLAlchemy)
- **SQL** (MySQL/PostgreSQL/SQLite)
- **Jupyter Notebook**

## Data Cleaning Process
1. **Loading the Dataset**
```python
import pandas as pd

# Load the dataset
file_path = "netflix_data.csv"
df = pd.read_csv(file_path)
```

2. **Handling Missing Values**
```python
# Checking for missing values
df.isnull().sum()

# Filling or dropping missing values
df.fillna(method='ffill', inplace=True)  # Forward fill as an example
```

3. **Removing Duplicates**
```python
# Drop duplicate rows
df.drop_duplicates(inplace=True)
```

4. **Formatting Data**
```python
# Convert date columns to datetime format
df['release_date'] = pd.to_datetime(df['release_date'])
```

## Connecting to SQL Database
1. **Setting Up SQL Connection**
```python
from sqlalchemy import create_engine

# Database connection string (Modify based on your SQL database)
engine = create_engine('sqlite:///netflix_data.db')
```

2. **Uploading Cleaned Data to SQL**
```python
# Storing the cleaned dataset into SQL
df.to_sql('netflix', con=engine, if_exists='replace', index=False)
```

## Querying Data from SQL
```python
import sqlalchemy

# Query example
query = "SELECT * FROM netflix WHERE genre='Comedy'"
df_sql = pd.read_sql(query, con=engine)
```

## Results and Insights
- Successfully cleaned and structured Netflix data.
- Efficiently stored and queried data from SQL.
- Ready for further analysis and visualization.

## Future Improvements
- Automating the data pipeline.
- Enhancing data visualization.
- Expanding dataset with additional sources.

## How to Run the Project
1. Install required libraries:  
   ```bash
   pip install pandas numpy sqlalchemy
   ```
2. Run the Jupyter Notebook or Python script.
3. Connect to your SQL database and execute queries.

Example: question 1. Determine the average, minimum, and maximum rating of categories for each city?
Answer
![Screenshot 2025-02-26 145344](https://github.com/user-attachments/assets/01a0a6d6-083e-4d9d-b4ba-28fe1b3838f0)




## Author
Sai babu



