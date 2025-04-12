# GenieWeb AI - Documentation

## Vue d'ensemble

GenieWeb AI est une plateforme qui utilise l'intelligence artificielle pour simplifier et booster la vie digitale des créateurs, freelancers et entrepreneurs. Cette application offre des outils propulsés par l'IA pour créer du contenu impactant, automatiser la productivité, générer des idées de revenus et faciliter l'apprentissage.

## Structure du projet

Le projet est structuré comme suit:

```
genieweb-ai/
├── src/
│   ├── app/                    # Routes de l'application (Next.js App Router)
│   ├── components/             # Composants UI réutilisables
│   ├── hooks/                  # Hooks personnalisés
│   ├── layouts/                # Layouts de pages
│   ├── modules/                # Modules IA principaux
│   ├── services/               # Services d'API et utilitaires
│   └── styles/                 # Styles globaux
├── public/                     # Fichiers statiques
├── .env.local                  # Variables d'environnement locales
└── tailwind.config.js          # Configuration de TailwindCSS
```

## Technologies utilisées

- **Frontend**: Next.js avec TypeScript et TailwindCSS
- **Backend**: API Routes de Next.js
- **IA**: Intégration avec l'API OpenAI
- **Authentification**: Système d'authentification personnalisé (simulé pour le MVP)
- **Styles**: TailwindCSS avec design system personnalisé

## Modules IA

### 1. Générateur de posts pour réseaux sociaux

Ce module permet de générer des posts professionnels pour différentes plateformes (LinkedIn, Twitter, Facebook, Instagram) avec différents objectifs (engagement, conversion, autorité).

### 2. Générateur d'idées de microservices

Ce module aide à générer des idées de microservices rentables dans différentes niches (freelance, e-commerce, SaaS, coaching, contenu) avec des propositions de valeur et des modèles de tarification.

### 3. Résumeur de contenu

Ce module permet de résumer du texte ou du contenu provenant d'une URL (articles, documents, vidéos YouTube) en différents formats (concis, détaillé, points clés).

## Composants UI

L'application utilise une bibliothèque de composants UI personnalisés qui respectent le design system:

- **Couleurs**: Primaire (bleu nuit #1e1b4b), Accent (orange néon #ff6b00), Soft (gris clair #f4f4f5)
- **Typographie**: Police Inter pour une lisibilité optimale
- **Composants**: Sidebar, Card, Button, Input, Textarea, Loader, Alert, Toggle, Tabs, CopyButton, ResultCard, ThemeToggle

## Responsive Design

L'application est conçue avec une approche mobile-first et s'adapte à différentes tailles d'écran:
- Mobile: < 640px
- Tablette: 640px - 1023px
- Desktop: ≥ 1024px

Une page de test responsive est disponible à `/dashboard/responsive-test` pour vérifier le comportement sur différents appareils.

## Performance

Plusieurs optimisations de performance ont été implémentées:
- Hooks personnalisés pour le debouncing et l'intersection observer
- Optimisations CSS pour le rendu
- Lazy loading des composants lourds
- Styles optimisés pour les appareils mobiles

## Déploiement

Voir le fichier `DEPLOYMENT.md` pour les instructions détaillées sur le déploiement de l'application.

## Variables d'environnement

- `NEXT_PUBLIC_OPENAI_API_KEY`: Clé API OpenAI (requise pour les fonctionnalités d'IA)

## Développement futur

Fonctionnalités potentielles pour les versions futures:
- Intégration avec d'autres modèles d'IA (Claude, Gemini)
- Système d'authentification complet avec Firebase ou Clerk
- Fonctionnalités premium avec paiement via Stripe
- Historique des générations avec sauvegarde dans une base de données
- Intégration directe avec les réseaux sociaux pour la publication
