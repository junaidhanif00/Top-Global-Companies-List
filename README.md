# Top-Global-Companies-List

import pandas as pd 
import requests
import csv
from bs4 import BeautifulSoup

baseurl = 'https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue'
page = requests.get(baseurl)
soup = BeautifulSoup(page.text, 'html')
  cleaned_titles = []

# Loop through each title and clean it
for title in world_title:
    cleaned_title = title.text.strip().replace('\n', '')  # Remove \n and strip whitespace
    print(cleaned_title)  # Optional: Print each cleaned title
    cleaned_titles.append(cleaned_title)  # Add cleaned title to the list
# Create the DataFrame using the cleaned titles as columns
df = pd.DataFrame(columns=cleaned_titles)
# Display the DataFrame

for row in column_data[1:]:
   row_data = row.find_all('td')
   individual_rowdata = [data.text.strip() for data in row_data]
   length = len(df)
   df.loc[length] = individual_rowdata
  df.to_csv('TopCopmanies.csv')
