# agriBORA-Commodity-Price-Forecasting-Challenge
## **Business Understanding**

## **Overview**

Smallholder farmers across Africa often face price volatility and post-harvest losses of up to 40%. agriBORA is a startup aiming to help smallholder farmers in Kenya by offering certified warehouses where farmers can safely store their produce and receive digital warehouse certificates, enabling access to loans and the option of delayed selling. This provides flexibility for farmers in deciding the optimal time to sell their produce for maximum returns, and reduces storage losses.

Using historical prices of dry maize in Kenya, the task is to develop a machine learning solution to predict average weekly prices of maize in the counties of Kiambu, Kirinyaga, Mombasa, Nairobi and Uasin-Gishu. At each prediction step, your model should generate forecasts for two consecutive weeks. The forecasting period spans six consecutive weeks, frMom November 17, 2025 to January 10, 2026.

## **Problem Statement**

Maize prices in Kenya are volatile due to factors such as:

- Weather conditions i.e rainfall and drought
- Supply and demand dynamics
- Seasonal variations and harvest cycles
- Market shocks and policy changes

The challenge is to forecast short-term maize prices accurately using historical data from agriBORA and supplemental features from KAMIS, while accounting for trends, seasonality, and external factors. 

Accurate forecasts will help farmers time their sales effectively, increase earnings, and strengthen agriBORA’s integrated storage, credit, and market intelligence service to East African farmers.

## **Objectives**

### **Main Objective**

To predict average weekly sales of maize in the five target counties

### **Secondary Objectives**

- Incorporate external market data i.e KAMIS to improve prediction accuracy
- Explore potential correlations with seasonality, supply volumes, and other market indicators
- Build a reproducible forecasting pipeline that can be extended to other counties or commodities

## **Metrics of success**

- MAE (50%): measures the average magnitude of errors between predicted and actual values.
- RMSE (50%): measures the deviation of your predictions from the actual values, but penalises large errors more heavily.

##  **Data Understanding**


### **AgriBora Dataset**

| Feature                  | Type        | Description                           |
| ------------------------ | ----------- | ------------------------------------- |
| County                   | Categorical | County of the transaction             |
| Date                     | Datetime    | Date of the transaction               |
| WholeSale                | Numeric     | Wholesale price (**target variable**) |
| Commodity_Classification | Categorical | Type of maize (white, yellow, mixed)  |
| Year_Week                | String      | Week identifier (YYYY-WW)             |
| WeekofYear               | Numeric     | Week number in the year               |



### **KAMIS Dataset**

| Feature        | Type        | Description                                 |
| -------------- | ----------- | ------------------------------------------- |
| Commodity      | Categorical | Maize type (white, yellow, mixed)           |
| Classification | Categorical | Commodity classification (wholesale/retail) |
| Grade          | Categorical | Maize grade                                 |
| Sex            | Categorical | Not relevant for maize                      |
| Market         | Categorical | Market where price recorded                 |
| Wholesale      | Numeric     | Wholesale price                             |
| Retail         | Numeric     | Retail price                                |
| Supply Volume  | Numeric     | Volume sold                                 |
| County         | Categorical | County of market                            |
| Date           | Datetime    | Date of observation                         |
| Unit           | Categorical | Price unit (e.g., Ksh per 90kg bag)         |
| Source         | Categorical | Data source                                 |
| Year           | Numeric     | Year                                        |
| Month          | Numeric     | Month                                       |
| Year-Month     | String      | YYYY-MM                                     |
| Week           | Numeric     | Week number                                 |

## **Data Preprocessing**

### **Data cleaning**
- Handling missing values
- Handling outliers
- Dropping duplicates

### **Feature Engineering**

- Date conversion
- Creating seasonal cyclic features
- Lag features
- Rolling averages
- Rolling volatility

## **Exploratory Data Analysis (EDA)**
