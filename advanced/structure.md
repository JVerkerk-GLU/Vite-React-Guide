# Project Structure

< [back](../README.md)

---

## Folder Structuring

A well-organized project structure helps you:

- Understand your codebase at a glance
- Separate concerns (logic, UI, assets, etc.)
- Scale and maintain code easily as your app grows

There’s no one “correct” structure, but here’s a proven starting point.

---

## Recommended Folder Structure

```
src/
├── assets/         # Images, fonts, and static files
├── components/     # Reusable UI components
├── pages/          # Route-based pages (if using React Router)
├── hooks/          # Custom React hooks
├── lib/            # Utilities and shared logic (e.g., API, date utils)
├── styles/         # Global or base CSS/SCSS files
├── context/        # React Context providers (if used)
├── App.tsx         # Root component
├── main.tsx        # App entry point
└── vite-env.d.ts   # Vite TypeScript definitions
...
```

## Learn More

🔗 [Bulletproof React](https://github.com/alan2207/bulletproof-react)
