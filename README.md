# GitHub Actions (CI/CD) Cheatsheet

## Table des matières
  - [1. Introduction fondamentale](#1-introduction-fondamentale)
    - [1.1 Introduction](#11-introduction)
    - [1.2 Les outils CI/CD](#12-les-outils-ci-cd)
        - [1.2.1 Gestion des versions](#121-gestion-des-versions)
        - [1.2.2 Serveurs d'intégration continue (CI)](#122-serveurs-dintégration-continue-ci)
        - [1.2.3 Serveurs de livraison et de déploiement continu (CD)](#123-serveurs-de-livraison-et-de-déploiement-continu-cd)
        - [1.2.4 Orchestration de conteneurs](#124-orchestration-de-conteneurs)
        - [1.2.5 Monitoring et logging](#125-monitoring-et-logging)
         - [1.2.6 Gestion de Version Sémantique (SemVer)](#126-gestion-de-version-sémantique-semver)
  - [2. Introduction à Github Actions](#2-introduction-à-github-actions)
    - [2.1 Introduction](#21-introduction)
    - [2.2 Composants de Github Actions](#22-composants-de-github-actions)
  - [3. Créer un premier workflow](#3-créer-un-premier-workflow)
    - [3.1 Exemple de workflow](#31-exemple-de-workflow)
    - [3.1.1 Déclencheurs d'évènements communs (trigger)](#311-déclencheurs-dévènements-communs-trigger)

---
# 1 Introduction fondamentale
## 1.1 Introduction à la CI/CD

*Métaphore utilisée : grand repas de famille*

Comme dans un repas, **plusieurs** étapes : 

### 1.1.1 Planification

| Étape | Côté Restaurant | Côté Développement |
|-------|-----------------|-------------------|
| Planification | Liste de courses détaillée | - Utilisation de Jira/Trello<br>- Création de tickets<br>- Planification méticuleuse des tâches |

### 1.1.2 Préparation et Cuisson

| Étape | Côté Restaurant | Côté Développement |
|-------|-----------------|-------------------|
| Préparation et Cuisson | - Cœur de l'activité<br>- Mélange des ingrédients selon la recette | Intégration Continue (CI)<br>- Intégration de chaque commit dans la branche principale |

### 1.1.3 Dressage

| Étape | Côté Restaurant | Côté Développement |
|-------|-----------------|-------------------|
| Dressage | - Décoration de la production<br>- Préparation de la cuisine | Livraison Continue (CD)<br>- Déploiement de chaque commit en production |

### 1.1.4 Service

| Étape | Côté Restaurant | Côté Développement |
|-------|-----------------|-------------------|
| Service | - Service aux invités<br>- Dégustation de la cuisine | Déploiement Continu (CD)<br>- Déploiement de chaque commit en production |

---
## 1.2 Les outils CI/CD

CI/CD = au coeur du DevOps
- Automatisation des compilation, tests, déploiement

### 1.2.1 Gestion des versions

Versioning = gestion des versions -> essentielle pour suivre les modifications, et permet aux équipes de collaborer efficacement

- **Git** : gestion décentralisée
- **Subversion (SVN)** : gestion centralisée
- **Mercurial** : gestion distribuée

### 1.2.2 Serveurs d'intégration continue (CI)

**Serveurs d'intégration continue** = systèmes automatisés jouant un rôle crucial dans le dev' logiciel moderne.
**Fonction** : compilation **automatique** après chaque commit

C'est souvent des conteneurs / machines virtuelles (environnement isolé) -> garantie que l'exécution des tests est propre et contrôlée

<!-- Intégrer les liens de site officiel de chaque outil -->
- **Jenkins** ([ici](https://www.jenkins.io/)) : outil open source de CI/CD
- **Gitlab CI** ([ici](https://docs.gitlab.com/ee/ci/)) : outil de CI/CD **intégré** par Gitlab
- **Github Actions** ([ici](https://docs.github.com/en/actions)) : outil de CI/CD **intégré** à Github
- **CircleCI** ([ici](https://circleci.com/)) : outil de CI/CD pour le développement de logiciel
- **TravisCI** ([ici](https://www.travis-ci.com/)) : outil de CI/CD pour construire et tester des projets 

### 1.2.3 Serveurs de livraison et de déploiement continu (CD)

**Serveurs de livraison continue** = systèmes automatisés qui permettent de déployer les applications **en production** -> favorise les déploiements rapides, fiables et sécurisés

En somme, c'est une transformation de la manière dont les logiciels sont **développés**, **testés** et **déployés**

**Fonction** : déploiement automatisé en production

**Exemples** :
- **Spinnaker** : déploiement en production
- **ArgoCD** : déploiement en production
- **Docker** : déploiement en production

### 1.2.4 Orchestration de conteneurs

Métaphore : **Orchestration** = **Orchestre** -> permet de « dupliquer » des conteneurs, de les déployer, de les gérer, de les mettre à jour, de les supprimer, etc.

En cas d'évènement important, on peut déployer des conteneurs supplémentaires pour gérer la charge sans surcharger le serveur principal et faire continuer le service. 
(exemple : Doctolib lors d'une pandémie)

**Fonction** : gestion et déploiement de conteneurs

**Exemples** :
- **Docker Swarm** : gestion de cluster
- **Kubernetes** : orchestration de conteneurs

### 1.2.5 Monitoring et logging

Ce sont deux aspects essentiels pour la gestion des applications, fournissant des informations sur l'état des applications et leur performance.

**Monitoring** : surveillance des performances
**Logging** : suivi des événements et erreurs

**Exemples** :
- **Prometheus** : monitoring open source
- **Grafana** : monitoring open source
- **ELK** : gestion des logs

### 1.2.6 Gestion de Version Sémantique (SemVer)

##### **SemVer** = **Semantic Versioning**

**Champs** :
- **MAJOR** : changements incompatibles
- **MINOR** : ajouts de fonctionnalités
- **PATCH** : corrections de bugs

---

# 2. Github Actions

## 2.1 Introduction

### 2.1.1 L'écosystème Github Actions

L'écosystème de Github Actions englobe : 
- **Dépots Git** : au coeur de Github, permet de stocker les fichiers et les versions des projets
- **Pull Requests** : permet de proposer des modifications à un projet
- **Github Issues** : permet de suivre les problèmes et les idées des utilisateurs
- **Github Pages** : permet de publier des pages web statiques à partir de dépots Github
- **Github Marketplace** : permet de trouver des actions Github, y compris pour Github Actions
- **Github Security** : fonctionnalités de sécurité pour les dépots Github
- **Explore** : permet de trouver des projets, collections, tendances, etc., partagés par la communauté GitHub

### 2.1.2 Intégration de Github Actions

#### Exemple de workflow : 
- **Automatisation** : permet de lancer des actions automatiquement lors d'évènements spécifiques
- **Déploiement Automatisé** : permet de déployer des applications en production
- **Intégration avec GitHub Issues** : permet de suivre les problèmes et les idées des utilisateurs
- **Sécurité et contrôle** : permet de sécuriser les dépots Github

### 2.1.3 Gestion des Minutes d'Exécution

- **Minutes d'exécution** : 2000 minutes gratuites par mois, facturation au-delà

Pour contrôler son utilisation -> dashboard d'utilisation, création d'alertes, etc.

## 2.2 Composants de Github Actions

### 2.2.1 Configuration avec fichier YAML

Pour configurer un workflow, on utilise un fichier YAML dans le dépot.

Elle définit les évènements qui déclenchent le workflow, les jobs à exécuter, et les étapes à effectuer de chaque job.

### 2.2.2 Les composants clés

- **Workflow** : Séquence d'instructions automatisées par des évènements spécifiques **dans votre dépot Github**
- **Jobs** : Collection de steps à exécuter dans un environnement spécifique (séquentiellement ou en parallèle)
- **Steps** : Tâches individuelles au sein d'un job, pouvant exécuter des actions ou des commandes shell
- **Actions** : Blocs de code réutilisables qui effectuent des tâches spécifiques (ex : checkout, build, test, deploy)
- **Runners** : Environnement dans lequel les jobs sont exécutés



### 2.2.3 Gestion des minutes d'exécution

Optimiser les minutes d'exécution -> mettre en place des workflows optimisés, utiliser des runners optimisés, etc.

## 3. Créer un premier workflow

## 3.1 Exemple de workflow

Dans ce présent dépôt, on va créer un workflow qui va exécuter un script simple.
Le dossier `.github/workflows/` contient le fichier [ci.yml](.github/workflows/ci.yml)

<details>
<summary>Explication du fichier ci.yml</summary>

`name` : nom du workflow  
`on` : évènements qui **déclenchent** le workflow  
`jobs` : collection de jobs à **exécuter**  
`build` : job à **exécuter**  
`runs-on` : **environnement** dans lequel le job est **exécuté**  
`steps` : tâches **individuelles** au sein d'un job, pouvant **exécuter** des actions ou des commandes shell  

</details>

### 3.1.1 Déclencheurs d'évènements communs (trigger)

Les workflows sont déclenchés par des évènements spécifiques.
En voici quelques exemples :

- **Push** : déclenche le workflow lorsqu'un commit est pushé sur le dépot
- **Pull Request** : déclenche le workflow lorsqu'un pull request est créé ou modifié
- **Schedule** : Planifie le workflow à une heure spécifique en utilisant un `cron`
- **Cron** : déclenche le workflow à une heure spécifique


Exemple de trigger avec `schedule` :

```yaml
on:
  schedule:
    - cron: '0 0 * * *'
```
Ici, le workflow sera déclenché chaque jour à 00:00.

## 3.2 Les triggers dans Github Actions

Github Actions permet de déclencher des workflows en fonction d'évènements spécifiques.

Voilà les triggers disponibles :

- **Push** 
  - Syntaxe : `on: push: [branches]`
  - Description : Déclenche le workflow lorsqu'un commit est **pushé** sur le dépot
- **Pull Request**
  - Syntaxe : `on: pull_request: [branches]`
  - Description : Déclenche le workflow lorsqu'un **pull request** est créé ou modifié
- **Schedule**
  - Syntaxe : `on: schedule:`
  - Description : Déclenche le workflow à une heure **spécifique**, en utilisant un `cron`
- **Workflow Dispatch**
  - Syntaxe : `on: workflow_dispatch`
  - Description : Déclenche le workflow **manuellement**, offrant une flexibilité


Un exemple de trigger est disponible : [exemple-trigger.yml](.github/workflows/exemple-trigger.yml)


## 4. Les actions dans Github Marketplace

### 4.1 Découvrir des actions
Github Marketplace est une plateforme qui permet de trouver des outils, y compris pour Github Actions.

Conseils principal pour trouver des actions : utiliser la barre de recherche comme un guide
-> Taper des mots clés relatifs à ce que l'on souhaite automatiser
-> Explorer les options disponibles

### 4.1.1 Sélectionner la meilleure action
- Regardez les **étoiles** et **commentaires** pour savoir si l'action est populaire et fiable : ce sont des indices précieux
- Vérifiez que l'action est **compatible** 

### 4.2 Créer un workflow avec une action

Imaginons que l'on souhaite créer un workflow qui va établir une chaîne de montage automatisée de test d'application
Voici la « recette » :
1. **Définir les déclencheurs avec `name: <action-name>` et `on: <trigger>`**

De façon "non-initié", on dit : *"Chaque fois que quelque chose est pushé sur le dépot, exécuter le workflow"*

2. **Ajouter les outils (Actions) à la chaîne** :
```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14'
      - run: npm install
      - run: npm test
```
   Dans cet exemple :
    - `actions/checkout@v2` vous permet de **cloner** votre code sur le serveur qui exécutera le workflow.
    - `actions/setup-node@v2` **prépare** l'environnement pour Node.js.
    - `npm install` et `npm test` sont vos commandes pour **assembler et tester** le produit.

  ### 4.3 Gestion et parallélisation des jobs

 La gestion des jobs dans un workflow repose sur 2 concepts clés : la **dépendance entre jobs** et la **parallélisation**
 - **Dépendance entre jobs** : permet de définir un ordre de déclenchement des jobs, ce qui garantit que les tâches sont exécutées dans une **séquence** logique 

 - **Parallélisation** : optimise le temps d'exécution du workflow en exécutant simultanément des jobs en **parallèle**

---
# 5. Les Secrets dans Github Actions

## 5.1 Gestion des Secrets

### 5.1.1 Découverte d'un secret

#### Définition
Un secret est une information **sensible** qui doit être **protégée**, comme des clés API, des mots de passe, un jeton d'accès, une clé SSH, etc.

#### Pourquoi les utiliser ?

Les secrets sont utilisés pour : 
- Protéger vos données sensibles contre les expositions accidentelles
- Séparer les informations de configuration
- Permettre une modification et gestion centrélisée des données, sans changer le code source


### 5.1.2 L'utilisation pratique des secrets

- Exemple de fichier de workflow comme `deploy.yml`, qui utilise un secret pour accéder à un service externe

- `appleboy/ssh-action` : action GitHub qui permet d'établir une connexion SSH à un serveur distant de façon sécurisée
-> Facilite l'automatisation des déploiements


### 5.1.3 Le script `deploy.sh`

- Un script shell côté serveur qui contient les commandes nécessaires pour mettre à jour et redémarrer l'application
- Script invoqué dans Github Actions, démontrant comment les tâches peuvent être **automatisées**
