# 💳 Decoding UPI Transactions: Behavioral & Adoption Trends 2024

## 🎯 Project Objective
This project conducts an in-depth analysis of 2.5 lakh UPI transactions from 2024 to uncover user behaviour patterns, transaction dynamics (P2P vs P2M), peak usage periods, and bank-wise adoption trends. which factors influence users to complete or abandon transactions? Why do certain banks or user segments exhibit higher engagement?
By exploring these questions, actionable insights are drived to help digital payment platforms enhance user experience, optimize transaction completion, and drive greater adoption across diverse user segments.

---

## 📂 Dataset Information
- *Source:* Kaggle / Public Dataset- UPI Transactions 2024 Dataset
- *Dataset Link:* https://www.kaggle.com/datasets/skullagos5246/upi-transactions-2024-dataset
- *Rows used:* ~250,000 transactions  
- *Key columns:* transaction_id , timestamp , transaction_type, merchant_category, amount(INR), transaction_status, fraud_flag, sender_age_group, receiver_age_group, sender_state, sender_bank, receiver_bank, device_type, network_type, upi_app

  
> Note: dataset was cleaned (stripped, standardized, timestamp parsed), categorical orders fixed for plotting, and synthetic upi_app column added for richer analysis.

---

## 🛠 Analysis Steps
1. *Data cleaning & preprocessing*
   - Strip whitespace, standardize categories, convert datatypes.
   - Handle / drop invalid timestamps (where needed) and save cleaned CSV.
   - Map age groups into ordered categorical for plots.

2. *Exploratory Data Analysis (EDA)*
   - Transaction success vs failure counts & percentages.
   - Fraud distribution across: transaction type, merchant category, amount, time (hour/day/weekend), state, bank, app, device, network.
   - Boxplots & binned analysis for amounts (median & mode).
   - Crosstabs / groupby summaries and heatmaps for combined risk views.

3. *Focused risk analysis*
   - Fraud rate (%) per group (not just counts) to surface per-transaction risk.
   - Zoomed counts/limits where fraud is rare (so fraud bars remain visible).
   - Save key summary tables (fraud rates by bank, state, age group) to CSV for reporting.

---

## 📊 Analysis & Key Visualizations (select highlights)

### 1. Transaction Success vs Failure (counts & %)
- *95% success, 5% failed* (visualized as count plot + % stacked view).  
- Insight: System largely reliable; failures concentrated in certain devices/networks.

### 2. Fraud Prevalence
- *Fraudulent transactions ≈ 0.2%* of total — highly imbalanced.  
- Insight: Detection is a rare-event problem; models must handle class imbalance.

### 3. Fraud vs Transaction Outcome
- *Most fraudulent transactions (~450+) were processed as successful*; only a few failed.  
- Insight: Many frauds slip past approval — prevention must act pre-authorization.

### 4. Time-based patterns
- *Most transactions* happen between *15:00–24:00*.  
- *Fraud rate peaks at ~4:00 AM* (early-morning spike) and shows a big count spike around *20:00 (8 PM)*; fraud remains high in afternoons/evenings.  
- Insight: Fraudsters exploit both off-peak low-vigilance hours and evening high-volume windows.

### 5. Day / Weekend
- Fraud counts are fairly even across weekdays, but *weekend fraud rate per day is higher* (i.e., fewer transactions overall, but proportionally more fraud).  
- Insight: Weekends are disproportionately riskier per transaction.

### 6. Transaction Type
- *P2P has the highest fraud count* (most cases).  
- *Recharge shows the highest fraud rate (%)* despite low counts.  
- Insight: Different defenses needed — P2P for volume-based monitoring, Recharge for stricter per-txn checks.

### 7. Merchant Category & Amount
- *Grocery & Food* show highest transaction volumes and highest fraud counts; *Education* the lowest.  
- *Median fraud amount = ₹618, **mode ≈ ₹162*.  
- *Most frauds in ₹0–₹500 range (~200 cases); majority of frauds < ₹5,000.*  
- Insight: Fraudsters prefer low-to-mid amounts; small-ticket frauds add up.

### 8. Demographics & Geography
- *26–35 age group* shows the highest fraud counts; older groups have significantly fewer incidents.  
- *Maharashtra & Karnataka* lead in fraud counts (sender-side).  
- Insight: Targeted awareness & monitoring for active younger cohorts and high-activity states.

### 9. Banks, Apps, Devices & Networks
- *SBI* registers the highest fraud counts (both sender & receiver).  
- *Paytm* shows the highest fraud count among apps.  
- *Android devices* have the most frauds and failures; *Web* the least.  
- *4G networks* see more fraud & failures than 3G (likely reflects volume).  
- Insight: Platform-, bank-, and device-focused controls will be more effective than one-size-fits-all.

### 10. Correlations (numeric)
- Positive correlation: *fraud_flag ↔ amount, **fraud_flag ↔ hour_of_day, **fraud_flag ↔ is_weekend*.  
- Negative correlation: *hour_of_day ↔ amount, **is_weekend ↔ amount*.  
- Insight: Fraud is linked to specific hours/weekend behavior and amount dynamics; combine time and amount signals for risk scoring.

---

## 🔑 Key Findings
- Fraud is rare (≈0.2%) but concentrated: *P2P (by count), Recharge (by rate%), Grocery/Food (by count)*.  
- *26–35* most targeted; *Maharashtra/Karnataka* hotspots.  
- *SBI* & *Paytm* prominently present in fraud counts.  
- *Android + 4G* show higher failures & fraud counts.  
- Fraud mostly in *low–mid amounts (< ₹5,000)* (median ₹618, mode ₹162).

---

## 💡 Business Recommendations 
*P2P is the highest in fraud count. What next?*  
- Add velocity checks for repetitive transfers, flag repeated small transfers to new payees, and apply lightweight friction (e.g., contextual OTP) for suspicious flows.

*Recharge shows highest fraud rate% — how to secure it?*  
- Enforce OTP revalidation for rapid recharges and apply micro-transaction anomaly detection (velocity + device risk).

*26–35 age group is most targeted — should we act?*  
- Yes. Roll out targeted awareness nudges, in-app security tips, and optional stricter controls for newly added beneficiaries among this cohort.

*Maharashtra & Karnataka are hotspots — what can banks do?*  
- Deploy region-specific monitoring thresholds and local awareness campaigns; coordinate with regional risk teams.

*SBI and Paytm show high counts — how should stakeholders collaborate?*  
- Banks and apps should share anonymized signals (volume spikes, devicetypes, IP ranges) to block cross-platform fraud patterns.

*Android + 4G show more failures & frauds — what to implement?*  
- Improve app hardening, in-app device integrity checks, and encourage timely app/OS updates.

*Most frauds are < ₹5,000 — why monitor small transactions?*  
- Because many small frauds accumulate losses. Apply behavioral analytics even for micro-transactions.

*Time windows show peaks (late nights, evenings). What countermeasures help?*  
- Introduce time-aware risk multipliers and more aggressive real-time scoring during high-risk hours and weekends.

---

## 📌 Conclusion
This analysis of ~250k UPI transactions surfaces *where fraud hides and who it targets*: younger, active users, P2P flows, grocery/food merchants, Android + 4G users, and specific states/banks/apps. Though fraud is a tiny fraction (~0.2%), its patterns are consistent — enabling focused defenses that preserve user convenience while dramatically reducing risk.

---
