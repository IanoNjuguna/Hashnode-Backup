---
title: "How to Migrate from Webpack to Turbopack"
seoTitle: "Migrating to Turbopack"
seoDescription: "Migrate from Webpack to Turbopack in NextJS 16 for improved build times and compatibility"
datePublished: Sun Jan 18 2026 15:18:28 GMT+0000 (Coordinated Universal Time)
cuid: cmkjvsfcg000102ju04b40zel
slug: how-to-migrate-from-webpack-to-turbopack
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/bEETIxP7iV8/upload/d97dc9cf2f72199e0174fa9b461581d5.jpeg
tags: webpack, bundler, cardano, turbopack, meshjs

---

Webpack and Turbopack are bundlers. A bundler is a tool that optimizes the browser’s performance by reducing the number of HTTP requests it makes. To make this possible, the bundler takes files in a web app and combines them into bundles.  
  
Since NextJS 16, Turbopack is the default bundler used for local development. While this *significantly speeds up build times*, there’s a conflict since your default `next.config.ts` lacks the `turbopack`config. The compiler raises this error because it is uncertain whether your app will break without the Webpack config being replicated in Turbopack.

For example:

```typescript
const nextConfig = {  
// NO TURBOPACK CONFIG
    webpack: (config: Configuration) => {
        config.experiments = {
          ...config.experiments,
          asyncWebAssembly: true,
          layers: true,
        };
}
```

### A Quick Fix

You will silence the error by having your Webpack experiments and an empty `turbopack` config:

```typescript
 const nextConfig = {
      experimental: {
        turbopack: {}, // SILENCE
      },
    webpack: (config) => {
      config.experiments = { asyncWebAssembly: true, layers: true };
      return config;
    },
};
```

An empty config works because Turbopack supports many standard Webpack features out of the box, and often doesn’t require an extra config for standard imports. You define aliases or loaders when needed.

### Force Webpack

Explicitly tell NextJS to use Webpack by running your dev server with a flag:

```bash
iano@iano$ next dev --webpack
```

Alternatively, you can update the `dev` script in your `package.json` file:

```json
"scripts": {
  "dev": "next dev --webpack"
}
```