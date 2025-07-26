# 🌐 multicloud-webserver-iac

## 📘 Présentation du projet

Ce projet a été conçu dans le cadre d'un TP avancé sur l'automatisation DevOps multi-cloud. L'objectif principal est de **déployer automatiquement un serveur web fonctionnel (NGINX)** sur des instances virtuelles provisionnées via **Terraform**, configurées via **Ansible**, et entièrement orchestrées par un pipeline **CI/CD GitHub Actions**.

L'infrastructure cible comprend **trois fournisseurs de cloud majeurs** :  
- Amazon Web Services (**AWS**)  
- Microsoft Azure (**Azure**)  
- Google Cloud Platform (**GCP**)

---

## 🎯 Objectifs pédagogiques

- Mettre en pratique les principes de l’Infrastructure as Code (**IaC**) avec **Terraform**
- Appliquer l’automatisation de configuration avec **Ansible**
- Mettre en place une **chaîne CI/CD complète** depuis GitHub
- Orchestrer un **déploiement multi-cloud automatisé**
- Déployer un service **NGINX** fonctionnel et accessible sur chaque cloud
- Assurer la **répétabilité**, **traçabilité** et **automatisation** totale du pipeline DevOps

---

## 💡 Justification du nom du dépôt

Le nom **`multicloud-webserver-iac`** est **précis, professionnel et représentatif** :

- `multicloud` : le projet cible **plusieurs fournisseurs cloud** (AWS, Azure, GCP)
- `webserver` : l'objectif final est de **déployer un serveur web (NGINX)** opérationnel sur chaque instance
- `iac` : tout le système repose sur le paradigme **Infrastructure as Code**, via Terraform et Ansible

Ce nom respecte les bonnes pratiques de nommage des projets DevOps : il est clair, explicite et facilement compréhensible dans un contexte professionnel ou académique.

---

## 🛠️ Technologies utilisées

| Technologie | Rôle |
|-------------|------|
| **Terraform** | Provisionnement de l’infrastructure (EC2, VM, Compute Engine) |
| **Ansible** | Configuration des instances (installation de NGINX) |
| **GitHub Actions** | Orchestration du pipeline CI/CD |
| **AWS / Azure / GCP** | Fournisseurs cloud pour déploiement multi-environnement |
| **NGINX** | Serveur web déployé sur chaque machine virtuelle |

---

## 🗂️ Structure du projet

```text
multicloud-webserver-iac/
├── terraform/ # Provisionnement multicloud
│ ├── main.tf
│ ├── variables.tf
│ ├── outputs.tf
│ ├── providers.tf
│ └── terraform.tfvars
├── ansible/ # Configuration des VM avec NGINX
│ ├── playbooks/
│ │ └── nginx.yml
│ ├── inventory/
│ │ └── hosts.yml
│ └── ansible.cfg
└── .github/
└── workflows/
└── deploy.yml # Pipeline CI/CD GitHub Actions
```

---

## 🔄 Pipeline DevOps

Voici les étapes clés automatisées via GitHub Actions :

1. **Code pushé sur GitHub** (`main`)
2. **Terraform Init/Plan/Apply** (pour chaque provider cloud)
3. **Extraction des IPs publiques des VM**
4. **Connexion SSH et configuration avec Ansible**
5. **Installation automatique de NGINX**
6. **Vérification que les serveurs web sont actifs (port 80 ouvert)**

---

## ⚠️ Prérequis

- Comptes créés sur **AWS**, **Azure** et **GCP**
- GitHub Secrets configurés pour :
  - `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`
  - `AZURE_CLIENT_ID`, `AZURE_CLIENT_SECRET`, `AZURE_SUBSCRIPTION_ID`, `AZURE_TENANT_ID`
  - `GOOGLE_CREDENTIALS` (clé JSON GCP)

---

## ✅ Résultat attendu

Une fois le pipeline déclenché, **trois serveurs web** (un par cloud) seront :
- Créés automatiquement
- Configurés avec Ansible
- Accessibles publiquement via leur adresse IP sur le port 80 (HTTP)
- Servant une page d’accueil NGINX par défaut

---

## 📍 Suivi CI/CD

Le pipeline CI/CD est visible depuis l'onglet **"Actions"** du dépôt GitHub.  
Les logs détaillent chaque étape : provisioning, configuration, test, succès ou erreurs.

---

## 📬 Auteur

- **Nom** : Ousmane KA 
- **Email** : ka.ousmane@uam.edu.sn 
- **Formation** : Master 2 - Ingénierie des Systèmes d’Information & Données (ISID)  
- **Encadrant** : Dr Massamba LO


