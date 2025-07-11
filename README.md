# Starbucks-Customer-Segmentation
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

### 7. Result and key vizualizations 
Once the model was trained, I analyzed the clusters using visualizations like bar charts,scatter plot and pair plots to understand the differences in behavior, spending, and responsiveness across segments.

Below are some visualizations and insights from my analysis: 

<img width="630" height="470" alt="download" src="https://github.com/user-attachments/assets/7c97ca06-4678-46e2-8561-2a3acfc8e088" />

<img width="2990" height="495" alt="download" src="https://github.com/user-attachments/assets/873bb746-401d-4218-965c-d345b30f2817" />

<img width="2990" height="495" alt="download" src="https://github.com/user-attachments/assets/0f7d4835-b785-4510-9c65-8818ee8e7c1f" />

<img width="2990" height="495" alt="download" src="https://github.com/user-attachments/assets/2f8b7faa-e20b-41ce-a28d-1a6f9f42d84c" />

<img width="914" height="490" alt="download" src="https://github.com/user-attachments/assets/b7fed7e3-9e13-47c3-9280-a20347f4f781" />


### 8. Interpretation from the cluster

Finlly i interpreted the resulting customer segments according to their behaviour as follows:

<img width="575" height="470" alt="download" src="https://github.com/user-attachments/assets/10454249-ce54-42a0-9bc9-79221e8d7ad1" />

### Customer Demographics:

<img width="580" height="453" alt="download" src="https://github.com/user-attachments/assets/301e2d84-bf05-4687-89ec-ad8c18666da4" />

<img width="571" height="453" alt="download" src="https://github.com/user-attachments/assets/1e822bde-9902-4180-b29c-54204fbb2949" />

<img width="580" height="453" alt="download" src="https://github.com/user-attachments/assets/9fe3d5a5-3d30-468e-b0a7-705397c8df9e" />

<img width="636" height="468" alt="download" src="https://github.com/user-attachments/assets/ce7d31ea-22a9-4c47-81b4-f51ffdae69e5" />

<img width="636" height="468" alt="download" src="https://github.com/user-attachments/assets/a5b0aa3f-36f5-49eb-b335-a4f9b25c719b" />

<img width="1114" height="986" alt="download" src="https://github.com/user-attachments/assets/4164e3da-c682-4da1-885a-afee33eeaebc" />

- Most Valuable Customers (MVC) – Cluster 4 - High-spending users with excellent engagement and completion rates.
- Regular Customers – Cluster 2 - Consistent, moderate spenders who engage steadily.
- High Potential Customers – Cluster 0 - Users with strong responsiveness.
- Offer Viewers Customers – Cluster 1 - Customers who frequently view promotions but seldom complete them.
- Low Engagers Customers – Cluster 3 - Users with minimal interaction.



