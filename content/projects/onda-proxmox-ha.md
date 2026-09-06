---
title: "ONDA : Infrastructure Haute Disponibilité (Proxmox HA & TrueNAS)"
date: 2025-08-31
draft: false
tags: ["Proxmox HA", "TrueNAS", "GNS3", "VLAN", "Firewalling"]
---

## 📌 Contexte du Projet
Lors de mon intégration à l'Office National des Aéroports (ONDA), l'objectif principal était de moderniser et de sécuriser l'infrastructure d'hébergement existante. L'enjeu était critique : garantir une continuité de service absolue (zéro downtime) pour les applications métiers de l'office.

<!--more-->

## 🏗️ Architecture Haute Disponibilité (HA)
Pour répondre aux exigences de résilience, j'ai conçu et déployé une architecture de virtualisation tolérante aux pannes :
* **Cluster Proxmox VE :** Déploiement d'un cluster multi-nœuds en mode Haute Disponibilité (HA). En cas de défaillance matérielle d'un serveur, les machines virtuelles (VMs) basculent automatiquement sur un nœud sain.
* **Sécurisation du Quorum :** Intégration d'un **Qdevice** (configuré virtuellement via **GNS3**) pour agir comme arbitre. Cela permet de prévenir les scénarios de "split-brain" (où deux moitiés du cluster pensent être actives simultanément), garantissant ainsi l'intégrité des données.

## 💾 Stockage Centralisé & Résilience
Une infrastructure HA nécessite un stockage partagé performant et fiable :
* Déploiement de **TrueNAS** comme solution de stockage réseau centralisée (SAN/NAS).
* Optimisation des flux de lecture/écriture pour les disques virtuels des VMs, augmentant ainsi les performances globales et la fiabilité de l'architecture.

## 🔒 Sécurité Interne & Segmentation
La sécurité réseau a été durcie en profondeur pour protéger les flux critiques :
* **Segmentation VLAN :** Mise en place d'une isolation stricte des flux métiers via des VLANs dédiés, réduisant la surface d'attaque en cas de compromission latérale.
* **Firewalling :** Configuration d'un pare-feu dédié pour contrôler et filtrer le trafic inter-VLAN et les accès externes, assurant un cloisonnement étanche des environnements de production.

## 🎯 Résultats & Acquis
Ce projet a permis de livrer à l'ONDA une infrastructure modernisée, robuste et hautement disponible. Sur le plan technique, il a considérablement renforcé mon expertise dans la gestion des clusters critiques, le stockage réseau d'entreprise et l'architecture réseau sécurisée.