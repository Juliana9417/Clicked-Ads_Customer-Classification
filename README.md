# Clicked-Ads_Customer-Classification
Predict Clicked Ads Customer Classification by using Machine Learning

## 📂 **Stage 0 : Problem Statement**
### Background:
A company in Indonesia is striving to enhance the effectiveness of its advertisements with the primary goal of capturing the attention of potential customers. Strategically utilizing advertisements is key to ensuring that the campaigns reach the right audience and achieve optimal conversions. Therefore, the company aims to leverage its historical advertisement data to understand patterns related to ad effectiveness.

By analyzing historical data, the company hopes to identify factors influencing user interactions with advertisements. A better understanding of user behavior patterns will help the company allocate marketing budgets more efficiently and target ads toward prospective customers most likely to be interested in their products or services.

### Goals:
To develop a machine learning classification model capable of accurately predicting target customers, making advertisements more effective and precisely targeted.

#### Objectives:
- Analyze and identify patterns and trends in customer behavior.
- Perform feature selection to identify the most relevant factors in predicting target customers.
- Develop and train a classification model to distinguish between potential customers (those more likely to engage with the ads) and non-potential customers.

---
<br>

## 📂 **Stage 1 : Data Preparation**
### Data Understanding & Assesment

<p align="center">
<img src="https://github.com/user-attachments/assets/99b43baa-3d2b-4136-bb03-e7d543cbae62"
 alt="BivariateAnalysis">
</p>
<br>
  
<br>
<p>
  
##### Dataset Overview
  1. Total Rows: 1000
  2. Total Columns: 11

##### Dataset Understanding
- Unnamed 0: Unique ID for each customer.
- Daily Time Spent on Site: The amount of time users spend on the website daily, measured in minutes.
- Age: Customer age.
- Area Income: The average income in the geographical area where the customer resides.
- Daily Internet Usage: The average time consumers spend using the internet daily, measured in minutes.
- Male: Gender of the customer.
- Timestamp: The specific time when the user clicked on the ad or closed the site window.
- Clicked on Ad: Target variable indicating whether the customer clicked on the ad or not.
- City: City where the customer resides.
- Province: Province where the customer resides.
- Category: The category of the advertisement displayed to the customer.
</p>
<br>


## 📂 **Stage 2 : Exploratory Data Analysis**

<p align="center">
<img src="https://github.com/user-attachments/assets/310f4f50-0c17-448e-8640-aa37dfe0906f"
 alt="BivariateAnalysis">
</p>
<br>

<p>
  
  - The feature Age has a negative correlation with Daily Time Spent on Site, indicating that older customers spend more time on the site compared to younger customers.
  - Age also shows a negative correlation with Daily Internet Usage.
  - Daily Time Spent on Site is positively correlated with Daily Internet Usage.
  - There is a clear separation between two data clusters with almost equal proportions. Less active customers tend to have a higher likelihood of clicking on ads compared to more active customers.
  - Daily Internet Usage and Daily Time Spent on Site are positively correlated with Area Income.
</p>

## 📂 **Stage 3 : Data Preprocessing**
<p>
A. Handling Missing Values in the Data
Missing values were identified in the following features: 
- Area Income and Daily Time Spent on Site have missing values of 1.3%.
- Daily Internet Usage has missing values of 1.1%.
- Male has missing values of 0.3%.
- Since the missing values constitute <4% of the total 1000 rows, the missing values were dropped.

B. Feature Extraction
- AdExposureRatio: This feature represents the ratio of Daily Time Spent on Site to Daily Internet Usage.
- Exposure_category: This feature categorizes the ad exposure ratio into defined groups.
- ExtractDataDate: This feature extracts components from the Timestamp into new columns: 'Year', 'Month', 'Day', 'DayOfWeek', 'Hour', 'Minute', and 'IsWeekend'.

C. Feature Encoding
- One-Hot Encoding: Applied to the features 'Clicked on Ad', 'City', 'Province', and 'Category'.
- Label Encoding: Applied to the feature 'Exposure_category'.

D. Rename Columns
- The column Male was renamed to Gender.

E. Drop Columns
- The columns 'Unnamed:0' and 'Timestamp' were dropped.

Split Data
- The data was split into features (X) and the target variable (Y). All features in X were used to predict the value of Y.
</p>
<br>

## 📂 **Stage 4 : Data Modeling**
<p align="center">
<img src="https://github.com/user-attachments/assets/a1dcbd37-4c00-4444-b5bc-227c6441ae3d"
alt="UserCluster">
</p>
<br>
The algorithm that achieved the "Best Performance" was Random Forest, with a tolerable difference in accuracy between the training and testing data.

## 📂 **Stage 5 : Conclusion and Recommendation**
<p align="center">
<img src="https://github.com/user-attachments/assets/dfa6c101-198c-4ffb-829b-0055550245a1"
alt="UserCluster">
</p>
<br>

Daily Time Spent on Site has a significant influence on the likelihood of users clicking on ads. The longer users spend on the site, the higher their exposure and interaction with ads. Advertisers should focus their efforts on users who are more active on the site.

Daily Internet Usage also significantly impacts the frequency or intensity of an individual's internet usage within a day. It serves as a quantitative measure of how often someone connects to the internet and engages in online activities, regardless of the platform or website visited.

##### Conclusion: Advertisers should target users who spend considerable time on specific sites. Meanwhile, site owners can enhance site appeal (ad relevance, ad design, and user experience) to increase user engagement duration and improve ad click-through rates.
