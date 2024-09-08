# Déploiement d'une Application de Gestion de Salaire avec Ansible et Jenkins

Ce projet utilise Jenkins et Ansible pour automatiser le déploiement d'une application de gestion de salaire. Le déploiement est orchestré à l'aide d'un Jenkinsfile pour piloter le processus CI/CD, tandis qu'Ansible gère la configuration des serveurs et l'installation de l'application.
Structure du Projet

Le projet est structuré comme suit :

```graphql

├── db-data/            # Contient les données de la base de données
├── php/                # Contient le code source PHP de l'application
├── roles/              # Dossier Ansible contenant les rôles nécessaires au déploiement
├── .my.cnf             # Fichier de configuration pour MySQL
├── Jenkinsfile         # Script Jenkins pour automatiser le pipeline CI/CD
├── README.md           # Documentation du projet
├── hosts.yml           # Fichier d'inventaire Ansible pour définir les serveurs cibles
├── inventaire/         # Contient les fichiers d'inventaire pour Ansible
└── playbook.yml        # Playbook Ansible pour déployer l'application

```
L'objectif de ce projet est de simplifier et automatiser l'installation et la configuration d'une application de gestion de salaire à travers Ansible, garantissant ainsi un déploiement cohérent et répétable.

# Prérequis

    Ansible : Assurez-vous qu'Ansible est installé sur votre machine de gestion. Suivez cette documentation pour l'installation.

    Serveur Linux : Un serveur distant ou une machine virtuelle exécutant une distribution Linux (comme Ubuntu ou CentOS) sur laquelle l'application sera déployée.

    Accès SSH : Accès SSH à la machine cible (public ou privé) avec un utilisateur disposant des privilèges sudo.

    Clé SSH : Générer une clé SSH pour l'accès au serveur distant depuis Ansible.

# Fonctionnement du Projet

## 1. Déploiement via Jenkins

Le fichier Jenkinsfile définit le pipeline de déploiement qui exécute les étapes suivantes :

    Checkout du Code : Jenkins récupère le code source de l'application depuis un dépôt Git.
    Déploiement avec Ansible : Jenkins exécute Ansible pour provisionner les serveurs et déployer l'application.
    Tests et Vérifications : Le pipeline peut inclure des tests pour vérifier que l'application est correctement déployée.

## 2. Déploiement via Ansible

L'application est déployée sur un serveur Linux à l'aide du playbook.yml Ansible. Ce playbook configure l'environnement nécessaire, installe les dépendances et déploie l'application.

## 3. Inventaire Ansible

Le fichier hosts.yml contient les adresses des serveurs où l'application sera déployée.

# Détails Techniques de l'Application

## Base de Données

Les données de l'application de gestion de salaire sont stockées dans une base de données MySQL. Les fichiers de données se trouvent dans le dossier db-data/.

## Code Source

L'application est développée en PHP, et le code se trouve dans le répertoire php/. Ansible est utilisé pour déployer ce code sur les serveurs cibles et configurer l'environnement.

## Nettoyage des Ressources

Pour supprimer l'application et nettoyer l'infrastructure, vous pouvez créer un playbook de nettoyage dans Ansible ou détruire les serveurs manuellement.
