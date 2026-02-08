# NAHLA

**Nahla** est une application mobile de gestion du temps d’écran gamifiée pour les familles. Elle transforme les négociations en un système clair : les enfants gagnent des Coins en accomplissant leurs tâches, puis dépensent ces Coins pour acheter du temps de jeu.

> Ce dépôt est volontairement minimal : il sert de vitrine produit. Le code source reste privé.

---

**Le problème**

Les parents passent un temps énorme à négocier et répéter les mêmes consignes. Les enfants perçoivent les limites d’écran comme un blocage injuste. Le résultat : tension quotidienne, perte de temps, et peu d’apprentissage de l’autonomie.

**La solution**

Nahla remplace la contrainte par un contrat simple et visible.

- Les tâches du quotidien rapportent des Coins.
- Le temps d’écran a un coût en Coins.
- Chaque enfant a son profil, son solde, et ses règles.
- Les parents valident en quelques secondes.

---

**Ce qui rend Nahla spéciale**

- Responsabilisation vs blocage : l’enfant “achète” son temps.
- Simplicité parentale : validation en 30 secondes.
- Gamification masquée : des Coins, pas des minutes.
- Multi-enfants équitable : chacun son profil et ses règles.
- Conçue par un utilisateur : un parent qui vit le problème.

---

**Fonctionnalités clés**

- Profils enfants avec soldes en temps réel.
- Catalogue de tâches et malus, prédéfinis et personnalisables.
- Récurrence et coefficients pour équilibrer effort et récompense.
- Timer de jeu avec alertes (5 min, 1 min) et fin claire.
- Limites journalières et conversion Coins -> minutes.
- Synchronisation multi-device entre parents.

---

**MVP (périmètre)**

- Gestion des enfants : profils, soldes, plafonds, coins négatifs.
- Système de tâches : récurrence, coefficients, validation rapide.
- Système de malus : retrait de Coins, possible négatif.
- Timer de jeu : coût avant validation, notifications locales, pas de pause.
- Configuration famille : compte partagé, sync temps réel.

---

**Objectifs d’impact**

- Diminuer fortement les répétitions parentales.
- Réduire le temps perdu en négociations.
- Améliorer l’initiative des enfants.
- Maintenir un équilibre de Coins (ni trop, ni trop peu).

---

**Architecture et stack**

- Mobile : React Native.
- Backend : NestJS.
- Base de données : PostgreSQL.
- Infra : Docker.
- Architecture : DDD / Hexagonale.
- Méthode : TDD.

---

**Structure du monorepo (détaillée)**

```text
.
├── nahla-api/                         # Backend NestJS (DDD/Hexa)
│   ├── src/
│   │   ├── modules/
│   │   │   ├── auth/
│   │   │   │   ├── application/
│   │   │   │   ├── domain/
│   │   │   │   ├── infrastructure/
│   │   │   │   └── interfaces/
│   │   │   ├── child/                 # Enfants
│   │   │   ├── family/                # Famille/compte partagé
│   │   │   ├── task/                  # Tâches
│   │   │   ├── malus/                 # Malus
│   │   │   ├── timer/                 # Sessions de jeu
│   │   │   ├── settings/              # Paramètres
│   │   │   └── realtime/              # Sync temps réel (WebSocket)
│   │   └── shared/
│   │       ├── events/
│   │       ├── infrastructure/
│   │       ├── presentation/
│   │       └── services/
│   ├── test/                           # Tests e2e
│   └── coverage/                       # Rapport de couverture Jest
│
├── nahla-mobile/                       # App mobile (Expo + React Native)
│   ├── app/                            # Routing Expo Router
│   │   ├── (auth)/
│   │   └── (app)/
│   ├── src/
│   │   ├── components/
│   │   │   ├── child/
│   │   │   ├── task/
│   │   │   ├── timer/
│   │   │   └── ui/
│   │   ├── constants/                  # Design system
│   │   ├── contexts/
│   │   ├── hooks/
│   │   ├── schemas/                    # Validation Zod
│   │   ├── services/
│   │   │   ├── api/
│   │   │   ├── auth/
│   │   │   ├── notifications/
│   │   │   ├── storage/
│   │   │   └── websocket/
│   │   ├── stores/                     # State management (Zustand)
│   │   ├── types/
│   │   └── utils/
│   ├── assets/
│   └── coverage/                       # Rapport de couverture Jest
│
└── nahla-postgres/                      # Base PostgreSQL (Docker)
```

---

**Backend (Nahla API)**

- Architecture DDD/Hexa par module : `domain` (entités, value objects), `application` (use cases), `infrastructure` (persistence, adapters), `interfaces` (HTTP/WS).
- Bounded contexts isolés par feature (auth, enfants, tâches, malus, timer, settings, realtime).
- WebSocket pour la synchronisation multi-parents en temps réel.
- Migrations et seeds TypeORM.

---

**Mobile (Nahla App)**

- Expo Router pour la navigation.
- Design system interne (thème, tokens, spacing).
- State management avec Zustand + data fetching avec React Query.
- Validation des formulaires via Zod.
- Notifications locales (timer).

---

**Tests et qualité**

- Backend : Jest (unit + integration), e2e sous `test/`, couverture générée dans `nahla-api/coverage/`.
- Mobile : Jest + Testing Library, couverture dans `nahla-mobile/coverage/`.
- Lint, format, typecheck dans chaque app.

---

**Mon rôle**

Projet conçu et développé par un parent développeur, avec une approche produit très terrain : partir d’un problème vécu, prototyper vite, puis stabiliser l’usage au quotidien.

---

**Statut**

MVP en cours d’évolution, testé en situation familiale réelle. Les itérations priorisent la stabilité, la simplicité, et l’impact comportemental.

---

**Confidentialité**

Ce repo ne contient pas de code ni de données sensibles. Il permet de présenter la vision, la logique produit et la trajectoire du projet sans exposer l’implémentation.

---

**Contact**

Si vous souhaitez une démo ou des détails techniques, je peux les partager sur demande.
