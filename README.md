# 💳 Decoding UPI Transactions: Behavioral & Adoption Trends 2024

## 🔹 Project Objective
UPI (Unified Payments Interface) has transformed digital transactions in India, but with growth comes challenges: rising frauds, risky transaction types, and vulnerable time patterns.  

This project explores *UPI transaction data (2020–2025)* to analyze fraud distribution across payment types, transaction amounts, timings, and geographies. The goal is to uncover fraud-prone patterns and provide *business recommendations* for banks, fintechs, and regulators to strengthen digital trust.

---

## 🔹 Dataset
- Source: Public UPI dataset (synthetic + real-world inspired patterns)  
- Rows: ~5,00,000 transactions  
- Columns:  
  - transaction_id – Unique transaction ID  
  - user_id – User identifier  
  - amount – Transaction value  
  - txn_type – P2P, P2M, AutoPay, QR Code, etc.  
  - is_fraud – Fraud flag (1/0)  
  - timestamp – Date & time of transaction  
  - location – Region/City  
- Description: Each row represents one UPI transaction with fraud detection status.

---

## 🔹 Analysis Steps
1. *Data Cleaning & Preprocessing*
   - Removed duplicates, invalid timestamps, and negative amounts  
   - Derived new columns (hour, day, month, is_weekend)  
   - Standardized txn types  

2. *Exploratory Data Analysis (EDA)*
   - Distribution of fraud vs genuine transactions  
   - Fraud patterns by *amount, **transaction type, **time, and **location*  

3. *Fraud Trend & Risk Analysis*
   - Month & hour-wise fraud patterns  
   - Txn type vs fraud ratio  
   - High-value fraud detection  

4. *Business Insights*
   - Fraud hotspots in time & geography  
   - Which txn types are riskiest?  
   - What actions can businesses & regulators take?  

---

## 🔹 Analysis & Key Visualizations  

### 📌 Fraud Distribution Across Transaction Types  
<img src="images/Fraud_by_TxnType.png" alt="Fraud by Transaction Type" width="600"/>  

Frauds are *highest in P2P transfers*, followed by QR-code transactions. P2M (merchant payments) and AutoPay remain relatively safer.  
👉 This reveals that direct peer-to-peer transfers carry the most risk, likely due to social engineering and scam-driven requests.  

---

### 📌 Fraud by Transaction Amount  
<img src="images/Fraud_by_Amount.png" alt="Fraud by Amount" width="600"/>  

Most frauds happen in the *₹500–₹2000 range, but the **loss impact is highest in high-value (>₹10,000) frauds*.  
👉 Fraudsters exploit mid-value transactions to stay unnoticed while still maximizing gain. Banks need tighter velocity checks in this slab.  

---

### 📌 Time-of-Day Fraud Patterns  
<img src="images/Fraud_by_Hour.png" alt="Fraud by Hour" width="600"/>  

Frauds peak between *11 PM – 3 AM*, when user alertness and bank monitoring are relatively weaker.  
👉 This highlights the need for AI-based real-time alerts and stricter night-time transaction monitoring.  

---

### 📌 Month-wise Fraud Trends  
<img src="images/Fraud_by_Month.png" alt="Fraud by Month" width="600"/>  

Fraud counts grew sharply post-2022, aligning with UPI adoption boom. Seasonal spikes around *festive seasons* (Diwali, New Year) show fraudsters exploiting higher transaction volumes.  
👉 Awareness campaigns must peak during festive seasons when users are most vulnerable.  

---

### 📌 Location-wise Fraud Hotspots  
<img src="images/Fraud_by_Location.png" alt="Fraud by Location" width="600"/>  

Metro cities dominate in fraud counts (due to higher volume), but *fraud rate per 1000 transactions* is *higher in Tier-2 & Tier-3 cities*.  
👉 This suggests awareness gaps in smaller towns where users are newer to UPI.  

---

## 🔹 Insights & Key Findings  
- *P2P transactions* = highest fraud risk.  
- *Mid-value slabs (₹500–₹2000)* are fraud hotspots, while *high-value frauds cause maximum loss per event*.  
- *Night-time transactions* (11 PM – 3 AM) see disproportionate fraud spikes.  
- *Tier-2/3 cities* have higher fraud rate per 1000 txn despite lower volumes.  
- *Festive seasons* bring seasonal fraud surges.  

---

## 🔹 Future Outlook / Business Impact  

Questions & Learnings:  

1. *Why are P2P transactions most vulnerable?*  
   → Because they lack merchant safeguards. Users often approve fraudulent “request money” pulls.  
   Recommendation: Stronger consent + two-step approvals for unknown contacts.  

2. *Why do fraudsters prefer ₹500–₹2000 transactions?*  
   → Small enough to avoid red flags, large enough to profit.  
   Recommendation: Implement *dynamic velocity limits* (flag multiple mid-value transfers).  

3. *Why do frauds spike late at night?*  
   → Lower user vigilance + weaker monitoring.  
   Recommendation: Real-time AI fraud scoring + night-time risk multipliers.  

4. *Are rural users equally at risk?*  
   → Yes, but in different ways. Tier-2/3 see higher fraud rates due to lack of awareness.  
   Recommendation: Awareness campaigns in regional languages + in-app fraud alerts.  

5. *How can businesses stop seasonal fraud surges?*  
   → By launching *“Festive Fraud Watch” campaigns* before high-volume periods.  
   Recommendation: Push notifications + dynamic fraud models tuned to seasonal spikes.  

---

## 🔹 Final Note  
This project doesn’t just analyze fraud—it helps businesses, banks, and regulators understand *where fraud hides, when it strikes hardest, and who is most at risk*.  
By turning data into *strategic defense insights, it builds the foundation for a **safer, more trusted UPI ecosystem*.
