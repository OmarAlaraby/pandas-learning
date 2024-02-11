## Pandas Cheat Sheet

Here's a compilation of useful Pandas commands for data manipulation and exploration.

### Basic Operations

- `df.shape`: Returns the number of rows and columns.
- `df.info()`: Returns full info of the data including datatypes.
- `pd.set_option('display.max_columns', 85)`: Adjusts the maximum number of columns to display.

### Data Viewing

- `df.head()`: Views the first 5 rows.
- `df.tail()`: Views the last 5 rows.
- Slicing:
  - `df.iloc[]` or `df.loc[]`: Integer location or label-based indexing.
  - `df.loc[0:2, 'Hobbyist']`: Slicing by label.
  
### Indexing

- `df.set_index('email', inplace=True)`: Sets the email as the index.
- `df.reset_index(inplace=True)`: Resets the index.
- `pd.read_csv(file_path, index_col='col_name')`: Sets index while reading CSV.

### Sorting

- `df.sort_index()`, `df.sort_index(ascending=False)`: Sorts the index.
- `df.sort_values(by=['col1'], inplace=True)`: Sorts values by a column.

### Filtering and Selection

- `df['Country'].isin(countries_list)`: Checks if values are in a list.
- `df['col_name'].str.contains(name, na=False)`: Checks if a column contains a string.

### Data Modification

- `df.rename(columns={'old_name': 'new_name'}, inplace=True)`: Renames columns.
- `df.drop_duplicates()`: Removes duplicates.
- `df.loc[2] = ['row1', 'row2', ... ]`: Modifies data in rows.

### Data Transformation

- `df['email'].str.lower()`: Converts column to lowercase.
- `df['email'].apply(function_name)`: Applies a function to the data.
- `df.apply(len, axis='rows')`: Applies function along rows.

### Missing Data Handling

- `df['col_name'].map({'old_val': 'new_val', 'old': 'new'})`: Maps values.
- `df.replace('NA', numpy.nan, inplace=True)`: Replaces values.
- `df.fillna('value')`: Fills missing values.

### Data Splitting and Aggregation

- `df['full_name'].str.split(' ', expand=True)`: Splits cell into multiple columns.
- `df.append(df2, ignore_index=True, sort=False)`: Adds rows from another DataFrame.

### Data Deletion

- `df.drop(index=4)`: Deletes a row by index.
- `df.drop(index=df[df['last'] == 'Doe'].index)`: Deletes rows based on condition.

### Statistical Analysis

- `df['col_name'].median()`: Computes the median.
- `df.describe()`: Describes the DataFrame.
- `df.value_counts()`: Computes value counts.

### Grouping and Aggregation

- `df.groupby(['Country'])['salary'].median()`: Groups data and computes median salary.
- `df.groupby(['Country'])['salary'].agg(['median', 'mean'])`: Aggregates statistics for groups.

### Date Handling

- `pd.to_datetime(df['Date'], format='%Y-%m-%d %I-%p')`: Converts to datetime.
- `df['Date'].dt.day_name()`: Extracts day name from dates.

### Visualization

- `df['heights'].plot()`: Visualizes the data using Matplotlib. 

**Note**: For detailed visualization, refer to the Matplotlib documentation.

This cheat sheet serves as a quick reference for common Pandas operations. For more advanced operations and detailed explanations, refer to the Pandas documentation.
