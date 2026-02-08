# NAHLA

**Nahla** est une application mobile de gestion du temps d'ecran gamifiee pour les familles. Elle transforme les negociations en un systeme clair: les enfants gagnent des Coins en accomplissant leurs taches, puis depensent ces Coins pour acheter du temps de jeu.

> Ce depot est volontairement minimal: il sert de vitrine produit. Le code source reste prive.

---

**Le probleme**

Les parents passent un temps enorme a negocier et repeter les memes consignes. Les enfants percoivent les limites d'ecran comme un blocage injuste. Le resultat: tension quotidienne, perte de temps, et peu d'apprentissage de l'autonomie.

**La solution**

Nahla remplace la contrainte par un contrat simple et visible.

- Les taches du quotidien rapportent des Coins.
- Le temps d'ecran a un cout en Coins.
- Chaque enfant a son profil, son solde, et ses regles.
- Les parents valident en quelques secondes.

---

**Ce qui rend Nahla speciale**

- Responsabilisation vs blocage: l'enfant "achete" son temps.
- Simplicite parentale: validation en 30 secondes.
- Gamification masquee: des Coins, pas des minutes.
- Multi-enfants equitable: chacun son profil et ses regles.
- Concue par un utilisateur: un parent qui vit le probleme.

---

**Fonctionnalites cle**

- Profils enfants avec soldes en temps reel.
- Catalogue de taches et malus, predefinis et personnalisables.
- Recurrence et coefficients pour equilibrer effort et recompense.
- Timer de jeu avec alertes (5 min, 1 min) et fin claire.
- Limites journaliere et conversion Coins -> minutes.
- Synchronisation multi-device entre parents.

---

**MVP (perimetre)**

- Gestion des enfants: profils, soldes, plafonds, coins negatifs.
- Systeme de taches: recurrence, coefficients, validation rapide.
- Systeme de malus: retrait de Coins, possible negatif.
- Timer de jeu: cout avant validation, notifications locales, pas de pause.
- Configuration famille: compte partage, sync temps reel.

---

**Objectifs d'impact**

- Diminuer fortement les repetitions parentales.
- Reduire le temps perdu en negociations.
- Ameliorer l'initiative des enfants.
- Maintenir un equilibre de Coins (ni trop, ni trop peu).

---

**Architecture et stack**

- Mobile: React Native.
- Backend: NestJS.
- Base de donnees: PostgreSQL.
- Infra: Docker.
- Architecture: DDD / Hexagonale.
- Methode: TDD.

---

**Mon role**

Projet concu et developpe par un parent developpeur, avec une approche produit tres terrain: partir d'un probleme vecu, prototyper vite, puis stabiliser l'usage au quotidien.

---

**Statut**

MVP en cours d'evolution, teste en situation familiale reelle. Les iterations priorisent la stabilite, la simplicite, et l'impact comportemental.

---

**Confidentialite**

Ce repo ne contient pas de code ni de donnees sensibles. Il permet de presenter la vision, la logique produit et la trajectoire du projet sans exposer l'implementation.

---

**Contact**

Si vous souhaitez une demo ou des details techniques, je peux les partager sur demande.
