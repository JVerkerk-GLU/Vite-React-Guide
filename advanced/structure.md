# Project Structure

< [back](../README.md)

---

## Folder Structuring

Een goed georganiseerde projectstructuur helpt je:

- Je codebase in één oogopslag te begrijpen
- Verantwoordelijkheden te scheiden (logica, UI, assets, enz.)
- Je code eenvoudig op te schalen en te onderhouden naarmate je app groeit

Er is niet één “juiste” structuur, maar hieronder zie je een bewezen startpunt.

---

## Recommended Folder Structure

```

src/
├── assets/         # Afbeeldingen, lettertypes en statische bestanden
├── components/     # Herbruikbare UI-componenten
├── pages/          # Pagina’s gekoppeld aan routes (bij gebruik van React Router)
├── hooks/          # Aangepaste React hooks
├── lib/            # Hulpmiddelen en gedeelde logica (zoals API’s, datums, enz.)
├── styles/         # Globale of basale CSS/SCSS-bestanden
├── context/        # React Context providers (indien gebruikt)
├── App.tsx         # Rootcomponent
├── main.tsx        # Startpunt van de app
└── vite-env.d.ts   # Vite TypeScript-definities
...

```

## Learn More

* 🔗 [Bulletproof React](https://github.com/alan2207/bulletproof-react)