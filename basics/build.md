# Building & Deploying with Vite
< [back](../README.md)

## What Does "Build" Mean?

When you build your project, you're creating a **final, optimized version** that can be uploaded to the internet.

This version is faster, smaller, and ready for users.

---

## Step 1: Build the Project

In your terminal, run:

```bash
npm run build
```

This creates a new folder called `dist/` — it contains your entire site, ready to be deployed.

---

## Step 2: Preview the Build (Optional)

Want to test the build locally before deploying? Run:

```bash
npm run preview
```

Then visit the link it shows (usually `http://localhost:4173`) to preview the final site.

---

## Step 3: Deploy Your Site

There are many free and easy ways to host your project. Here are some popular options:

### 🔹 GitHub Pages

1. Push your project to GitHub
2. Use a tool like [vite-plugin-gh-pages](https://www.npmjs.com/package/vite-plugin-gh-pages)
3. Or manually upload the `dist/` folder to a `gh-pages` branch

### 🔹 Netlify (Very Easy)

1. Go to [Netlify](https://netlify.com)
2. Drag your `dist/` folder into the Netlify dashboard
3. Or connect your GitHub repo and let it auto-deploy

### 🔹 Vercel (Great for React)

1. Go to [Vercel](https://vercel.com)
2. Import your GitHub repo
3. Vercel will auto-detect your Vite + React project and handle everything

---

## Common Build Issues

- **Broken Paths?** → Try setting `base` in `vite.config.ts` if you’re deploying to a subfolder:

```ts
export default defineConfig({
  base: "/your-repo-name/",
  // other config...
})
```

- **Missing Environment Variables?** → Make sure `.env` files are included if needed.

---

## Learn More

🔗 [Vite Build Docs](https://vitejs.dev/guide/build.html)  
🔗 [Deploy React Apps](https://create-react-app.dev/docs/deployment/)
