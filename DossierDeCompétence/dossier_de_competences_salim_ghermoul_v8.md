# Dossier de compétences — Salim Ghermoul

## Profil
Ingénieur DevOps / Cloud confirmé, certifié CKAD, spécialisé dans la gouvernance de plateformes CI/CD, l'industrialisation des déploiements cloud / Kubernetes et l'intégration de pratiques DevSecOps dans des environnements multi-équipes.

## Synthèse
- Localisation : Paris / Île-de-France.
- Positionnement : Freelance DevOps plateforme / intégrateur DevOps / Lead DevOps.
- Socle central : Kubernetes / AKS, renforcé par la certification CKAD.
- Périmètre : CI/CD, cloud public Azure / AWS, Kubernetes, conteneurisation, orchestration, automatisation, sécurité de la chaîne logicielle, accompagnement transverse.
- Valeur apportée : standardiser les workflows de delivery, fiabiliser les mises en production, réduire le time-to-market et fournir aux équipes un socle de delivery exploitable et maintenable.

## Compétences clés
- Gouvernance et exploitation de plateformes Kubernetes multi-nœuds : K3S, AKS, scheduling, taints / tolerations, probes, Ingress, DNS, stockage persistant.
- Conception, industrialisation et refonte de chaînes de build / test / release / déploiement.
- Déploiements Azure et AWS sur AKS, Azure Functions, App Services, Container Instances, Static Web Apps et AWS Lambda.
- Intégration DevSecOps : SAST, SCA, DAST, scans de dépendances et de conteneurs, quality gates, gestion des secrets, RBAC / IAM.
- Standardisation des workflows de release, des pratiques de pull request et des patterns de déploiement.
- Accompagnement technique des équipes de développement, QA et sécurité sur les sujets cloud, CI/CD et delivery.
- Cadrage et pilotage de chantiers techniques à forte composante plateforme.
- Infrastructure de workflows IA : déploiement et exploitation de stacks RAG locales (LLM, base vectorielle, API d'inférence) sur Kubernetes.

## Expériences significatives

### Plateforme K3S IA / Streaming — Client formation digitale
**Période :** Juin 2026
**Client :** structure d'environ six personnes, secteur formation digitale.

**Contexte client**
- Projet livré pour une structure d'environ six personnes, incluant un développeur, dans le secteur de la formation digitale.
- L'objectif était de fournir deux livrables complémentaires : une plateforme de streaming pour les élèves et les enseignants, et une plateforme IA / RAG destinée à enrichir les parcours pédagogiques.
- La plateforme devait être mise en production et intégrée au flux de développement du client afin de permettre l'industrialisation progressive de fonctionnalités de type "questions sur vidéo".

**Volet Plateforme Kubernetes / Streaming**
- Conception et déploiement d'un cluster K3S multi-nœuds avec séparation des rôles entre un nœud control-plane CPU et un nœud worker GPU dédié aux workloads IA.
- Livraison industrialisée via un repository Git versionné regroupant les manifests Kubernetes YAML, les playbooks Ansible, les scripts Bash et la documentation technique publiée via MkDocs.
- Mise en place de la stack de streaming auto-hébergée sur le nœud CPU avec persistance via NFS et exposition des services via Nginx Ingress.
- Configuration de CoreDNS pour la résolution des domaines internes du cluster et le forwarding des requêtes externes vers des résolveurs publics.
- Mise en place de probes liveness / readiness sur les services critiques afin de sécuriser l'exploitation et la supervision des workloads.

**Volet IA / RAG**
- Construction d'une plateforme RAG locale reposant sur Ollama, FastAPI et Qdrant pour permettre l'interrogation de contenus pédagogiques à partir des transcripts déposés par les enseignants.
- Préparation des manifests Kubernetes pour les composants IA, avec gestion des ressources CPU / GPU, taints / tolerations et capacité d'évolution horizontale.
- Utilisation de Kubernetes Secrets et ConfigMaps pour séparer les données sensibles de la configuration applicative et d'infrastructure.
- Intégration d'un nœud GPU "GPU-ready" via installation de la stack NVIDIA Container Toolkit et du device plugin.
- Mise en œuvre d'un socle technique permettant au développeur client de brancher ensuite l'expérience IA dans l'interface pédagogique.

**Volet Réseau / sécurité / accès**
- Mise en place d'un reverse proxy Nginx Ingress pour l'exposition des services internes.
- Configuration locale de certificats TLS via cert-manager et gestion d'un point d'entrée sécurisé pour les différents services.
- Mise en œuvre d'une architecture réseau orientée sécurité avec WireGuard sur une VM AWS EC2 comme point de sortie du cluster.
- Routage du trafic sortant via le tunnel WireGuard et exposition limitée des services via le reverse proxy.
- Déploiement d'un dashboard Homepage pour visualiser les statuts, URLs et health checks de l'ensemble des services.

**Environnement technique :** K3S, Kubernetes, NVIDIA Container Toolkit, device plugin GPU, Ollama, FastAPI, Qdrant, Nginx Ingress, cert-manager, CoreDNS, WireGuard, AWS EC2, NFS, Ansible, Bash, Helm/manifests, Secrets, ConfigMaps, livenessProbe, readinessProbe, Homepage, MkDocs, Git.

### SimStew — Cloud DevOps & Product Engineering, Freelance
**Période :** Jan. 2026 — Avr. 2026

**Contexte client**
- SimStew est une plateforme communautaire en phase de lancement dans l'univers du jeu vidéo.
- Le projet s'inscrit dans une logique startup early-stage, avec un besoin de matérialiser rapidement une première version exploitable du produit, tout en posant une base technique propre et industrialisable.
- Le MVP devait permettre aux fondateurs de disposer d'un support de démonstration crédible pour la prospection, les échanges avec des partenaires et la recherche de financement.

**Volet DevOps / Plateforme**
- Conception d'une chaîne CI/CD structurée autour d'une stratégie de branches GitFlow, avec automatisation du cycle de livraison dès le premier commit.
- Intégration d'automatisations Jira au flux de développement afin d'aligner activité Git, suivi backlog et pilotage des releases.
- Mise en place de contrôles locaux et CI successifs : hooks pre-commit, tests unitaires, analyse statique SonarQube et quality gate avant poursuite de la chaîne.
- Orchestration via GitHub Actions des étapes de validation complémentaires : tests d'intégration, contrôles SAST / SCA et tests end-to-end.
- Mise en place d'un déploiement continu automatisé sur Vercel pour fiabiliser la mise en production du MVP et limiter les frictions de delivery dans un contexte de cycle court.

**Volet Architecture applicative / Delivery MVP**
- Conception de l'architecture applicative du MVP et choix d'une stack web adaptée à une logique de delivery rapide, de maintenabilité et de simplicité d'exploitation.
- Développement et mise en production d'une première version bêta sur Next.js, TypeScript, Tailwind CSS et Supabase.
- Mise en place d'une authentification OAuth via Discord et Google, en cohérence avec la cible communautaire du produit.
- Structuration des flux de travail techniques dans Jira pour supporter le découpage du backlog, le suivi des tâches et la coordination du delivery.
- Définition des principaux flux applicatifs et des parcours nécessaires à une démonstration exploitable du produit auprès de prospects et partenaires.

**Environnement technique :** Next.js, TypeScript, Tailwind CSS, Supabase, OAuth, GitHub Actions, Jest, SonarQube, Vercel, Jira, GitFlow, pre-commit hooks, SAST, SCA, tests E2E.

### Isagri — Lead Cloud DevOps Engineer
**Période :** Jan. 2024 — Août 2025

**Contexte client**
- ISAGRI évolue dans un environnement multi-projets et multi-équipes, avec des enjeux de standardisation des pratiques de delivery, de fiabilisation des déploiements et d'accélération de la mise en production.
- La mission s'inscrivait dans un périmètre plateforme partagé, au service de plusieurs équipes de développement et de QA, sur des déploiements Azure et AWS couvrant plusieurs modèles d'hébergement et plusieurs typologies applicatives.
- Le poste combinait gouvernance d'outillage, industrialisation de pipelines, intégration de contrôles de sécurité et accompagnement transverse des équipes sur la chaîne de delivery.

**Volet Gouvernance plateforme CI/CD et Cloud**
- Administration d'Azure DevOps, XL Release, XL Deploy et des souscriptions Azure utilisées pour les déploiements applicatifs.
- Définition, standardisation et documentation des pratiques CI/CD à l'échelle de plusieurs équipes, avec responsabilité directe sur l'adoption des workflows et la qualité d'exécution de la chaîne de delivery.
- Industrialisation des pipelines de build et de déploiement sous Azure DevOps et GitHub Actions, sur Azure et AWS, avec des déploiements sur AKS, Azure Functions, App Services, Container Instances, Static Web Apps et AWS Lambda.
- Contribution aux choix d'architecture DevOps liés aux workflows, à l'outillage, aux modes d'hébergement et aux patterns de déploiement, dans un cadre standardisé et documenté.
- Mise en place d'un socle de delivery cohérent permettant de réduire l'hétérogénéité des implémentations et d'accélérer l'onboarding des nouvelles applications sur la plateforme.

**Volet DevSecOps / sécurité de la chaîne logicielle**
- Intégration de pratiques DevSecOps au sein de la chaîne CI/CD, avec SAST, SCA, scans de dépendances, scans conteneurs et DAST, principalement via JFrog Artifactory / XRay, SonarQube et OWASP ZAP.
- Centralisation des secrets dans Azure Key Vault afin de réduire l'exposition d'informations sensibles dans les pipelines et d'améliorer la maîtrise des accès.
- Mise en place de mécanismes RBAC / IAM pour gérer les accès aux applications, aux environnements, aux outils de supervision et aux ressources cloud selon les besoins des équipes.
- Production de dashboards de sécurité à destination du security architect et du CTO pour fournir une vision consolidée de l'état de sécurité par application et par équipe.
- Intégration progressive de problématiques de software supply chain security dans les standards de plateforme.

**Volet Accompagnement transverse / référent DevOps**
- Rôle de référent DevOps / Cloud auprès de plusieurs équipes de développement et de QA.
- Accompagnement sur les bonnes pratiques de pull request, de delivery, de structuration des workflows CI/CD et de déploiement applicatif.
- Support opérationnel et debugging pour débloquer les sujets build, cloud, release et intégration continue.
- Présentations internes pour vulgariser les concepts DevOps / cloud et faciliter l'adoption des nouvelles pratiques de delivery.
- Appui aux arbitrages techniques relatifs aux solutions de déploiement, aux choix d'hébergement et aux règles de plateforme dans une logique de standardisation et de fiabilité.

**Volet Pilotage de projets techniques**
- Pilotage de trois chantiers techniques structurants dans un contexte multi-équipes, avec cadrage, priorisation, coordination et suivi d'avancement.
- Projet DAPR : implémentation de DAPR sur environ 30 microservices et 8 squads afin de standardiser les échanges inter-services et l'accès aux services externes, notamment Redis, Key Vault et les bases de données.
- Projet CI/CD from scratch après rachat de startup : création complète de la chaîne CI/CD pour accompagner le passage d'une équipe de 8 développeurs / 2 QA à 30 développeurs / 6 QA, avec choix des outils, définition de la stratégie, mise en place des KPIs et structuration du delivery.
- Projet de refonte des pipelines CI/CD : chantier de 3 mois mené au sein d'une équipe de 3 DevOps pour refactoriser les pipelines, concevoir une librairie standardisée et versionnée, paralléliser les tâches et réduire les temps d'exécution par trois, avec pilotage via backlog Jira.

**Impacts**
- Réduction du délai de mise à disposition d'un pipeline standard pour une nouvelle API ou SPA, de plus d'une journée à quelques minutes.
- Réduction du temps de test end-to-end de 2h30 à 40 minutes.
- Division par 3 des coûts d'infrastructure CI/CD via migration des runners vers AWS CodeBuild.
- Réduction du délai de provisioning d'un nouveau projet microservice de 3–4 jours à 1 jour.

**Environnement technique :** Azure DevOps, GitHub Actions, XL Release, XL Deploy, AKS, Azure Functions, Azure App Services, Azure Container Instances, Azure Static Web Apps, AWS Lambda, AWS CodeBuild, SonarQube, JFrog Artifactory / XRay, OWASP ZAP, Azure Key Vault, Kubernetes, DAPR, Jira.

### ALTEN — Développeur Java / DevOps
**Période :** Mar. 2022 — Nov. 2023

**Volet interne**
- Contribution à un MVP d'application de maintenance industrielle destiné à Airbus.
- Mise en place et exploitation d'une plateforme CI/CD sous Azure DevOps, avec pipelines YAML pour supporter les cycles de build et de validation.
- Construction d'environnements de test pour une application mobile et web à l'aide de Bash, Ansible, Vagrant et Docker.
- Contribution en développement Kotlin sur la partie mobile, avec un rôle centré sur le build et l'implémentation de fonctionnalités.

**Volet BNP Paribas**
- Contribution à des applications internes dans un environnement bancaire.
- Rôle mixte développement / DevOps, centré sur des activités de build.
- Développement full stack Java, côté front et back, sur des applications internes.
- Maintenance des pipelines DevOps associés au cycle de livraison applicatif.

### Quadient — Développeur VBA / Python
**Période :** Oct. 2020 — Oct. 2021
- Automatisation de traitements et de contrôles de données via VBA et Python.
- Production de reportings et d'analyses de données à destination des équipes financières et commerciales.
- Contribution à l'optimisation de processus internes liés à la manipulation et à la consolidation de données.

## Stack technique
| Domaine | Compétences |
|---|---|
| Cloud & Infrastructure | Azure, AWS, AKS, Kubernetes, K3S, Docker, Azure App Services, Azure Functions, AWS Lambda, Azure Container Instances, Azure Static Web Apps |
| CI/CD & Release | Azure DevOps, GitHub Actions, XL Release, XL Deploy, Jenkins, YAML, GitFlow, quality gates |
| DevSecOps | SonarQube, JFrog Artifactory, JFrog XRay, OWASP ZAP, SAST, SCA, DAST, Azure Key Vault, RBAC, IAM |
| Automation & IaC | Python, Bash, Ansible, Helm, Terraform, Vagrant |
| Développement | Java, Kotlin, TypeScript, JavaScript, Next.js, Tailwind CSS, Supabase |
| Architecture & plateforme | Microservices, DAPR, patterns de déploiement, standardisation CI/CD, industrialisation des workflows |
| IA & RAG | Ollama, Qdrant, FastAPI, Open WebUI, n8n, NVIDIA GPU stack |

## Formation et certifications
- 2026 — Certified Kubernetes Application Developer (CKAD).
- 2023 — Certified in CyberSecurity (CC), ISC².
- 2020 — Formation Ingénieur DevOps, 6 mois.
- 2019 — Bootcamp Python Data Science, 3 mois.
- Master of Science in Financial Markets Analysis, Rennes School of Business, 2014–2018.

## Langues
- Français.
- Anglais courant.
- Espagnol professionnel.
