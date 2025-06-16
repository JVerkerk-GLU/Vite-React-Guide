# Project Setup Guide

< [back](../README.md)

---

## Prerequisites

Before you start, make sure you have these installed:

* [Node.js](https://nodejs.org/en) (JavaScript runtime)
* Git (version control)
* A code editor, such as:

    * [Visual Studio Code](https://code.visualstudio.com/)
    * [WebStorm](https://www.jetbrains.com/webstorm/)

---

## Creating a New Vite + React Project

Open your terminal and follow these steps:

1. Navigate to or create an empty folder for your project.

2. Open this folder in your editor (VSCode or WebStorm).

3. Open the terminal inside the editor.

4. Run the Vite project creation command:

   ```bash
   npm create vite@latest
   ```

5. A setup wizard will appear:

    * Use a single dot `.` for the project name (to use the current folder)
    * If it asks to overwrite existing files, choose **Ignore**
    * Choose a package name (or leave it blank)
    * Select **React** as the framework
    * Select **TypeScript** as the variant

6. When the wizard finishes, install the dependencies:

   ```bash
   npm install
   ```

7. Start the development server:

   ```bash
   npm run dev
   ```

---

## Result

If everything worked, Vite will launch your new React app at:

```
http://localhost:5173
```

You should see a page like this:

<img src="setup-example.png" alt="Vite Example Page">

---

## 🔗 Learn More

* [Vite Documentation](https://vitejs.dev/)
* [React Documentation](https://reactjs.org/)