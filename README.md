# 🛒 Pakistan E-Commerce Customer Segmentation

A data science project focused on **customer segmentation using RFM analysis and K-Means clustering** on Pakistan’s Largest E-Commerce Dataset.

The goal of this project is to identify meaningful customer groups based on purchasing behavior so that businesses can better understand high-value customers, frequent buyers, and inactive customers.

---

## 📌 Project Overview

E-commerce businesses generate large amounts of transactional data, but raw transactions alone do not directly explain customer behavior.

This project transforms customer transaction history into meaningful behavioral features using **RFM analysis**:

- **Recency** — How recently a customer made a purchase
- **Frequency** — How often a customer made purchases
- **Monetary** — How much a customer spent

These features are then standardized and clustered using **K-Means** to identify customer segments.

---

## 🎯 Objective

The main objective of this project is to group customers based on their historical purchase behavior.

Customer segmentation can help businesses with:

- Personalized marketing
- Customer retention strategies
- Loyalty programs
- Inventory planning
- Revenue optimization
- Churn reduction
- Customer relationship management

---

## 📊 Dataset

This project uses **Pakistan’s Largest E-Commerce Dataset** from Kaggle.

The dataset contains transaction records from **2016 to 2018** and includes more than half a million entries related to:

- Product categories
- Order status
- Customer IDs
- Pricing
- Transaction dates
- Payment information
- Order totals

The dataset is not included in this repository.

Users should download it separately from Kaggle and update the dataset path inside the notebook before running the project.

---

## 🧹 Data Cleaning & Preprocessing

The dataset required several preprocessing steps before clustering.

The main cleaning steps included:

- Removing empty or invalid records
- Handling missing values
- Correcting data types
- Converting timestamps into datetime format
- Converting price-related columns into numerical form
- Filtering completed orders
- Handling skewed transaction values
- Applying log transformation
- Standardizing the final RFM features

---

## 🧩 Feature Engineering

Three main customer-level features were created:

### Recency

Measures the number of days since the customer’s most recent purchase.

A lower Recency value usually represents a more recently active customer.

---

### Frequency

Measures how many purchases or completed orders a customer has made.

Customers with higher Frequency values are generally more active.

---

### Monetary

Measures the total amount of money spent by each customer.

Customers with higher Monetary values contribute more revenue to the business.

---

## ⚙️ Feature Scaling

The engineered RFM features were standardized using **StandardScaler**.

Scaling was necessary because K-Means is a distance-based clustering algorithm.

Without scaling, features with larger numerical values could dominate the clustering process.

---

## 🤖 Machine Learning Model

This project uses **K-Means Clustering**, an unsupervised machine learning algorithm.

K-Means was selected because:

- The dataset does not contain predefined customer segment labels
- It can identify hidden groups within customer behavior
- It is computationally efficient for large datasets
- It is commonly used for customer segmentation

---

## 📉 Elbow Method

The **Elbow Method** was used to determine a suitable number of clusters.

The Within-Cluster Sum of Squares was calculated for different values of K.

The curve showed a strong reduction in clustering error during the early values of K, and the project selected:

**K = 3**

as the final number of customer segments.

The Elbow Method visualization is available in:

**figures/elbow_method.png**

---

## 📈 Model Evaluation

Because this is an **unsupervised learning** problem, a traditional train-test split was not used.

Instead, cluster quality was evaluated using the **Silhouette Score**.

The model achieved:

**Silhouette Score: 0.36**

This indicates that the clusters show a reasonable level of separation while still containing some overlap between customer groups.

---

## 👥 Customer Segments

The K-Means model identified three main behavioral groups.

### 🟢 High-Value / Loyal Customers

These customers typically show:

- High spending
- Strong purchasing activity
- High business value

These customers are important revenue drivers and should be prioritized for retention and loyalty programs.

---

### 🟡 Potential / Frequent Small Buyers

These customers make purchases relatively frequently but may have lower overall spending compared with high-value customers.

Possible strategies include:

- Product recommendations
- Bundle offers
- Cross-selling
- Upselling
- Personalized promotions

---

### 🟣 At-Risk / Inactive Customers

These customers show lower recent activity and may have stopped purchasing.

They may benefit from:

- Re-engagement campaigns
- Discount offers
- Reminder emails
- Personalized promotions
- Retention strategies

---

## 📊 Customer Segment Visualization

The final customer segments are visualized using **Frequency vs Monetary Value**.

The visualization helps show how different customer groups behave based on purchasing activity and total spending.

The plot is available in:

**figures/customer_segments.png**

Because Monetary values have a wide range, a logarithmic scale is used to make the customer distribution easier to interpret.

---

