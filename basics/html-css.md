# HTML & CSS Guide
< [back](../README.md)

## Introduction

Deze gids helpt je op weg met het schrijven van semantische HTML en het stijlen van je applicatie met CSS.
Hoewel een volledige beschrijving van alle HTML en CSS buiten de scope van deze repository valt, kun je voor meer uitleg terecht op online tutorials zoals [W3Schools](https://www.w3schools.com/).

---

## HTML

HTML staat voor **HyperText Markup Language**. Het is de basisstructuur van een webpagina. Het vertelt de browser wat er getoond moet worden — zoals tekst, afbeeldingen, knoppen en meer.

Een HTML-bestand bestaat uit **elementen** — elk element is als een bouwsteen van je pagina.

### HTML Basics

- Gebruik tags zoals `<header>`, `<main>`, `<section>`, en `<footer>` om je pagina te organiseren.
- Dit zijn semantische tags — ze helpen om de betekenis van de inhoud te verduidelijken.

### HTML Example

```html
<header class="site-header">
    <h1>My Web App</h1>
</header>
````

* `<header>` en `<h1>` zijn elementen.
* De tekst binnen `Hello World` is wat je op de pagina ziet.
* Elementen komen vaak in paren: een openingstag `<h1>` en een sluitingstag `</h1>`.
* Het stukje `class="site-header"` zorgt ervoor dat we er met CSS een stijl aan kunnen geven.

---

## CSS

CSS staat voor **Cascading Style Sheets**. Het bepaalt hoe je webpagina eruitziet — zoals kleuren, marges, lettertypes en layout.

CSS wordt vaak geschreven in een apart bestand met een `.css` extensie.

Je kunt je componenten stijlen met gewone CSS, CSS Modules of utility-first frameworks zoals [Tailwind](https://tailwindcss.com/).

### CSS Basics

Je kunt op verschillende manieren stijlen toevoegen aan je webpagina:

* Globale CSS: in bestanden zoals `src/index.css` of `App.css`
* Component CSS: specifiek voor een component (zoals `Button.module.css`)
* Utility Libraries: zoals Tailwind CSS, dat vooraf gemaakte klassen aanbiedt

### CSS Example

```css
h1 {
    color: blue;
}
```

### Adding New CSS

1. Maak een nieuw bestand aan, bijvoorbeeld `style.css`
2. Voeg wat CSS-code toe:

```css
.site-header {
  background-color: #f0f0f0;
  padding: 1rem;
}
```

3. Importeer het CSS-bestand bovenaan je componentbestand (zoals `App.tsx`):

```tsx
import './style.css';
```

Nu zal elk element met `class="site-header"` deze stijl gebruiken.

---

## Learn More

Deze gids geeft je de basis, maar je kunt meer leren via:

* 🔗 [w3schools HTML Tutorial](https://www.w3schools.com/html)
* 🔗 [w3schools CSS Tutorial](https://www.w3schools.com/css)
