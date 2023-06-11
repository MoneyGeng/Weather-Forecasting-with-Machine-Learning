# Weather-Forecasting-with-Machine-Learning
Data Analytics Bootcamp collaborative Project 4

Group Members: Ayokunle Oluwole, Tina Saravi, Haoyue Lin, and John Geng

# Dataset 

<img width="1194" alt="pic 1" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/2febb64d-eb70-48da-8ea0-b2e1e40e5859">


The data used was download from the Government of Canada Climate Weather Data. Three different weather station in toronto were picked, Billy Bishop Airport, Buttonville Airport, and Toronto Pearson Airport. 

# ETL 


# Extraction 
  
  Download the data from Government of Canada Climate Weather Data filtering by     monthly data. Billy Bishop Airport Monthly Data (1840-2006), Buttonville         Airport Monthly Data (1986-2015), and Toronto Lester B. Pearson Int'l Airport     Monthly Data (1937-2013). 
  
  Run each airports extraction file; billyairport_extraction.ipynb,                 buttonvilleairport_extraction.ipynb, and pearsonairport_extraction.ipynb. These   will create a CVS file called cleaned_billy.csv, cleaned_buttonville, and         cleaned_pearson.csv. 
  
  Uploaded these three cvs files to Railway to host a SQL sever for                 transformation of dataset. 



<img width="1014" alt="pic 2" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/ec156bc8-c385-4a0f-bdc2-cbcde8ca5322">


<img width="1011" alt="pic 3" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/5cf3bba8-1200-4ee7-ba5d-ed3efc444331">



<img width="521" alt="pic 4 " src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/3ad354bf-b49f-4994-a8b8-c024d0da7338">




# Transformation 

<img width="877" alt="pic 5" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/90c004d9-8d7b-4eaf-8b71-03cff7765c30">




  Run the SQL-ETL.ipynb to concatenate the three different csv files together.     Once the file has been concatenated, the file will now group and average ou       the mean temperature by year and month. 

# Load 
Running the SQL-ETL.ipynb file, the final dataset that is created is the  average_df dataframe. Using the average_df dataframe you can now run the machine learning module SARIMA to forcaste future weather for the city of Toronto based on historical dataset from 1840 - 2014. 

 



<img width="738" alt="pic 6 " src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/df2c1ef9-a1d4-4eca-b3e4-2d51d77b46a2">




<img width="760" alt="pic 7 " src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/91ad015f-114f-4c18-8f19-8b80379e1407">



<img width="1062" alt="pic 8 " src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/1cb41aeb-f84f-4293-b8d9-cafd9491c377">



<img width="1360" alt="pic 9" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/7cce8cdd-080f-4452-add7-c9559cf6018d">



<img width="1067" alt="pic 10" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/d997adee-412b-4541-a369-c49f6646a2be">



<img width="806" alt="pic 11" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/4591ea7b-9a3f-49d2-bccd-ce949e38bca5">


<img width="1127" alt="pic 12" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/f35cdb5b-ed30-40b7-a4d8-7a1e614d0dcc">



<img width="980" alt="pic 13" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/f9e2380f-407d-426b-af4b-c496f4af93a3">



<img width="992" alt="pic 14" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/80cfca70-275b-4864-abef-c039d8b69349">


<img width="1055" alt="pic 15" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/c8627484-a6ac-4678-97fd-90c010963dbf">


<img width="713" alt="pic 16" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/6274cf19-e0a1-46c0-80c1-32fccecd09d9">


<img width="808" alt="pic 17" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/31aeb1e0-0fca-45e2-b691-1cb456458cf0">


<img width="1003" alt="pic 18" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/659c0718-56ff-4121-8bc9-ab7fbeecc4a8">



<img width="1357" alt="pic 19" src="https://github.com/MoneyGeng/Weather-Forecasting-with-Machine-Learning/assets/119383340/0a9f4bcd-1f1b-44d9-95c9-51a54981f191"> 
