# Assignment
Created a python script
import pandas as pd
import numpy as np
import boto3
import pyodbc

# Connected to SQL Server
connection_string = "DRIVER={ODBC Driver 17 for SQL Server};SERVER=localhost,1433;DATABASE=root;UID=sa;PWD=Shravani@5796
conn = pyodbc.connect(connection_string)

# Retrieved data from the table
query = "SELECT * FROM SampleTable;"
df = pd.read_sql(query, conn)

# Saved the data as a CSV file
csv_file_path = "wc_champions.csv"
df.to_csv(wc_champions.csv, index=False)

# Upload the CSV file to AWS S3
s3_bucket_name = "prasqaure"
s3_file_path = "wc_champions.csv"
s3_client = boto3.client("s3")
s3_client.upload_file(prasqaure, wc_champions.csv)
