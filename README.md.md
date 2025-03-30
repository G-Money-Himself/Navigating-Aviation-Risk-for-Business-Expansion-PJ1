```python
import pandas as pd

# Load the dataset from your Jupyter Notebook
file_path = "Navigating Aviation Risks for Business Expansion .ipynb"

# Load the dataset (assuming it's in a CSV format)
df = pd.read_csv("cleaned_aviation_data.csv", encoding = 'latin1', low_memory = False)
```


```python
import pandas as pd

# Load the dataset from your Jupyter Notebook
file_path = "Navigating Aviation Risks for Business Expansion .ipynb"

# Load the dataset (assuming it's in a CSV format)
df = pd.read_csv("cleaned_aviation_data.csv", encoding = 'latin1', low_memory = False)

# Select relevant columns for Tableau
columns_needed = [
    "Model", "Aircraft.damage", "Broad.phase.of.flight", 
    "Total.Fatal.Injuries", "Purpose.of.flight", "Event.Date"
]
df_cleaned = df[columns_needed].copy()  # ✅ Add .copy() to create an independent copy
df_cleaned.loc[:, "Event.Date"] = pd.to_datetime(df_cleaned["Event.Date"])


# Fill missing values with "Unknown"
df_cleaned.fillna("Unknown", inplace=True)

# Export cleaned data for Tableau
df_cleaned.to_csv("Aviation_Data_Cleaned.csv", index=False)

print("✅ Data cleaned & saved as 'Aviation_Data_Cleaned.csv' for Tableau.")
```

    ✅ Data cleaned & saved as 'Aviation_Data_Cleaned.csv' for Tableau.
    


```python

```


```python
jupyter nbconvert --to markdown your_notebook.ipynb
mv your_notebook.md README.md
```


      File "<ipython-input-5-fbea8c09eb08>", line 1
        jupyter nbconvert --to markdown your_notebook.ipynb
                ^
    SyntaxError: invalid syntax
    



```python

```
