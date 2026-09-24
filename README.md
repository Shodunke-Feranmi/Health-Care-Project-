# Healthcare Analytics Dashboard
 
A combined Excel + Power BI project analyzing hospital performance across patients, finance, treatment outcomes, doctors, and branches. Four source workbooks were joined and cleaned in Excel, then loaded into Power BI for a 6-page interactive dashboard.
 
---
 
## 📌 Project Overview
 
This project mirrors a real hospital network's data: patient records, financials, treatments, doctor performance, and branch-level results, originally split across **4 separate workbooks** and joined into a single model in Excel before being loaded into Power BI.
 
## 🗂️ Dashboard Pages & Goals
 
### 1. Executive Dashboard
**Goal:** A top-level snapshot for leadership — total revenue, patient volume, satisfaction, and cost, all in one view.
**Visuals:** KPI cards (Total Revenue, Patients, Total Doctors, Total Departments, Avg Patient Satisfaction, Avg Length of Stay, Avg Treatment Cost, Total Diagnosis), a revenue trend line, and a patient breakdown bar chart.
**Findings:**
- **500 patients** generated **$141.31M in revenue**, across **5 departments** and **5 doctors**, with **5 diagnosis types**
- Average treatment cost per patient: **$245.00K** | Average length of stay: **7.46 days** | Average patient satisfaction: **2.98**
- **April and November are the clear peak months** — April: 56 patients / $14.9M revenue; November: 55 patients / $16.2M revenue (the single highest revenue month)
- **February is the weakest month** on both measures — only 30 patients and $8.1M in revenue
### 2. Patient Analysis Dashboard
**Goal:** Understand who the patients actually are — demographics, geography, and which branches see the most volume.
**Visuals:** Patients by state, by hospital branch (area chart), by age group, and by gender (donut). Filterable by Gender.
**Findings:**
- Gender split is nearly even: **253 male (50.6%)**, **247 female (49.4%)**
- **Old patients are the largest age group (156)**, followed by Adult (141), Young Adult (107), and Child (96)
- **Ibadan is the busiest branch (131 patients)**, followed by Lagos (126), Port Harcourt (124), and Abuja (119)
- Patients also break down by **5 states**: FCT (106), Lagos (106), Oyo (101), Rivers (98), and **Kano (89)** — but Kano has no matching hospital branch in the data, meaning every Kano-state patient is traveling to one of the 4 existing branches for care
### 3. Financial Dashboard
**Goal:** Understand where revenue actually comes from — by branch, department, payment method, and insurance status.
**Visuals:** Revenue by branch, by department, by payment method (trend line), and two donut breakdowns (gender × payment method, gender × insurance status). Filterable by Department.
**Findings:**
- **Neurology is the top-revenue department ($33.3M)**, ahead of Orthopedics ($28.3M), Cardiology ($28.2M), Oncology ($28.0M), and Pediatrics ($23.4M)
- **Ibadan generates the most branch revenue ($40M)**, followed by Port Harcourt ($35M), and Lagos and Abuja tied at $33M each
- **Transfer is used by the fewest patients (148, 29.6%) but generates the most revenue ($51.7M)** — an average of about **$349K per transfer transaction**, well above Cash (~$269K) or Insurance (~$241K)
- Revenue is almost evenly split between **Insured ($71.21M, 50.4%)** and **Not Insured ($70.09M, 49.6%)** patients
### 4. Treatment Dashboard
**Goal:** Evaluate clinical outcomes and cost — which diagnoses and treatments are most common, most expensive, and how they relate to satisfaction and readmission.
**Visuals:** Patient satisfaction trend, diagnosis volume, treatment cost by type, satisfaction by department, treatment type by patient count, and a readmission/insurance/gender breakdown.
**Findings:**
- **Migraine is the most common diagnosis (111 cases)**, followed by Fracture (107), Cancer (103), Hypertension (103), and Malaria (76)
- **Surgery is both the most performed treatment (135 patients) and the costliest overall ($33.7M)**, followed by Medication (125 patients, $31.0M), Consultation (121 patients, $27.8M), and Therapy (119 patients, $30.0M)
- **Neurology has the highest satisfaction score (324)**; **Oncology has the lowest (276)**, despite Oncology bringing in solid revenue ($28.0M) — a quality gap worth investigating
- **52.8% of patients (264 of 500) were readmitted** — a notably high readmission rate
### 5. Doctor Performance Dashboard
**Goal:** Identify which doctors drive the most patient volume, revenue, and satisfaction — and whether those three things line up.
**Visuals:** Total Doctors KPI, patient satisfaction by doctor, patients seen by doctor, revenue by doctor (trend), and treatment cost by doctor (area chart).
**Findings:**
- **Dr. Ade generates the most revenue ($32.7M)** and sees the second-most patients (111), but has the **lowest patient satisfaction of all 5 doctors (2.76)**
- **Dr. Grace has the highest patient satisfaction (3.26)** but the **fewest patients (82) and lowest revenue ($20.7M)** of the group
- Patient volume by doctor: Dr. Musa (113), Dr. Ade (111), Dr. Bello (98), Dr. Okafor (96), Dr. Grace (82)
- Treatment cost follows the same ranking as revenue: Dr. Ade ($28.1M) and Dr. Musa (~$27.9M) are highest, Dr. Grace lowest ($18.0M)
### 6. Branch Performance Dashboard
**Goal:** Compare hospital branches directly on cost, revenue, satisfaction, and patient volume, to see which locations are performing best.
**Visuals:** Total Branches KPI, treatment cost by branch (donut), revenue by branch (trend), patient satisfaction by branch, and patients by branch. Filterable by Hospital Branch.
**Findings:** `[ ]` *(pending screenshot)*
 
