# Installing Packages
< [back](../README.md)

## What Are Packages?

Packages are **reusable pieces of code** made by other developers that you can add to your project.

They help you save time and avoid reinventing the wheel — for example, you can install a package for animations, icons, routing, or UI components.

We use a tool called **npm** (Node Package Manager) to install packages.

---

## Install Packages

To install a package, open your terminal and type:

```bash
npm install <package-name>
```

### Example

```bash
npm install react-icons
```

This adds the package to your project so you can use it in your code.

---

## Using an Installed Package

After installing, you usually import the package at the top of your `.tsx` file.

Example using `react-icons`:

```tsx
import { FaBeer } from 'react-icons/fa';

function App() {
  return <h1>Cheers! <FaBeer /></h1>;
}
```

---

## Dev Packages

Some packages are only needed during development (like formatting or testing tools). For those, use `-D`:

```bash
npm install -D prettier
```

These won't be included in the final production build.

---

## Remove a Package

If you installed something by mistake or no longer need it:

```bash
npm uninstall <package-name>
```

---

## Updating Packages

You can check for outdated packages using:

```bash
npm outdated
```

To update everything that can be safely upgraded:

```bash
npm update
```

---

## Useful Package Examples

- **UI Libraries**: [Tailwind CSS](https://tailwindcss.com/), [Radix UI](https://www.radix-ui.com/), [Material UI](https://mui.com/)
- **Routing**: [React Router](https://reactrouter.com/)
- **State Management**: [Zustand](https://zustand-demo.pmnd.rs/), [Redux](https://redux.js.org/), [Jotai](https://jotai.org/)
- **Development Tools**: [ESLint](https://eslint.org/), [Prettier](https://prettier.io/)
- **Testing**: [Vitest](https://vitest.dev/), [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)

---

## Learn More

🔗 [npm Docs](https://docs.npmjs.com/)  
🔗 [React Awesome Packages](https://reactjsexample.com/)
