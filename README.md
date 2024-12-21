# Todo App - Vue 3

Une application simple de gestion de tâches développée avec Vue 3.

---

## Fonctionnalités

- **Ajouter une tâche** : Ajoutez de nouvelles tâches via un champ texte et un bouton "Add".
- **Marquer une tâche comme terminée** : Cochez une tâche pour l'indiquer comme terminée.
- **Filtrer les tâches terminées** : Utilisez une checkbox avec le label `Masquer les tâches terminées` pour masquer les tâches déjà accomplies.
- **Tri automatique** : Les tâches non terminées sont affichées en haut de la liste.

---

## Prérequis

- **Node.js** : Version 14 ou supérieure.

---

## Installation

1. Clonez ce dépôt :

   ```bash
   git clone https://github.com/Amanda-Safoura/todo-app-vue3.git
   ```

2. Accédez au répertoire du projet :

   ```bash
   cd todo-app-vue3
   ```

3. Installez les dépendances :
   ```bash
   npm install
   ```

---

## Lancer l'application

Pour démarrer le serveur de développement :

```bash
npm run dev
```

Accédez à l'application dans votre navigateur à l'adresse suivante : [http://localhost:5173](http://localhost:5173).

---

## Fichier principal

Toute l'application est contenue dans un seul fichier : **`App.vue`**.  
Voici un résumé des parties principales :

- **Template** : Gère l'interface utilisateur (champ de saisie, liste des tâches, et checkbox de filtre).
- **Script** : Contient les fonctions suivantes :
  - `createNewTodo` : Ajout d'une nouvelle tâche.
  - `updateCompletedBool` : Modification de l'état terminé d'une tâche.
  - `sortTodoArr` : Trie la liste des tâches pour afficher les non terminées en premier.
- **Style** : Style minimal pour une présentation claire de la liste des tâches.

---

## Licence

Ce projet est sous licence **MIT**.  
Consultez le fichier `LICENSE` pour plus de détails.
