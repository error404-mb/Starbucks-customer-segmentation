# Starbucks-customer-segmentation
# Business Understanding :
Starbucks Corporation is a global coffee company with over 30,000 stores across 80+ countries. To build customer loyalty, it offers a Starbucks Rewards Program, where members receive promotional offers through various channels. However, customer responses to these offers vary significantly, leading to missed engagement opportunities and inefficient marketing. Understanding customer behavior is key to delivering relevant promotions and improving customer retention.

# Project Overview :
The motivation behind this project is to propose a solution that helps the company in forming a better understanding of its customers base. In this project, an unsupervised learning technique will be used to segment customers and measure how each segment behave during different periods of the test. In particular, K-Means clustering will be used. The provided dataset of courses will go through different phases at first before being ready for modeling. Starting with cleaning and ending with the final dataset grouped by customer profiles with their data aggreated.

Here's a high-level overview of the workflow followed in this project:

- Define the problem in-hands and measurement criterias.
- Explore, understand, and clean the provided datasets.
- Prepare final dataset grouped by customers.
- Transform final dataset appropriately before fitting model.
- Fit model on final dataset and predict cluster labels.
- Explore distributions among formed clusters.
- Discuss outcomes and make recommendations.

# Dataset :
This data set contains simulated data that mimics customer behavior on the Starbucks Rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink (informational) or an actual offer such as a discount or BOGO (buy one get one free). This data set is a simplified version of the real Starbucks app because the underlying simulator only has one product whereas Starbucks actually sells dozens of products.

The data is contained in three files mentioned below in brief and will be discussed in details later.

- PORTFOLIO DATASET- containing meta data about the promotions offered by the company.
- PROFILE DATASET- demographic data about members enrolled in the reward program.
- TRANSCRIPT DATASET- records for transactions, offers received, offers viewed, and offers completed.

# Project Workflow:
### 1. Data Understanding
Firstly, I explored the three datasets to understand their structure features, and how they connect with each other — especially how user behavior can be tracked across events and offer types.

### 2. Data Cleaning
Then, I cleaned the dataset by removing null values from the 'gender' and 'income' columns, filtered out invalid entries (like age = 118), and dropped customers with no meaningful activity. I also corrected inconsistent data types and renamed several columns for better clarity and understanding during analysis.

### 3. Exploratory Data Analysis (EDA)
I then performed EDA on the all DataFrames individually to gain a comprehensive understanding of the data. Univariate analysis was performed on each DataFrame, summarizing the statistics of all variables related to offers, customers, and events. Bivariate analysis was applied to the customer demographic data to explore the relationships between age, gender, and income.

### 4. Data Preprocessing
After that, I merged all three datasets into one customer-level view and created several new features, such as:

- Total offers received, viewed, and completed.
- Total amount spent according to tranactions.
- find out offer view and completion rate.
I also encoded categorical variables and scaled the data to make it ready for clustering.

### 5. Customer Segmentation
Then, I segmented customers based on their behavior during the campaign month. I extracted key features for each customer, including the number of offers received, viewed, and completed, as well as the number of transactions made and the total amount spent. Using these metrics, I grouped customers into meaningful segments to better understand engagement levels and spending patterns.

### 6. Model Training
I applied K-Means Clustering to segment customers based on demographic and behavioral features. To determine the ideal cluster count, I used both the Elbow Method and Silhouette Score. After selecting the optimal number of clusters, I trained the model and labeled each customer accordingly for further analysis.

### Elbow Method :
<img width="589" height="453" alt="download" src="https://github.com/user-attachments/assets/9e87a486-a58a-4c29-aa0e-cf2a8b41b565" />

### Silhouette Method
<img width="576" height="453" alt="download" src="https://github.com/user-attachments/assets/c7edd2c1-6548-487f-88c4-e8e91bb6f2be" />



