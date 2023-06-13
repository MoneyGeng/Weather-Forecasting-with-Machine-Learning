# Weather-Forecasting-with-Machine-Learning
Data Analytics Bootcamp collaborative Project 4

Group Members: Ayokunle Oluwole, Tina Saravi, Haoyue Lin, and John Geng

# Dataset 

The data used was download from the Government of Canada Climate Weather Data. Three different weather station in toronto were picked, Billy Bishop Airport, Buttonville Airport, and Toronto Pearson Airport. 

# ETL 

## Extraction 
Download the data from Government of Canada Climate Weather Data filtering by monthly data. Billy Bishop Airport Monthly Data (1840-2006), Buttonville Airport Monthly Data (1986-2015), and Toronto Lester B. Pearson Int'l Airport Monthly Data (1937-2013). 
 
PySpark, is a powerful framework that was used to process and clean each CSV data. The first step was to start a SparkSession and load each CSV file for cleaning. After, we needed to examine the loaded data to understand its structure, columns, and data types before fitting each airports extraction file into a DataFrame in order to continue cleaning the data. 
 
Run each airports extraction file; billyairport_extraction.ipynb, buttonvilleairport_extraction.ipynb, and pearsonairport_extraction.ipynb. These will create a CVS file called cleaned_billy.csv, cleaned_buttonville, and       cleaned_pearson.csv. 
  
Uploaded these three cvs files to Railway to host a SQL server for transformation of dataset. 

## Transformation 
Run the SQL-ETL.ipynb to concatenate the three different csv files together. Once the file has been concatenated, the file will now group and average out the mean temperature by year and month. 

## Load 
Running the SQL-ETL.ipynb file, the final dataset that is created is the  average_df dataframe. Using the average_df dataframe you can now run the machine learning module SARIMA to forecast future weather for the city of Toronto based on historical dataset from 1840 - 2014. For the purpose of accuracy, the dataset used for forecasting is narrowed down to 1900-2013.

# Weather Forecasting with SARIMA
The SARIMA model, short for Seasonal Autoregressive Integrated Moving Average, is an advanced variation of the ARIMA model that has gain widespread recognition in time series analysis. Developed  an extension of the ARMA model from the 1970s, SARIMA has proven to be highly effective in modeling and forecasting time series data with both non-seasonal and peasonal petterns.

The ARIMA model, which captures relationships between observations at different time lags and moving average components, laid the foundation for SARIMA's success. By incorporating seasonal components into the ARIMA framework, SARIMA enhances its ability to accurately represent and predict time series data exhibiting recurring patterns at fixed intervals. This is particulary valuable in fields where data display seasonality, such as in monthly weather patterns.

## Parameter Selection
### Grid Search

ARIMA models are represented by the notation ARIMA(p, d, q), where the parameters p, d, and q correspond to the autoregressive, integrated, and moving average components, respectively. By incorporating these parameters, ARIMA enables us to effectively model and forecast time series data while considering important characteristics such as seasonality, trend, and noise.

The parameters with the lowest AIC score is ARIMA(1, 0, 1)x(0, 1, 1, 12)12 - with AIC score of 5456.289718415431

## Fitting the SARIMA Model
### Model Diagnostic
Running a model diagnostic to investigate any outliners in the dataset. In the normal Q-Q plot, we see that red KDE line follows closely with the N(0,1) normal distribution line. This is a good indication that the results are normally distributed.

| Coefficient | Standard Error |      z     | P-value | 95% CI Lower | 95% CI Upper |
|-------------|---------------|------------|---------|--------------|--------------|
|   ar.L1     |     0.7154    |   0.064    |  0.000  |    0.590     |    0.841     |
|   ma.L1     |    -0.5271    |   0.077    |  0.000  |   -0.678     |   -0.376     |
|  ma.S.L12   |    -1.0160    |   0.011    |  0.000  |   -1.037     |   -0.995     |
|   sigma2    |     3.0948    |   0.113    |  0.000  |    2.873     |    3.316     |


## Forecasting the Weather

To initiate the forecasts, the provided code assumes a starting point of January 2013. By setting the dynamic parameter to False, the code ensures that each forecast is generated based on the entire historical data available up to that specific point. This approach is known as one-step ahead forecasting. To evaluate the accuracy of our forecasts, we can plot both the actual and predicted values of the average daily temperature. To focus on the latter portion of the time series, we have applied a slicing technique to zoom in on the desired timeframe by modifying the date index. Overall, our forecasts align with the true values very well, showing a seasonal cycle of length 365 days.

### Evlation Metrics

The Mean Squared Error of our forecasts is 3.235

The Root Mean Squared Error of our forecasts is 1.799

The relatively low evaluation metrics validates the high accuracy of the SARIMA model's forecasts.

# Forescasting in the future
In this project, a remote postgreSQL server was hosted through Railway.app to facilitate efficient data management. The data was consolidated and prepared for analysis using pandas' comprehensive data manipulation capabilities.

The seasonal SARIMA (Seasonal Autoregressive Integrated Moving Average) model was employed to forecast weather patterns. This advanced model incorporated historical data, seasonal components, and underlying patterns to generate accurate predictions for time series data. Through model diagnostics were conducted to assess the SARIMA model's ability to capture the underlying patterns in the weather data.

The reliability of the forecasts was further validated through evaluation metrics, including Mean Squared Error (MSE) and Root Mean Squared Error (RMSE), which exhibited low values. These metrics served as indicators of the accuracy and dependability of the forecasts.

It is important to acknowledge the inherent challenges in weather forecasting, such as the multitude of exogenous variables and potential data inaccuracies. The limited size of the dataset used in this analysis posed a significant limitation. Future endeavors could involve exploring diverse datasets, incorporating additional variables, and adopting a more dynamic approach by iteratively refining the machine learning process through sequential forecasting.

Addressing these limitations and expanding the scope of the analysis would enhance the robustness and applicability of the weather forecasting model. This would empower informed decision-making and effective adaptation to changing environmental conditions.



