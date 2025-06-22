# 📚 Exercice Pratique : Gestion d'une Bibliothèque

## 🎯 Objectif

Créer une application Node.js pour gérer une bibliothèque avec des livres, des auteurs et des emprunts en utilisant MongoDB et Mongoose.

## 📋 Contexte

Vous êtes développeur junior et votre client, la Bibliothèque Municipale de CodeVille, souhaite numériser sa gestion. Vous devez créer une application qui permet de gérer les livres, les auteurs et les emprunts.

## 📁 Structure du Projet

```
bibliotheque/
├── models/
│   ├── connection.js
│   ├── authors.js
│   ├── books.js
│   └── loans.js
├── app.js
├── package.json
└── README.md
```

## 📝 Étapes de l'Exercice

### Étape 1 : Récupération du Projet

1. Cloner le repository : `git clone https://github.com/Dada342/bibliotheque.git`
2. Aller dans le dossier : `cd bibliotheque`
3. Installer les dépendances : `yarn install`
4. Installer mongoose : `yarn add mongoose`


### Étape 2 : Configuration de la Base de Données

1. Créer une base de données nommée `bibliotheque`
2. Configurer la connexion dans `models/connection.js`

**Indice :** Utilisez la documentation Mongoose pour la syntaxe de connexion.

### Étape 3 : Création des Modèles

#### Auteurs (models/authors.js)

- `firstName` : (prénom)
- `lastName` : (nom)
- `nationality` : (nationalité)
- `biography` : (biographie)
- `birthDate` : (date de naissance)
- `address` : sous-document (city, street)

#### Livres (models/books.js)

- `title` : (titre)
- `author` : ObjectId référence vers authors
- `genre` : (genre)
- `publicationYear` : (année de publication)
- `copies` : (nombre d'exemplaires)
- `availableCopies` : (exemplaires disponibles)

#### Emprunts (models/loans.js)

- `book` : ObjectId référence vers books
- `borrowerName` : (nom de l'emprunteur)
- `borrowerEmail` : (email de l'emprunteur)
- `loanDate` : (date d'emprunt)
- `returnDate` : (date de retour prévue)
- `returned` : (si le livre a été retourné)

### Étape 4 : Implémentation des Fonctionnalités

Dans `app.js`, implémenter les opérations CRUD suivantes :

#### Pour les Auteurs :

- ✅ Créer 3 auteurs différents
- ✅ Afficher tous les auteurs
- ✅ Rechercher un auteur par son nom
- ✅ Modifier la biographie d'un auteur

#### Pour les Livres :

- ✅ Créer 5 livres avec des références vers les auteurs
- ✅ Afficher tous les livres avec les informations des auteurs (populate)
- ✅ Rechercher les livres d'un genre spécifique
- ✅ Modifier le nombre d'exemplaires d'un livre

#### Pour les Emprunts :

- ✅ Créer 3 emprunts différents
- ✅ Afficher tous les emprunts avec les détails des livres
- ✅ Marquer un emprunt comme retourné
- ✅ Supprimer un emprunt

### Étape 5 : Requêtes Avancées (Bonus)

- 🔍 Trouver tous les livres disponibles (availableCopies > 0)
- 🔍 Trouver les emprunts en retard (returnDate < aujourd'hui et returned = false)
- 🔍 Compter le nombre de livres par genre
- 🔍 Trouver l'auteur qui a le plus de livres

## 🎯 Critères d'Évaluation

- ✅ Structure du projet respectée
- ✅ Modèles correctement définis avec les relations
- ✅ Opérations CRUD fonctionnelles
- ✅ Utilisation correcte de `populate()`
- ✅ Gestion des erreurs
- ✅ Code commenté et lisible
- ✅ Fonctionnalités bonus implémentées

## 💡 Conseils

- **Documentation** : Consultez la documentation Mongoose pour les méthodes CRUD
- **Relations** : Pensez à utiliser `populate()` pour afficher les données liées
- **Test** : Testez chaque fonctionnalité avant de passer à la suivante

- **Commentaires** : Commentez votre code pour expliquer votre logique

## 📚 Ressources Utiles

- [Documentation Mongoose](https://mongoosejs.com/)
- [MongoDB Atlas](https://www.mongodb.com/atlas)
- [Node.js](https://nodejs.org/)
- [MongoDB Compass](https://www.mongodb.com/compass)

## ❓ Questions à se poser

- Comment créer une relation entre deux modèles ?
- Quelle est la différence entre `find()` et `findOne()` ?
- Comment utiliser `populate()` pour récupérer les données liées ?
- Comment structurer les sous-documents ?

## 🎉 Bonne chance !

N'oubliez pas de bien commenter votre code et de tester chaque fonctionnalité avant de passer à la suivante. La recherche et l'expérimentation font partie de l'apprentissage !
