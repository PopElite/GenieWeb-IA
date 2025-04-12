# Déploiement de GenieWeb AI

Ce document contient les instructions pour déployer l'application GenieWeb AI sur différentes plateformes.

## Prérequis

- Compte GitHub pour héberger le code source
- Compte sur une plateforme de déploiement (Vercel, Netlify, etc.)
- Clé API OpenAI valide pour l'environnement de production

## Options de déploiement

### 1. Déploiement sur Vercel (Recommandé)

Vercel est parfaitement adapté pour les applications Next.js et offre un déploiement simple et rapide.

1. Créez un compte sur [Vercel](https://vercel.com) si vous n'en avez pas déjà un
2. Connectez votre compte GitHub à Vercel
3. Importez votre projet depuis GitHub
4. Configurez les variables d'environnement:
   - `NEXT_PUBLIC_OPENAI_API_KEY`: Votre clé API OpenAI
5. Déployez l'application

### 2. Déploiement sur Netlify

1. Créez un compte sur [Netlify](https://netlify.com) si vous n'en avez pas déjà un
2. Connectez votre compte GitHub à Netlify
3. Importez votre projet depuis GitHub
4. Configurez les paramètres de build:
   - Build command: `npm run build`
   - Publish directory: `.next`
5. Configurez les variables d'environnement:
   - `NEXT_PUBLIC_OPENAI_API_KEY`: Votre clé API OpenAI
6. Déployez l'application

### 3. Déploiement sur un serveur personnalisé

1. Construisez l'application:
   ```bash
   npm run build
   ```
2. Démarrez le serveur:
   ```bash
   npm start
   ```

## Configuration des variables d'environnement

Pour que l'application fonctionne correctement en production, vous devez configurer les variables d'environnement suivantes:

```
NEXT_PUBLIC_OPENAI_API_KEY=votre_clé_api_openai
```

## Domaine personnalisé

Une fois l'application déployée, vous pouvez configurer un domaine personnalisé dans les paramètres de votre plateforme de déploiement.

## Surveillance et maintenance

- Configurez des alertes pour surveiller les performances de l'application
- Mettez régulièrement à jour les dépendances pour maintenir la sécurité
- Surveillez l'utilisation de l'API OpenAI pour gérer les coûts
