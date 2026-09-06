---
title: "Cyber Range UM6P : Architecture Hybride (Proxmox & Docker)"
date: 2026-06-30
draft: false
tags: ["Proxmox", "Docker", "Zero Trust", "pfSense", "Llama 3"]
---

## 📌 Contexte du Projet
Dans le cadre de la formation pratique en cybersécurité à l'HEWB-UM6P, il était nécessaire de concevoir un environnement d'apprentissage sur mesure. L'objectif de ce projet de fin d'études était de construire un "Cyber Range" (champ de tir numérique) scalable, sécurisé et capable d'héberger des scénarios d'attaque et de défense complexes, tout en garantissant une isolation totale par rapport au réseau de production de l'université.

<!--more-->

## 🏗️ Architecture Technique
Pour répondre aux exigences de performance et de flexibilité, j'ai opté pour une approche hybride :
* **Bare-Metal (Proxmox VE) :** Déploiement d'un cluster d'hyperviseurs pour héberger les machines virtuelles lourdes (Windows Server, cibles Active Directory, solutions SIEM).
* **Cloud-Native (Docker) :** Conteneurisation des services légers et des applications web vulnérables (CTF), permettant un déploiement, une réinitialisation et une destruction rapides des laboratoires.

## 🔒 Sécurité & Micro-segmentation (Zero Trust)
L'infrastructure devait être un modèle de sécurité "Zero Trust" par conception :
* **Micro-segmentation :** Utilisation de **pfSense** et du taggage **VLAN 802.1Q** pour segmenter drastiquement les réseaux. Chaque laboratoire ou scénario de test est isolé dans sa propre enclave réseau.
* **Accès Sécurisé (SSO) :** Implémentation d'**Apache Guacamole** en tant que passerelle d'accès "clientless". Les étudiants accèdent à leurs machines cibles directement via leur navigateur web, avec une authentification centralisée (Single Sign-On), sans nécessiter de client VPN lourd, réduisant ainsi la surface d'attaque globale.

## 🤖 Intégration de l'IA (RAG & Llama 3)
Pour optimiser l'accompagnement pédagogique des étudiants de manière autonome, j'ai intégré un assistant virtuel intelligent et 100 % local :
* Déploiement sécurisé du modèle LLM **Llama 3**.
* Mise en place d'une architecture **RAG (Retrieval-Augmented Generation)** propulsée par la base de données vectorielle **ChromaDB**. 
* **Résultat :** L'assistant ingère la documentation technique des laboratoires pour fournir des indices contextuels aux étudiants lorsqu'ils sont bloqués, sans jamais compromettre les scénarios en donnant les solutions directes.

## 🎯 Résultats & Acquis
Le Cyber Range livré est une plateforme robuste, résiliente et prête pour la production. Ce projet m'a permis de consolider mon expertise dans la convergence entre l'ingénierie système, l'architecture réseau sécurisée (Firewalling, Zero Trust) et l'intégration de solutions d'intelligence artificielle appliquées à la cybersécurité.