# Building & Deploying with Vite
< [back](../README.md)

## What Does "Build" Mean?

Als je je project bouwt, maak je een **definitieve, geoptimaliseerde versie** die online gezet kan worden.

Deze versie is sneller, kleiner en klaar voor gebruikers.

---

## Step 1: Build the Project

Voer in je terminal het volgende uit:

```bash
npm run build
````

Dit maakt een nieuwe map `dist/` aan — deze bevat je hele site, klaar om gedeployed te worden.

---

## Step 2: Preview the Build (Optional)

Wil je de build lokaal testen voordat je het deployt? Voer dan uit:

```bash
npm run preview
```

Bezoek daarna de link die getoond wordt (meestal `http://localhost:4173`) om de definitieve site te bekijken.

---

## Step 3: Deploy Your Site

Er zijn veel gratis en makkelijke manieren om je project te hosten. Hier zijn een paar populaire opties:

### 🔹 GitHub Pages

1. Push je project naar GitHub
2. Gebruik een tool zoals [vite-plugin-gh-pages](https://www.npmjs.com/package/vite-plugin-gh-pages)
3. Of upload handmatig de `dist/` map naar een `gh-pages` branch

### 🔹 Netlify (Heel makkelijk)

1. Ga naar [Netlify](https://netlify.com)
2. Sleep je `dist/` map in het Netlify dashboard
3. Of verbind je GitHub repo en laat het automatisch deployen

### 🔹 Vercel (Geweldig voor React)

1. Ga naar [Vercel](https://vercel.com)
2. Importeer je GitHub repo
3. Vercel detecteert automatisch je Vite + React project en regelt de rest

---

## Common Build Issues

* **Broken Paths?** → Probeer `base` in `vite.config.ts` in te stellen als je naar een submap deployed:

```ts
export default defineConfig({
  base: "/your-repo-name/",
  // andere config...
})
```

* **Missing Environment Variables?** → Zorg dat `.env` bestanden erbij zitten als dat nodig is.

---

## Learn More

* 🔗 [Vite Build Docs](https://vitejs.dev/guide/build.html)
* 🔗 [Deploy React Apps](https://create-react-app.dev/docs/deployment/)