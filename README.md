# 💳 Decoding UPI Transactions: Behavioral & Adoption Trends 2024

## 🎯 Project Objective
Why do UPI transactions fail or get flagged as fraud?  
Which *transaction types, banks, devices, or networks* face the highest risks?  
How do fraud patterns vary across *states, user age groups, and merchant categories*?  

This project explores a UPI transaction dataset to uncover patterns in *fraudulent activities, transaction failures, and user behavior, providing **actionable insights* for banks, businesses, and UPI platforms to improve security and customer trust.

---

## 📂 Dataset Information
- *Source:* UPI Transaction Dataset (synthetic & anonymized)  
- *Rows Used:* ~2.5 lakh transactions  
- *Columns:*
  - transaction_id – Unique transaction identifier  
  - sender_bank & receiver_bank – Banks facilitating the transaction  
  - transaction_type – (P2P, Recharge, Merchant Payments, etc.)  
  - category – Merchant category (Grocery, Food, Education, etc.)  
  - amount – Transaction value  
  - device_type – Android, iOS, Web  
  - network_type – 3G, 4G, WiFi  
  - is_fraud – Fraud flag (0/1)  
  - is_failed – Failure flag (0/1)  
  - user_age_group – Age group of user (18–25, 26–35, etc.)  
  - state – Sender’s state  

> Each row represents a UPI transaction with metadata about fraud, failure, and device/bank/network used.

---

## 🛠 Analysis Steps
1. *Data Cleaning*
   - Removed duplicates & missing values  
   - Standardized bank names, device types, and categories  

2. *Exploratory Data Analysis (EDA)*
   - Fraud & transaction failure trends by:
     - Transaction type  
     - Category  
     - Age group  
     - State & Bank  
     - UPI Apps, Devices, and Networks  

3. *Statistical & Correlation Analysis*
   - Boxplots for fraud vs non-fraud amount distributions  
   - Correlation heatmap between fraud flag, amount, time, and weekend  

4. *Business Insights & Recommendations*
   - Actionable strategies for fraud prevention and improving transaction success  

---

## 📊 Analysis & Key Visualizations
### 1. Transaction Type Insights
- *Highest fraud count:* P2P transactions  
- *Lowest fraud count:* Recharge  
- *Fraud rate %:* Highest in Recharges, lowest in P2P  

### 2. Merchant Categories
- *Most transactions:* Grocery & Food  
- *Least transactions:* Education  
- *Highest frauds:* Grocery & Food  
- *Lowest frauds:* Education  

### 3. User Demographics
- *26–35 age group* faces the highest fraud risk  
- Older users experience the *least fraud cases*  

### 4. State & Bank Analysis
- *Maharashtra & Karnataka* report the highest frauds (sender side)  
- *SBI* dominates fraud counts across both sender & receiver banks  

### 5. UPI Apps & Device/Network
- *Paytm* leads in fraud counts among UPI apps  
- *Android devices* face most frauds & failures; *Web* the least  
- *4G networks* show highest frauds & failures; *3G* the lowest  

### 6. Transaction Amount Patterns
- Fraud transactions cluster mostly *below ₹5000, with median **₹618* & mode *₹162*  
- Non-fraud outliers mostly fall between *₹2000–₹30,000*  

### 7. Correlation Analysis
- *Fraud ↔ Amount:* Positive correlation (higher amounts = higher fraud risk)  
- *Hour of Day ↔ Amount:* Negative correlation (small transactions at odd hours)  
- *Fraud ↔ Weekends:* Positive correlation (frauds spike on weekends)  

---

## 🔑 Insights & Key Findings
- *P2P transactions* dominate fraud count, while *Recharges* have the highest fraud rate %.  
- *Grocery & Food* transactions are most vulnerable to fraud.  
- *Young adults (26–35)* are the most targeted age group.  
- *SBI* records the largest share of fraud across banks.  
- *Paytm users* are most exposed to fraud attempts.  
- *Android + 4G users* face the greatest risk of both fraud and transaction failure.  
- Fraudulent transactions are mostly *low to mid-value (< ₹5000)*.  

---

## 💡 Business Recommendations
- *P2P Fraud Spike:* Strengthen identity checks & anomaly detection for P2P transfers.  
- *Recharge Fraud Rate:* Why are recharges most risky? Enforce stricter validation & OTP checks.  
- *Bank-Level Risks:* SBI should invest in advanced fraud detection & customer awareness.  
- *UPI App Security:* Paytm should implement stronger transaction monitoring.  
- *Device/Network:* Android + 4G users need additional safeguards; web flows should be optimized for security.  
- *Age-Based Awareness:* Launch fraud awareness campaigns for 26–35 age group.  
- *Low-Value Frauds:* Small-ticket transactions need equal monitoring to prevent large cumulative losses.  

---

## 📌 Conclusion
This project analyzes *2.5 lakh UPI transactions* to uncover hidden fraud patterns and transaction failures.  
By combining *transaction type, category, device, and bank-level analysis*, we identify critical vulnerabilities in India’s UPI ecosystem.  
These insights empower businesses, banks, and UPI platforms to *strengthen fraud detection, enhance user trust, and secure the future of digital payments*.
