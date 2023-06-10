# Weather-Forecasting-with-Machine-Learning
Data Analytics Bootcamp collaborative Project 4

Group Members: Ayokunle Oluwole, Tina Saravi, Haoyue Lin, and John Geng

# Dataset 

The data used was download from the Government of Canada Climate Weather Data. Three different weather station in toronto were picked, Billy Bishop Airport, Buttonville Airport, and Toronto Pearson Airport. 

# ETL 

# Extraction 
  
  Download the data from Government of Canada Climate Weather Data filtering by     monthly data. Billy Bishop Airport Monthly Data (1840-2006), Buttonville         Airport Monthly Data (1986-2015), and Toronto Lester B. Pearson Int'l Airport     Monthly Data (1937-2013). 
  
  Run each airports extraction file; billyairport_extraction.ipynb,                 buttonvilleairport_extraction.ipynb, and pearsonairport_extraction.ipynb. These   will create a CVS file called cleaned_billy.csv, cleaned_buttonville, and         cleaned_pearson.csv. 
  
  Uploaded these three cvs files to Railway to host a SQL sever for                 transformation of dataset. 

# Transformation 

  Run the SQL-ETL.ipynb to concatenate the three different csv files together.     Once the file has been concatenated, the file will now group and average ou       the mean temperature by year and month. 

# Load 
Running the SQL-ETL.ipynb file, the final dataset that is created is the  average_df dataframe. Using the average_df dataframe you can now run the machine learning module SARIMA to forcaste future weather for the city of Toronto based on historical dataset from 1840 - 2014. 

 
  
