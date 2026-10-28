# Telecom Customer Churn Analysis

An interactive dashboard that shows where customer churn comes from in a telecom company, built from SQL analysis of the public Kaggle Telco Customer Churn dataset.

**Live dashboard:** https://vdntswnt.github.io/telco-churn-dashboard/

![Dashboard overview](images/dashboard-full.png)

## Business question

Which customers leave, and what could the company do about it? The dashboard answers this with filters for contract, internet type and customer type, so churn can be checked inside any group.

## Key findings

| Finding | Result |
|---|---|
| Overall churn rate | **26.5%** (1,869 of 7,043 customers) |
| Contract length | Month-to-month **42.7%**, one-year 11.3%, two-year **2.8%**. Month-to-month is 55% of customers but 88.6% of all churn |
| Riskiest group | Fiber optic, month-to-month, paying by electronic check: **60.4%** churn (1,307 customers) |
| Tenure | First 11 months: **48.3%** churn. After 48 months: 9.6% |
| Tech support | Internet customers without it churn at 41.6%, with it at 15.2% |
| Gender | No real difference (26.9% female, 26.2% male) |

## Recommended actions

1. Offer a discount or free add-on to move month-to-month customers onto a 12-month plan, starting with first-year customers.
2. Review fiber pricing and service quality, and run a retention call for the riskiest group before month 6.
3. Add onboarding check-ins at months 2, 4 and 8.
4. Trial free tech support for at-risk fiber customers against a control group. The gap shows association, so the trial is what proves cause.

## Method

- Raw CSV loaded into **SQLite** and cleaned with **SQL**. 11 blank `TotalCharges` values belong to customers with zero tenure and were set to 0.
- Validation checks: 7,043 unique customer IDs, no non-positive charges, no add-ons recorded for customers without internet.
- Churn rates were calculated by contract, internet service, payment method, tenure band, tech support and household, and the highest-risk segments (at least 100 customers) were ranked.
- The results were turned into a filterable single-page dashboard in plain HTML, CSS and JavaScript.

## Data

Kaggle Telco Customer Churn (IBM sample data), with two ticket-count columns. This is a public teaching dataset, so the figures describe a sample company. Differences between groups show association, not proven cause.

## Repository contents

```
index.html     the interactive dashboard (open in any browser)
images/        screenshots used in this README
sql/           SQL queries used for cleaning, validation and analysis
```

## Tools

SQL, SQLite, HTML, CSS, JavaScript

## Author

Vedant Sawant — [LinkedIn](https://www.linkedin.com/in/vdnt-swnt/) · [GitHub](https://github.com/vdntswnt)
