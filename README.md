

# 🚗 Car Insurance Risk & Defaulters Analysis – Power BI Dashboard

This project showcases a professional-grade **Power BI dashboard** designed to help insurance providers **identify high-risk customers**, monitor **claim trends**, and take **proactive actions** against potential defaulters based on customer behavior and claim history.

---

## 📌 Project Objectives

- Identify **high-risk customers** using data-driven rules
- Visualize customer and vehicle claim behavior
- Classify defaulters based on claim frequency and old claim value
- Deliver **actionable insights** for premium adjustments and fraud detection

---

## 🔍 Risk Criteria & Defaulter Logic

A customer is classified as **High Risk** if:
- They have **CLM_FREQ ≥ 3**, indicating frequent claims
- Or their **OLDCLAIM > $10,000**, indicating costly past claims

These customers are flagged using a custom DAX column:
```DAX
##Risk_Flag = 
IF(
    'Data'[CLM_FREQ] >= 3 || 'Data'[OLDCLAIM] > 10000,
    "High Risk",
    "Low/Medium Risk"
)
##
