# SmokingRiskDashboard-With-PowerBI

![image alt](https://github.com/iammigjoe/SmokingRiskDashboard-With-PowerBI/blob/main/Dashboard.png?raw=true)

🇬🇧 README — Smoking Health Risk Analysis Dashboard (Power BI)

📌 Project Overview

The Smoking Health Risk Analysis Dashboard is an interactive Power BI report designed to analyze the health impact of smoking behaviors across different demographic groups.

The project focuses on transforming raw health data into clear, actionable insights related to smoking status, age, BMI, cholesterol, hypertension, and organ health risks.
It is built with a business & healthcare analytics mindset, suitable for data analyst or business analyst portfolios.

⸻

🎯 Objectives
	•	Analyze smoking behavior (Never / Current / Former)
	•	Compare age and BMI vs overall averages
	•	Identify health risk patterns across age groups
	•	Visualize the relationship between smoking duration, daily intake, and health outcomes
	•	Provide an intuitive and visually engaging dashboard for decision-making

⸻

📊 Key KPIs & Metrics
	•	Total Patients
	•	Average Age vs Global Average
	•	Average BMI vs Global Average
	•	Smoking Status Distribution
	•	Smoking Duration & Daily Intake
	•	Cholesterol & Hypertension Rates
	•	Organ Condition (Healthy vs Damaged)

⸻

🧮 DAX Measures Used

vs Average Age

vs Avg Age = 
VAR _CurrentAge = AVERAGE(health_dataset[Age])
VAR _OverallAge = CALCULATE(AVERAGE(health_dataset[Age]), ALL(health_dataset))
VAR _Diff = _CurrentAge - _OverallAge

RETURN
SWITCH(
    TRUE(),
    _Diff > 0, UNICHAR(9650) & " " & FORMAT(_CurrentAge, "0.0"),
    _Diff < 0, UNICHAR(9660) & " " & FORMAT(_CurrentAge, "0.0"),
    FORMAT(_CurrentAge, "0.0")
)

vs Average BMI

vs Avg BMI = 
VAR _CurrentBMI = AVERAGE(health_dataset[BMI])
VAR _OverallBMI = CALCULATE(AVERAGE(health_dataset[BMI]), ALL(health_dataset))
VAR _Diff = _CurrentBMI - _OverallBMI

RETURN
SWITCH(
    TRUE(),
    _Diff > 0, UNICHAR(9650) & " " & FORMAT(_CurrentBMI, "0.0"),
    _Diff < 0, UNICHAR(9660) & " " & FORMAT(_CurrentBMI, "0.0"),
    FORMAT(_CurrentBMI, "0.0")
)


⸻

🏷 Calculated Column

Age Group

Age Group = 
SWITCH(
    TRUE(),
    health_dataset[Age] <= 28, "18–28",
    health_dataset[Age] <= 38, "29–38",
    health_dataset[Age] <= 48, "39–48",
    health_dataset[Age] <= 58, "49–58",
    health_dataset[Age] <= 68, "59–68",
    "69+"
)


⸻

🧠 Insights Provided
	•	Current smokers tend to have higher BMI and health risk indicators
	•	Health deterioration increases with smoking duration
	•	Older age groups show higher cholesterol and hypertension rates
	•	Visual organ indicators help quickly identify damaged vs healthy conditions

⸻

🛠 Tools & Technologies
	•	Power BI Desktop
	•	DAX (Measures & Calculated Columns)
	•	Data Modeling
	•	Interactive Visual Design

⸻

📂 Dataset Structure

Main table: health_dataset

Key fields:
	•	Age
	•	Gender
	•	BMI
	•	Smoking_Status
	•	Cigarettes_Per_Day
	•	Years_of_Smoking
	•	Cholesterol_Level
	•	BP_Risk
	•	Organ
	•	Organ_Condition

⸻

🚀 Use Case
	•	Healthcare analytics
	•	Public health awareness
	•	Data analytics portfolio project
	•	Business & medical decision support

🇫🇷 README — Dashboard d’Analyse des Risques Liés au Tabagisme (Power BI)

📌 Présentation du projet

Le Smoking Health Risk Analysis Dashboard est un tableau de bord interactif Power BI permettant d’analyser l’impact du tabagisme sur la santé selon différents profils démographiques.

Ce projet vise à transformer des données de santé brutes en indicateurs clairs et exploitables, afin de mieux comprendre les risques liés au tabac : âge, IMC, cholestérol, hypertension et état des organes.

⸻

🎯 Objectifs
	•	Analyser les statuts de fumeur (Jamais / Actuel / Ancien)
	•	Comparer l’âge et l’IMC à la moyenne globale
	•	Identifier les facteurs de risque santé
	•	Étudier l’impact de la durée et de l’intensité du tabagisme
	•	Offrir une visualisation claire pour l’aide à la décision

⸻

📊 Indicateurs clés
	•	Nombre total de patients
	•	Âge moyen vs moyenne globale
	•	IMC moyen vs moyenne globale
	•	Répartition des statuts de tabagisme
	•	Durée de tabagisme et consommation quotidienne
	•	Taux de cholestérol et d’hypertension
	•	État des organes (Sain / Endommagé)

⸻

🧮 Mesures DAX

(Identiques à la version anglaise — voir section précédente)

⸻

🏷 Colonne calculée

Groupe d’âge

Age Group = 
SWITCH(
    TRUE(),
    health_dataset[Age] <= 28, "18–28",
    health_dataset[Age] <= 38, "29–38",
    health_dataset[Age] <= 48, "39–48",
    health_dataset[Age] <= 58, "49–58",
    health_dataset[Age] <= 68, "59–68",
    "69+"
)


⸻

🧠 Enseignements clés
	•	Les fumeurs actifs présentent davantage de risques santé
	•	L’IMC et les pathologies augmentent avec la durée du tabagisme
	•	Les groupes d’âge élevés montrent des risques accrus
	•	Les visuels permettent une lecture rapide et intuitive

⸻

🛠 Outils utilisés
	•	Power BI Desktop
	•	DAX (mesures & colonnes calculées)
	•	Modélisation de données
	•	Design de dashboards interactifs

⸻

🚀 Cas d’usage
	•	Analyse santé publique
	•	Sensibilisation aux risques du tabac
	•	Projet portfolio Data / Business Analyst
	•	Aide à la décision médicale

⸻
Projet Power BI – Analyse des risques santé
