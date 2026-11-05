# TP2 - Gestion des tickets de maintenance

## Identité
Nom : Votre nom  
Prénom : Votre prénom

## Prérequis
- Node.js 22 ou supérieur
- npm
- Git

## Installation

```bash
npm install
```

## Lancement du serveur JSON

```bash
npx json-server db.json --port 3000
```

## Lancement de l’application Vue

```bash
npm run dev
```

## Fonctionnalités réalisées
- Liste des tickets avec recherche et filtrage par statut
- Création de tickets via formulaire validé
- Édition de ticket avec mise à jour via API REST
- Suppression avec confirmation
- Changement rapide de statut sans rechargement
- Navigation entre pages avec Vue Router
- Gestion des erreurs réseau et des tickets introuvables
- Persistance des données dans le fichier db.json

## Difficultés rencontrées
La partie la plus délicate a été la cohérence entre les routes Vue Router, la mise à jour immédiate de la liste et la persistance côté JSON Server. Il a fallu gérer proprement les cas où l’API répond en erreur ou quand un ticket n’existe plus, afin de ne pas bloquer l’application.

## Questions traitées

### 1) Différence entre POST, PUT et PATCH ?
POST sert à créer une ressource dans une collection. PUT remplace complètement une ressource existante en identifiant un objet précis par son ID. PATCH permet de modifier uniquement une partie d’une ressource sans remplacer tout le document.

### 2) Pourquoi une confirmation avant DELETE ?
La suppression est une action destructrice : elle supprime définitivement une donnée de la base et peut provoquer une perte de suivi. La confirmation protège l’utilisateur contre les clics accidentels et améliore l’expérience de navigation.

### 3) Quel est le rôle de Vue Router ?
Vue Router permet de gérer la navigation entre écrans sans recharger la page. Il synchronise l’URL avec l’état de l’application et facilite la création de pages comme la liste, la création et le détail d’un ticket.

### 4) Comment éviter les doublons lors de l’enregistrement ?
Il faut désactiver le bouton de soumission pendant l’enregistrement, valider les champs obligatoires et empêcher les re-soumissions rapides. La logique de formulaire doit également ne pas laisser passer plusieurs clics consécutifs avant la réponse réseau.

## Références techniques
- Vue 3
- Vue Router
- Axios
- JSON Server

## Déploiement local
L’application est démontrable localement avec :
1. le serveur JSON sur le port 3000 ;
2. le serveur Vite sur le port 5173 ;
3. l’ouverture du navigateur sur l’URL affichée par Vite.