---
 
## 💡 Business Insights
 
1. **Higher-volume doctors and higher-satisfaction doctors are not the same people.** Dr. Ade brings in the most revenue but rates lowest on satisfaction (2.76), while Dr. Grace rates highest (3.26) but treats the fewest patients. This is a direct volume-vs-quality tradeoff worth investigating: is Dr. Ade being overloaded, or is Dr. Grace's smaller caseload actually what enables the higher satisfaction score?
2. **Transfer payments are disproportionately valuable.** Transfer accounts for only 29.6% of patients but 36.6% of revenue, at roughly $349K per transaction versus ~$241–269K for Insurance and Cash — suggesting transfer patients are undergoing costlier procedures, which has implications for how payment-method mix is forecast.
3. **The hospital network is treating patients from a state it doesn't operate a branch in.** 89 patients (about 18%) come from Kano, which has no corresponding branch in the Financial dashboard's branch list — worth confirming whether this is a referral pattern worth formalizing (or a data-linking gap between the state and branch fields).
4. **A 52.8% readmission rate is high enough to be a real quality-of-care flag**, not just a data point — worth cross-referencing against treatment type or department to see if it concentrates anywhere specific.
5. **Demand is seasonal**, peaking sharply in April and November (both patient volume and revenue) and bottoming out in February — useful for staffing and capacity planning.
6. **Oncology stands out as a quality outlier**: it brings in solid revenue ($28.0M, 3rd-highest department) but has the lowest satisfaction score of any department (276) — a gap between financial and experiential performance worth investigating directly.
---
 
## 🛠️ Tools & Technologies
 
- **Microsoft Excel** — joining and cleaning 4 source workbooks into one combined dataset
- **Power BI** — data modeling, 6-page interactive dashboard, slicers (Gender, Department, Hospital Branch), KPI cards, trend and comparison visuals

 
![Executive Dashboard](images/Healthcare_Executive_dashboard.png)
![Patient Analysis Dashboard](images/Healthcare_Patient_Dashboard.png)
![Financial Dashboard](images/Healthcare_Financial_dashboard.png)
![Treatment Dashboard](images/Healthcare_Treatment_Dashboard.png)
![Doctor Performance Dashboard](images/Healthcare_Doctor_Dashboard.png)
![Branch Performance Dashboard](images/Healthcare_Doctor_Dashboard.png)
 
## 📚 Skills Demonstrated
 
- Multi-workbook data consolidation in Excel
- Power BI data modeling
- Multi-page dashboard design
- - Patient, financial, and operational analytics
## 👤 Author
 
**[Shodunke Feranmi]**
 [GitHub](https://github.com/Shodunke-Feranmi)
