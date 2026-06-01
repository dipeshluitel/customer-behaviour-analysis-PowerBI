# Things I have done in order
## Step 1: *Getting Insights on Data sets*
- Customer behaviour Data is loaded locally
- Checked all the columns using `df.info()`
- Numerical and Statistical values are checked using `df.describe(include='all')`

*Insights*: `We found there are a total of 18 columns of the following data types: int, str and float.`

### Checking for Null Column
Used: `df.isnull().sum()`
- *Insights*: `Found Review Rating has 37 null columns`
- *Action*: `We will Replace Null with median`
  
### Finding out the median review rating with each category and replace the missing value
*Code Used for achieving this*: `df['Review Rating'] = df.groupby('Category')['Review Rating'].transform(lambda x: x.fillna(x.median()))` 

### Transforming Columns name to consistent format (snake_case)
`df.columns = df.columns.str.lower()`
`df.columns = df.columns.str.replace(' ','_')`
- *Insights*: Got unusal column name as `purchase_amount_(usd)` so renamed it to `purchase_amount`
  
`df = df.rename(columns = {'purchase_amount_(usd)':'purchase_amount'})`
  