## 💼 Business Interpretation

The customer segments provide several useful business insights.

### High-Value Customers

High-value customers represent an important source of revenue.

Recommended strategy:

- Loyalty rewards
- Premium offers
- Personalized recommendations
- Early access to promotions

---

### Operational Improvement

Customer segmentation can help businesses better understand which customers and purchasing patterns contribute most to overall activity.

This information can support:

- Inventory planning
- Product prioritization
- Marketing strategy
- Customer retention

---

### Revenue Efficiency

Targeted marketing can be more effective than sending the same promotion to every customer.

Different segments can receive different strategies based on their behavior.

For example:

- Loyal customers → loyalty rewards
- Potential customers → upselling campaigns
- At-risk customers → re-engagement offers

---

## 📁 Repository Structure

Pakistan-Ecommerce-Customer-Segmentation/

├── notebook/

│   └── customer_segmentation_rfm_kmeans.ipynb

│

├── report/

│   └── Customer_Segmentation_Report.pdf

│

├── figures/

│   ├── elbow_method.png

│   └── customer_segments.png

│

├── requirements.txt

├── .gitignore

└── README.md

---

## 📓 Notebook

The main implementation is available in:

**notebook/customer_segmentation_rfm_kmeans.ipynb**

The notebook contains the complete workflow including:

- Data loading
- Dataset inspection
- Data cleaning
- Missing value handling
- Data type correction
- Filtering completed orders
- RFM feature engineering
- Log transformation
- Feature scaling
- Elbow Method
- K-Means clustering
- Cluster evaluation
- Customer visualization
- Business interpretation

The notebook was originally developed and executed using **Kaggle**.

---

## 📄 Research Report

The complete project report is available in:

**report/Customer_Segmentation_Report.pdf**

The report covers:

- Dataset overview
- Problem statement
- Business relevance
- Data understanding
- Data cleaning
- Feature engineering
- Predictive modeling
- Hyperparameter selection
- Model evaluation
- Customer segment interpretation
- Business recommendations
- Deployment considerations
- Ethical considerations
- Limitations
- Future improvements

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook
- Kaggle
- K-Means Clustering
- StandardScaler
- RFM Analysis

---

## 📦 Requirements

The main Python libraries used in this project include:

- pandas
- numpy
- matplotlib
- scikit-learn
- jupyter

Install the required libraries using:

**pip install -r requirements.txt**

---

## ▶️ How to Run

1. Clone this repository.
2. Download Pakistan’s Largest E-Commerce Dataset from Kaggle.
3. Place the dataset in your preferred local directory.
4. Update the dataset path inside the notebook.
5. Install the required Python libraries.
6. Open the Jupyter Notebook.
7. Run the notebook cells sequentially.

---

## 🏗️ Deployment Considerations

The customer segmentation model can potentially be used as part of a batch-processing pipeline.

For example, customer segments could be recalculated periodically and stored in a database.

A possible production workflow could include:

- Cloud storage for transactional data
- Python-based preprocessing pipeline
- Scheduled customer segmentation
- SQL database for storing cluster labels
- Marketing or CRM integration

---

## ⚖️ Ethical Considerations

Customer segmentation should be used responsibly.

Businesses should avoid using customer groups in ways that could result in:

- Unfair price discrimination
- Bias against customer groups
- Privacy violations
- Misuse of customer behavioral data

Segmentation should support better customer experiences rather than unfair treatment.

---

## ⚠️ Limitations

The current project has several limitations:

- Demographic information is not included
- Customer age and location are unavailable
- K-Means assumes relatively simple cluster structures
- Some customer behaviors may overlap between clusters
- The Silhouette Score indicates moderate rather than perfect separation
- The current analysis focuses primarily on transaction behavior

---

## 🚀 Future Improvements

Possible future improvements include:

- Adding demographic information
- Including customer location
- Comparing K-Means with DBSCAN
- Comparing K-Means with hierarchical clustering
- Testing Gaussian Mixture Models
- Performing deeper customer lifetime value analysis
- Building an interactive customer segmentation dashboard
- Automating periodic customer segmentation
- Integrating the model with a CRM system
- Creating personalized recommendation strategies for each segment

---

## 👩‍💻 Author

**Fatima Sohail**

BS Data Science  
GIFT University

---

## 🎓 Academic Context

This project was developed as part of the **Data Science Applications** course.

The objective was to apply a complete data science workflow to a real-world e-commerce dataset, including data preprocessing, feature engineering, unsupervised machine learning, model evaluation, and business interpretation.

---

## ⭐ Support

If you find this customer segmentation project useful for learning data science, clustering, or RFM analysis, consider giving the repository a ⭐.
