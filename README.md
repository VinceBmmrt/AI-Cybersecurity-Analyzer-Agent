# 🔐 AI Cybersecurity Analyzer

> Une application web alimentée par l'IA qui analyse du code Python pour détecter des failles de sécurité — déployée sur Azure et GCP avec Terraform & Docker.

---

## 🇫🇷 Français

### C'est quoi ce projet ?

L'**AI Cybersecurity Analyzer** est une application web full-stack alimentée par l'IA, qui analyse du code Python pour détecter des failles de sécurité. Elle combine l'analyse statique avec des recommandations intelligentes pour aider les développeurs à écrire du code plus sécurisé.

### Stack Technique

- **IA** : API OpenAI pour l'analyse intelligente du code
- **Analyse de sécurité** : Semgrep via serveur MCP
- **Frontend** : React / Next.js
- **Backend** : FastAPI
- **Conteneurisation** : Docker
- **Infrastructure as Code** : Terraform
- **Plateformes Cloud** : Microsoft Azure & Google Cloud Platform

### Ce qui a été construit et déployé

✅ Mise en place du projet Cybersecurity Analyzer  
✅ Configuration de Semgrep pour l'analyse statique de sécurité  
✅ Création de la configuration d'environnement  
✅ Tests en local avec les serveurs de développement  
✅ Build et exécution du conteneur Docker  
✅ Déploiement sur **Azure Container Apps** via Terraform  
✅ Déploiement sur **Google Cloud Run** via Terraform

### Déploiement — Azure

Le déploiement Azure utilise **Terraform** pour provisionner :

- Azure Container Apps (exécution serverless de conteneurs)
- Azure Container Registry (ACR) pour le stockage des images Docker
- Les workspaces Terraform pour la gestion des environnements

### Déploiement — Google Cloud Platform

Le déploiement GCP utilise **Terraform** pour :

1. Activer les APIs Google Cloud nécessaires
2. Builder l'image Docker en local
3. Pousser l'image vers Google Container Registry (GCR)
4. Déployer le service Cloud Run
5. Configurer l'accès public

### Azure vs GCP — Comparaison

| Fonctionnalité         | Azure Container Apps                | Google Cloud Run              |
| ---------------------- | ----------------------------------- | ----------------------------- |
| Démarrage à froid      | ~30 secondes                        | ~5-10 secondes                |
| Scale to Zero réel     | Partiel (processus en arrière-plan) | Oui — s'arrête complètement   |
| Modèle de tarification | Par vCPU/Mémoire allouée            | Par requête + temps de calcul |
| Registre de conteneurs | Service séparé (ACR)                | Intégré (GCR)                 |
| Format d'URL           | Sous-domaine long                   | Plus court, plus propre       |
| Offre gratuite         | Limitée                             | Généreuse (2M requêtes/mois)  |

### Lequel est le meilleur ?

- **Pour apprendre** : Google Cloud Run (meilleure offre gratuite, démarrage plus rapide)
- **En production** : Dépend de votre charge de travail et de votre écosystème cloud existant

### Compétences acquises

- Expérience de déploiement multi-cloud (Azure + GCP)
- Infrastructure as Code avec Terraform
- Conteneurisation Docker et gestion des registres
- Gestion des variables d'environnement sur différentes plateformes
- Gestion des coûts cloud et optimisation
- Patterns d'architecture serverless pour conteneurs

---

## 🇬🇧 English

### What is this project?

The **AI Cybersecurity Analyzer** is a full-stack AI application that scans Python code for security vulnerabilities. It combines static analysis with AI-powered insights to help developers write more secure code.

### Tech Stack

- **AI**: OpenAI API for intelligent code analysis
- **Security Scanning**: Semgrep via MCP server
- **Frontend**: React / Next.js
- **Backend**: FastAPI
- **Containerization**: Docker
- **Infrastructure as Code**: Terraform
- **Cloud Platforms**: Microsoft Azure & Google Cloud Platform

### What Was Built & Deployed

✅ Set up the Cybersecurity Analyzer project  
✅ Configured Semgrep for static security analysis  
✅ Created environment configuration  
✅ Tested locally with development servers  
✅ Built and ran the Docker container  
✅ Deployed to **Azure Container Apps** using Terraform  
✅ Deployed to **Google Cloud Run** using Terraform

### Deployment — Azure

The Azure deployment uses **Terraform** to provision:

- Azure Container Apps (serverless container runtime)
- Azure Container Registry (ACR) for Docker image storage
- Terraform workspaces for environment management

### Deployment — Google Cloud Platform

The GCP deployment uses **Terraform** to:

1. Enable required Google Cloud APIs
2. Build the Docker image locally
3. Push the image to Google Container Registry (GCR)
4. Deploy the Cloud Run service
5. Configure public access

### Azure vs GCP — Comparison

| Feature            | Azure Container Apps           | Google Cloud Run             |
| ------------------ | ------------------------------ | ---------------------------- |
| Cold Start         | ~30 seconds                    | ~5-10 seconds                |
| True Scale to Zero | Partial (background processes) | Yes — completely stops       |
| Pricing Model      | Per vCPU/Memory allocated      | Per request + compute time   |
| Container Registry | Separate service (ACR)         | Integrated (GCR)             |
| URL Format         | Long subdomain                 | Shorter, cleaner             |
| Free Tier          | Limited                        | Generous (2M requests/month) |

### Which is Better?

- **For learning**: Google Cloud Run (better free tier, faster cold starts)
- **For production**: Depends on your workload and existing cloud ecosystem

### Skills Gained

- Multi-cloud deployment experience (Azure + GCP)
- Infrastructure as Code with Terraform
- Docker containerization and registry management
- Environment variable handling across platforms
- Cloud cost management and optimization
- Serverless container architecture patterns

---

## Architecture

```
Internet
    │
    ▼
┌─────────────────────────────────────────┐
│           Cloud Run / Container Apps     │
│         (Serverless Container Runtime)   │
└───────────────────┬─────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────┐
│            Docker Container              │
│  ┌──────────────┐  ┌──────────────────┐ │
│  │ Next.js      │  │ FastAPI Backend  │ │
│  │ Frontend     │  │ + Semgrep MCP    │ │
│  └──────────────┘  └──────────────────┘ │
└─────────────────────────────────────────┘
                    │
                    ▼
         ┌──────────────────┐
         │   OpenAI API     │
         └──────────────────┘
```

---

_Déployé sur Azure Container Apps & Google Cloud Run — Infrastructure gérée avec Terraform_  
_Deployed on Azure Container Apps & Google Cloud Run — Infrastructure managed with Terraform_
