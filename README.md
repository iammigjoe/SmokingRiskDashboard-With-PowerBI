# SmokingRiskDashboard-With-PowerBI

![image alt](https://github.com/iammigjoe/SmokingRiskDashboard-With-PowerBI/blob/main/Dashboard.png?raw=true)

Smoking Health Risk Analysis Dashboard (Power BI)

Project Overview

The Smoking Health Risk Analysis Dashboard is an interactive Power BI report designed to analyze the health impact of smoking behaviors across different demographic groups.

This project focuses on transforming raw health data into clear, actionable insights related to smoking status, age, BMI, cholesterol, hypertension, and organ health risks.
It is built with a business and healthcare analytics mindset, making it suitable for Data Analyst and Business Analyst portfolios.

⸻

Objectives
	•	Analyze smoking behavior (Never / Current / Former)
	•	Compare age and BMI against overall averages
	•	Identify health risk patterns across age groups
	•	Explore relationships between smoking duration, daily intake, and health outcomes
	•	Deliver an intuitive and decision-oriented dashboard

⸻

Key KPIs & Metrics
	•	Total number of patients
	•	Average age vs global average
	•	Average BMI vs global average
	•	Smoking status distribution
	•	Smoking duration and daily intake
	•	Cholesterol and hypertension rates
	•	Organ condition (Healthy vs Damaged)

⸻

DAX Measures Used

Average Age vs Global Average

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

Average BMI vs Global Average

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

Calculated Column

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

Insights Generated
	•	Current smokers show higher BMI and health risk indicators
	•	Health deterioration increases with smoking duration
	•	Older age groups present higher cholesterol and hypertension rates
	•	Visual indicators allow fast identification of damaged vs healthy organs

⸻

Tools & Technologies
	•	Power BI Desktop
	•	DAX (Measures and Calculated Columns)
	•	Data Modeling
	•	Interactive Dashboard Design

⸻

Dataset Structure

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

Use Cases
	•	Healthcare analytics
	•	Public health awareness
	•	Data analytics portfolio project
	•	Business and medical decision support

⸻

⸻

Dashboard d’Analyse des Risques Liés au Tabagisme (Power BI)

Présentation du projet

Le Smoking Health Risk Analysis Dashboard est un tableau de bord interactif Power BI permettant d’analyser l’impact du tabagisme sur la santé selon différents profils démographiques.

L’objectif est de transformer des données de santé brutes en indicateurs clairs et exploitables afin de mieux comprendre les risques liés au tabac : âge, IMC, cholestérol, hypertension et état des organes.

⸻

Objectifs
	•	Analyser les statuts de fumeur (Jamais / Actuel / Ancien)
	•	Comparer l’âge et l’IMC à la moyenne globale
	•	Identifier les principaux facteurs de risque santé
	•	Étudier l’impact de la durée et de l’intensité du tabagisme
	•	Fournir une visualisation claire pour l’aide à la décision

⸻

Indicateurs clés
	•	Nombre total de patients
	•	Âge moyen vs moyenne globale
	•	IMC moyen vs moyenne globale
	•	Répartition des statuts de tabagisme
	•	Durée de tabagisme et consommation quotidienne
	•	Taux de cholestérol et d’hypertension
	•	État des organes (Sain / Endommagé)

⸻

Enseignements clés
	•	Les fumeurs actifs présentent des risques santé plus élevés
	•	Les indicateurs de santé se dégradent avec la durée du tabagisme
	•	Les groupes d’âge élevés sont plus exposés aux pathologies
	•	Les visuels facilitent une lecture rapide et orientée décision

⸻

Outils utilisés
	•	Power BI Desktop
	•	DAX (mesures et colonnes calculées)
	•	Modélisation de données
	•	Conception de dashboards interactifs

⸻

Cas d’usage
	•	Analyse en santé publique
	•	Sensibilisation aux risques du tabac
	•	Projet portfolio Data Analyst / Business Analyst
	•	Aide à la décision médicale et stratégique
