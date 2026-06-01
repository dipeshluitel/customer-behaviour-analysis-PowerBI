# Connected to Postgresql to store the exploratory data into the Database
## Following steps are followed:
- pip installed `psycopg2-binary`, `sqlalchemy` along with `dotenv` for hiding credentials


``` import os ```

``` load_dotenv() ```


``` username = os.getenv("DB_USERNAME") ```

`password = os.getenv("DB_PASSWORD") `

`host = os.getenv("DB_HOST") `

`port = os.getenv("DB_PORT") `

`database = os.getenv("DB_NAME")`

`engine = create_engine(f"postgresql+psycopg2://{username}:{password}@{host}:{port}/{database}")`

`table_name = "customer"`
`df.to_sql(table_name,engine, if_exists = "replace", index = False)`
