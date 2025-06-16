# Deployment Deep Dive
< [back](../README.md)

---

## Hosting your App

Na het bouwen van je React-app met Vite, moet je deze hosten op een webserver of platform.

### Populaire Hosting Providers

- **Netlify** — Makkelijk op te zetten met Git-integratie en eigen domeinen
- **Vercel** — Geoptimaliseerd voor frontend-frameworks zoals React
- **GitHub Pages** — Gratis voor statische sites, goed voor kleine projecten
- **Cloudflare Pages** — Supersnelle wereldwijde CDN voor statische sites

---

## Custom Domain

De meeste hostingproviders laten je een eigen domeinnaam koppelen:

1. Koop een domeinnaam via een registrar zoals Namecheap of Google Domains.
2. Voeg DNS-records toe (meestal CNAME of A-records) die wijzen naar je hostingplatform.
3. Stel je domeinnaam in via het dashboard van je hostingprovider.

---

## Environment Variables

Gebruik omgevingsvariabelen om gevoelige gegevens of omgevings-specifieke instellingen op te slaan (zoals API-sleutels).

- Maak `.env`-bestanden aan in de hoofdmap van je project:

```bash
VITE_API_URL=https://api.example.com
VITE_ANALYTICS_KEY=abcd1234
````

* Toegang in je React-code via: `import.meta.env.VITE_API_URL`

> **Let op:** Vite vereist dat variabelen beginnen met `VITE_` om ze beschikbaar te maken aan de frontend.

---

## Deployment with GitHub Actions

Laat je app automatisch bouwen en deployen telkens als je code pusht.

### Example `.github/workflows/deploy.yml`:

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

> Je moet `NETLIFY_AUTH_TOKEN` en `NETLIFY_SITE_ID` toevoegen als [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets).

---

## Other CI/CD Tools

* **GitLab CI/CD**
* **CircleCI**
* **Travis CI**

De werking is meestal hetzelfde: code ophalen, dependencies installeren, bouwen, en deployen.

---

## Tips voor Productie

* Test altijd je productie-build lokaal vóór je die publiceert:

  ```bash
  npm run build
  npx serve dist
  ```

* Zet HTTPS aan voor je domein voor extra veiligheid.

* Gebruik CDN-caching voor snellere laadtijden.

---

## Learn More

* 🔗 [Netlify Documentatie](https://docs.netlify.com/)
* 🔗 [Vercel Documentatie](https://vercel.com/docs)
* 🔗 [GitHub Actions](https://docs.github.com/en/actions)
* 🔗 [Vite Omgevingsvariabelen](https://vitejs.dev/guide/env-and-mode.html)