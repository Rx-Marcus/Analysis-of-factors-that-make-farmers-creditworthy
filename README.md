# Analysis-of-factors-that-make-farmers-creditworthy

## Table of Content
- [Project Overview](#project-overview)
- [Business Objectives](#business-objectives)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Data Analysis](#data-analysis)
- [Key Insights](#key-insights)
- [Recommendations](#recommendations)

### Project Overview 📽️
---

Agriculture remains vital to Nigeria’s economy but continues to face challenges that limit youth participation and productivity. Among these, limited access to affordable finance stands out as a major constraint for young Nigerians aspiring to enter or expand in the agricultural sector.
This project investigates the key factors shaping the creditworthiness of young agripreneurs in Nigeria. Through data analysis and visualization in Power BI, it explores how education, financial literacy, asset ownership, and banking access influence credit eligibility. The findings reveal regional and demographic trends that can inform policies and financial strategies aimed at enhancing credit access and promoting youth financial inclusion in agriculture.

<img width="982" height="562" alt="Screenshot 2025-10-17 190125" src="https://github.com/user-attachments/assets/3b4d4b52-6b59-4d38-a769-603c9ab3dfb8" />

![Uploading Screenshot 2025-10-17 190155.png…]()


### Business Objectives
1. Identify factors that make farmers "creditworthy."
2. Predict future repayment behavior or business success.


### Data Source
The dataset used for this project was obtained from [Access to Financial Services](https://www.a2f.ng)

### Tools
- Excel 
- Power Bi

### Data Cleaning and Preparation
The cleaned dataset was first imported into Power Query Editor for additional data manipulation before analysis in Power BI.

- Several categorical variables were standardized for clarity and consistency:

- Gender: ‘1’ replaced with Male; ‘2’ replaced with Female.

- Sector: ‘1’ replaced with Urban; ‘2’ replaced with Rural.

- Educational Level: Numerical values (1–11) recoded into descriptive categories such as Pre-school, Primary Incomplete, Secondary Complete, University/Polytechnic OND, Post-University Complete, Non-formal Education, and No Education.

- Banked: ‘1’ replaced with Yes; ‘2’ replaced with No.

- Investment in Physical Assets: ‘1’ replaced with Yes; ‘2’ replaced with No.

Following these transformations, the prepared dataset was imported into Power BI for further modeling and analysis.

### Data Analysis

Seven (7) DAX measures were created to enhance analysis
- ```Credit worthiness score = IF('Cleaned_Agri cvs'[Paying_borrowed] = 1 && 'Cleaned_Agri cvs'[Debt] <= 2 && 'Cleaned_Agri cvs'[finlit_knowledge] >= 1, "High", "Low")```
- ```Repayment Risk = SWITCH(TRUE(), 'Cleaned_Agri cvs'[Borrowed_in_past] = 1 && 'Cleaned_Agri cvs'[Paying_borrowed] = 1, "Low Risk", 'Cleaned_Agri cvs'[Borrowed_in_past] = 1 && 'Cleaned_Agri cvs'[Paying_borrowed] = 2, "High Risk", "Medium Risk")```
- ```Age Group = IF('Cleaned_Agri cvs'[Age] < 22, "18 - 21", "22 - 25")```
- ```High credit worthy count = CALCULATE(COUNT('Cleaned_Agri cvs'[Credit worthiness score]), 'Cleaned_Agri cvs'[Credit worthiness score] = "High")```
- ```Total credit worthy count = COUNT('Cleaned_Agri cvs'[Credit worthiness score])```
- ```Total Respondence = COUNT('Cleaned_Agri cvs'[Age])```
- ```ID Verification Index = 'Cleaned_Agri cvs'[Voters_card] + 'Cleaned_Agri cvs'[BVN] + 'Cleaned_Agri cvs'[Tax_cert] + 'Cleaned_Agri cvs'[Tax_invoice]```t

### Key Insights
- Of the 1,055 young agripreneurs surveyed, only 155, which is approximately 14.7%, were classified as credit-worthy. This highlights a significant unmet need for financial support and capability building within the cohort.

- States in the North-Central and North-East regions dominate the credit-worthy rankings, suggesting that regional programs may be effective there, while other regions are lagging behind.
- Older young agripreneurs are about 1.5 times more likely to be credit-worthy compared to the younger cohort. This may reflect greater experience, a more substantial asset base, or stronger relationships with lenders.
- Two-thirds of credit-worthy farmers possess physical assets (such as equipment, livestock, and land), indicating that ta ngible collateral is a key factor in accessing credit.
- Agripreneurs with strong financial literacy are significantly more likely to be credit-worthy. Therefore, financial education programs could have a meaningful impact on improving credit access.
- Holding a formal bank account correlates with higher creditworthiness. Credit-worthy farmers are predominantly banked, suggesting that promoting basic account openings could enhance credit outcomes.
- Higher levels of education appear to be a strong indicator of creditworthiness. Tailored training programs targeting secondary-level literacy might be especially effective.
- Geographic clusters in the northern regions, particularly North-Central and North-East, showcase stronger repayment profiles. This trend may be attributed to factors such as agro-climatic advantages, the presence of NGOs, and access to extension services.
- Ownership of assets (such as equipment, livestock, and land) appears to significantly enhance repayment capacity. Therefore, financing products linked to asset acquisition may further reduce repayment risk.
- Moderate borrowing (level 2) is correlated with the strongest repayment capabilities. Both under and over leveraging negatively impact low-risk status. Tailored credit limits may optimize repayment.
- Completing secondary education is the strongest indicator for good repayment behavior for agriprenuers between the age of 18 to 25. Financial training programs at the secondary level could reinforce this.
- Older young agripreneurs tend to repay reliably compared to their younger counterparts, likely due to greater maturity, experience, or asset base.
- The analysis indicates that a greater percentage of low-risk borrowers are female agripreneurs. This suggests that female agripreneurs may be more creditworthy or financially responsible, which could lead to lower default rates among women in agricultural lending. Lenders might want to take this trend into account when developing targeted loan products or risk mitigation strategies.

### Recommendations

1. Prioritize high-repayment regions: Channel more credit to North-Central and North-East states (e.g., Niger, Nasarawa, Adamawa) and assess barriers in lagging states.

2. Promote asset-based lending: Link loans to equipment or livestock financing, as asset ownership reduces repayment risk and builds collateral.

3. Adopt tiered credit limits: Set loan ceilings based on debt capacity (e.g., “debt level 2”) using borrower profiling tools to prevent over-indebtedness.

4. Embed financial education in schools: Integrate credit management and financial literacy into secondary school curricula.

5. Focus on agripreneurs aged 22–25: Provide targeted lending and mentorship; offer training and risk-sharing support to those aged 18–21.

6. Develop gender-inclusive products: Create women-focused loan schemes with reduced rates or group lending models to encourage participation.

7. Expand regional credit programs: Replicate successful North-Central and North-East initiatives in underperforming South-South and South-East regions.

8. Support younger agripreneurs (18–21): Offer mentorship, incubation, and asset-building programs to strengthen credit profiles.

9. Encourage physical asset investment: Provide subsidized or cooperative financing for equipment, livestock, and land to improve loan eligibility.

10. Strengthen financial literacy: Integrate practical modules on budgeting, saving, and credit management into agripreneur programs.

11. Enhance financial inclusion: Partner with banks to simplify account opening and incentivize formal banking among rural youth.

12. Link education with credit access: Tie credit eligibility to educational attainment and entrepreneurship training at the secondary level.

