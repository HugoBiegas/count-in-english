# Count in English

Site d'entraînement à la prononciation des nombres en anglais (nombres, années, heures, dates, décimaux, fractions, ordinaux, téléphones, argent).

🔗 **[Accéder à l'application](https://hugobiegas.github.io/count-in-english/)**

## Fonctionnalités

- **Mode flashcards** : un élément aléatoire s'affiche, tu le dis à voix haute, tu cliques pour révéler la réponse, puis « Suivant ».
- **Génération infinie et aléatoire** : tout est calculé côté client, aucune limite.
- **12 catégories** sélectionnables via le menu déroulant, plus un mode « Aléatoire » qui mélange tout.
- **Prononciation audio** via l'API Web Speech du navigateur (bouton 🔊).
- **Mode Cours** : tout le cours organisé en 14 sections avec sommaire latéral.
- **Raccourcis clavier** : `Espace` (révéler/suivant), `→` ou `Entrée` (suivant), `S` (écouter).

## Stack

HTML + CSS + JavaScript natifs. Aucune dépendance, aucun build, un seul fichier.

## Structure du code

- `generators` : objet contenant une fonction par catégorie. Chaque fonction retourne `{ display, answer, alt?, label, note?, displayStyle?, speech? }`.
- `numToWords(n)` : conversion d'un entier vers sa lecture anglaise (version UK avec `and`).
- `numToWordsUS(n)` : version américaine sans `and`.
- `ordinalWord(n)` / `ordinalSuffix(n)` : ordinaux en mots / avec suffixe.
- Logique UI séparée : flip de carte, navigation entre modes, scroll spy du sommaire.

Pour ajouter une catégorie : ajouter une fonction dans `generators`, et un `<option>` correspondant dans le `<select>`.