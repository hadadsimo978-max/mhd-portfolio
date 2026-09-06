---
title: "Automatisation de l'Évaluation des Risques par l'IA"
date: 2026-01-15
draft: false
tags: ["Machine Learning", "OpenVAS", "ELK", "Threat Intelligence"]
---

## 📌 Contexte du Projet
Face à la multiplication des vulnérabilités, les équipes de sécurité sont souvent submergées par le volume d'alertes. L'objectif de ce projet académique était de créer une solution de Threat Intelligence capable non seulement de scanner les vulnérabilités, mais surtout de les trier et de les prioriser intelligemment grâce à l'Intelligence Artificielle.

<!--more-->

## 🔍 Automatisation des Scans & Centralisation
Pour obtenir une visibilité totale et en temps réel sur l'infrastructure :
* **OpenVAS :** Déploiement et automatisation des scans de vulnérabilités pour identifier les failles du système.
* **ELK Stack :** Intégration d'Elasticsearch, Logstash et Kibana pour centraliser les alertes remontées par OpenVAS.
* **Visualisation :** Création de tableaux de bord (Dashboards) interactifs sur Kibana pour surveiller la posture de sécurité globale.

## 🧠 Priorisation par Machine Learning
La valeur ajoutée majeure du projet réside dans le traitement analytique des données remontées :
* **Modélisation :** Utilisation de la bibliothèque **scikit-learn** en Python pour développer un modèle de Machine Learning.
* **Évaluation Dynamique :** Le modèle analyse les scores CVSS (Common Vulnerability Scoring System) et évalue dynamiquement les menaces pour prioriser les correctifs sur les vulnérabilités les plus critiques, réduisant ainsi le bruit pour les analystes.

## 🎯 Résultats & Acquis
Ce projet prouve l'efficacité de l'approche "Data-Driven" en cybersécurité. Il m'a permis de fusionner mes compétences en sécurité défensive (Vulnerability Assessment) avec le développement Python et l'analyse de données, créant un outil d'aide à la décision redoutable pour les environnements SOC.