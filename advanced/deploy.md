# Deployment Deep Dive
< [back](../README.md)

---

## Hosting Your App

After building your React app with Vite, you need to host it on a web server or platform.

### Popular Hosting Providers

- **Netlify** — Easy setup with Git integration and custom domains
- **Vercel** — Optimized for frontend frameworks like React
- **GitHub Pages** — Free for static sites, good for small projects
- **Cloudflare Pages** — Fast global CDN for static sites

---

## Custom Domains

Most hosting providers let you connect your own domain:

1. Buy a domain from registrars like Namecheap or Google Domains.
2. Add DNS records (usually CNAME or A records) pointing to your hosting service.
3. Configure the domain in your hosting dashboard.

---

## Environment Variables

Use environment variables to store sensitive info or environment-specific settings (API keys, endpoints).

- Create `.env` files at the root of your project:

```bash
VITE_API_URL=https://api.example.com
VITE_ANALYTICS_KEY=abcd1234
````

* Access them in your React code with `import.meta.env.VITE_API_URL`

> **Note:** Vite requires env variables to start with `VITE_` to expose them to the client.

---

## Automating Deployment with GitHub Actions

Automate builds and deployment whenever you push code.

### Example workflow `.github/workflows/deploy.yml`:

```yaml
name: Deploy React App

on:
  push:
    branches:
      - main

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repo
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 18

      - name: Install dependencies
        run: npm install

      - name: Build project
        run: npm run build

      - name: Deploy to Netlify
        uses: netlify/actions/cli@master
        with:
          args: deploy --dir=dist --prod
        env:
          NETLIFY_AUTH_TOKEN: ${{ secrets.NETLIFY_AUTH_TOKEN }}
          NETLIFY_SITE_ID: ${{ secrets.NETLIFY_SITE_ID }}
```

> You’ll need to add `NETLIFY_AUTH_TOKEN` and `NETLIFY_SITE_ID` as [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets).

---

## Other CI/CD Tools

* **GitLab CI/CD**
* **CircleCI**
* **Travis CI**

Most work similarly: checkout code, install, build, then deploy.

---

## Tips for Production

* Always test your production build locally before deploying:

  ```bash
  npm run build
  npx serve dist
  ```
* Enable HTTPS on your domain for security.
* Use CDN caching for faster load times.

---

## Learn More

* [Netlify Docs](https://docs.netlify.com/)
* [Vercel Docs](https://vercel.com/docs)
* [GitHub Actions](https://docs.github.com/en/actions)
* [Vite Env Variables](https://vitejs.dev/guide/env-and-mode.html)