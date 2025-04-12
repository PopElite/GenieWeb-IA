# Optimisations pour le déploiement

Ce fichier contient des configurations et optimisations supplémentaires pour améliorer les performances de l'application GenieWeb AI lors du déploiement.

## Configuration next.config.js

```js
/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
  swcMinify: true,
  images: {
    domains: ['images.unsplash.com'],
    formats: ['image/avif', 'image/webp'],
  },
  experimental: {
    optimizeCss: true,
    scrollRestoration: true,
  },
  compiler: {
    removeConsole: process.env.NODE_ENV === 'production',
  },
}

module.exports = nextConfig
```

## Optimisations supplémentaires

### 1. Compression des images

Assurez-vous que toutes les images sont optimisées avant le déploiement. Vous pouvez utiliser des outils comme:
- [TinyPNG](https://tinypng.com/)
- [Squoosh](https://squoosh.app/)

### 2. Lazy loading des modules

Utilisez l'importation dynamique pour les composants lourds:

```jsx
import dynamic from 'next/dynamic'

const DynamicComponent = dynamic(() => import('../components/HeavyComponent'), {
  loading: () => <p>Chargement...</p>,
})
```

### 3. Mise en cache

Configurez les en-têtes de cache pour les ressources statiques:

```js
// next.config.js
module.exports = {
  async headers() {
    return [
      {
        source: '/static/:path*',
        headers: [
          {
            key: 'Cache-Control',
            value: 'public, max-age=31536000, immutable',
          },
        ],
      },
    ]
  },
}
```

### 4. Préchargement des pages

Utilisez `next/link` avec `prefetch` pour précharger les pages:

```jsx
import Link from 'next/link'

<Link href="/dashboard" prefetch>
  Dashboard
</Link>
```

### 5. Analyse des performances

Après le déploiement, utilisez ces outils pour analyser les performances:
- [Lighthouse](https://developers.google.com/web/tools/lighthouse)
- [WebPageTest](https://www.webpagetest.org/)
- [PageSpeed Insights](https://pagespeed.web.dev/)

## Surveillance en production

### 1. Sentry pour le suivi des erreurs

```bash
npm install @sentry/nextjs
```

### 2. Google Analytics pour le suivi des utilisateurs

```jsx
// pages/_app.js
import Script from 'next/script'

<Script
  strategy="afterInteractive"
  src={`https://www.googletagmanager.com/gtag/js?id=${GA_TRACKING_ID}`}
/>
```

## Mise à l'échelle

Si votre application connaît une croissance rapide, envisagez:
- Mise en cache avec Redis
- CDN pour les ressources statiques
- Serveurs régionaux pour réduire la latence
