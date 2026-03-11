# React Project Structure & Components

## 🚀 Continuing My React Learning

In this lecture I explored **how React actually connects with HTML** and how React projects are structured internally.

The instructor compared **two React setups**:

* Create React App (CRA)
* Vite

The goal was to understand **how React code gets injected into HTML** and how React applications actually run.

---

# Core Idea: How React Connects to HTML

A very important rule was discussed:

> JavaScript cannot manipulate HTML unless it is loaded inside an HTML file using a `<script>` tag.

This is a fundamental rule of web development.

React follows the same rule, but it **automates the script injection process behind the scenes**.

---

# Create React App (CRA) Project Structure

A typical CRA project contains several folders and files.

## node_modules

This folder contains **all installed dependencies**.

Examples:

* React
* ReactDOM
* Other supporting libraries

Important notes:

* This folder is **not pushed to GitHub**
* It can be recreated using:

```bash
npm install
```

---

## package-lock.json

This file **locks dependency versions** so that the same versions install on every machine.

This prevents unexpected behavior caused by version changes.

---

## .gitignore

This file tells Git **which files should not be pushed to GitHub**.

Common ignored items include:

```
node_modules
build
.env
```

---

## README.md

This file usually contains **project documentation**.

It explains:

* What the project is
* How to run it
* Any important notes

---

# The public Folder

The `public` folder contains static files.

Examples:

* favicon
* icons
* manifest.json
* robots.txt

### Important File: index.html

This is the **only HTML file** in a React application.

That is why React apps are called **Single Page Applications (SPA)**.

Inside `index.html`, we usually see:

```html
<div id="root"></div>
```

This div is where the **entire React application gets rendered**.

Another tag present is:

```html
<noscript>You need to enable JavaScript to run this app.</noscript>
```

This message appears if JavaScript is disabled in the browser.

---

# The src Folder

Most of the actual application code lives in the `src` folder.

Important files include:

### index.js

This is the **entry point of the React application**.

It is responsible for connecting React with the HTML file.

---

### App.js

This is the **root component** of the application.

All other components are usually nested inside it.

---

# How React Injects Content into HTML

Inside `index.js`, React connects to the root div.

Example code:

```javascript
import React from "react"
import ReactDOM from "react-dom/client"

const root = ReactDOM.createRoot(document.getElementById("root"))
root.render(<App />)
```

### Understanding This Code

**react**

The core React library.
It contains the fundamental logic behind React.

---

**react-dom**

This library connects React to the **browser DOM**.

Think of it like:

* `react-dom` → Web
* `react-native` → Mobile

---

**createRoot()**

This creates a **React root inside the DOM element** with id `"root"`.

---

**render()**

This renders the React component tree inside that root element.

So essentially:

```
React Component Tree → Injected into HTML div with id="root"
```

Important note:

The `root` id **can be anything**, as long as it matches in both HTML and JavaScript.

---

# Automatic Script Injection in CRA

In CRA projects, we never manually add script tags.

Instead, **React Scripts automatically inject compiled JavaScript bundles into the HTML file**.

If we inspect the page source, we will see `<script>` tags that were never manually written.

These are generated during build or development.

---

# Understanding the Virtual DOM

React does not directly manipulate the real DOM every time something changes.

Instead it uses something called **Virtual DOM**.

### Real DOM

The browser maintains a **tree structure of HTML elements**.

Updating the real DOM is relatively expensive.

---

### Virtual DOM

React creates a **lightweight copy of the DOM in memory**.

When something changes:

1. React updates the Virtual DOM
2. Compares it with the previous Virtual DOM
3. Finds the differences
4. Updates only the changed elements in the real DOM

This process makes React applications **fast and efficient**.

---

# Vite Project Structure

Vite is a more modern tool for building React projects.

One major difference is the placement of `index.html`.

### Key Difference

In Vite:

```
index.html
```

is placed in the **root directory**, not inside the public folder.

---

# Script Loading in Vite

Unlike CRA, Vite does not hide script loading.

Inside `index.html`, we see:

```html
<script type="module" src="/src/main.jsx"></script>
```

This script directly loads the main React entry file.

So Vite's setup is **more transparent and lightweight**.

---

# main.jsx in Vite

Example code:

```javascript
import ReactDOM from "react-dom/client"
import App from "./App.jsx"

ReactDOM.createRoot(document.getElementById("root")).render(<App />)
```

This is similar to CRA's `index.js`.

The difference is mainly **simpler syntax and file naming**.

---

# CRA vs Vite Comparison

| Feature             | CRA                         | Vite              |
| ------------------- | --------------------------- | ----------------- |
| Script Injection    | Automatic via React Scripts | Direct script tag |
| Entry File          | index.js                    | main.jsx          |
| Project Size        | Heavier                     | Lighter           |
| Setup Speed         | Slower                      | Faster            |
| Core React Concepts | Same                        | Same              |

The main takeaway:

> CRA and Vite differ mainly in tooling, not in React fundamentals.

---

# Creating My First Custom Component

The instructor demonstrated creating a new component.

File created:

```
chai.jsx
```

Inside the `src` folder.

Example component:

```jsx
function Chai() {
  return (
    <h2>Chai aur React</h2>
  )
}

export default Chai
```

Then imported inside `App.jsx`:

```jsx
import Chai from "./chai"

function App() {
  return (
    <Chai />
  )
}
```

This is how React applications are built using **multiple reusable components**.

---

# Common Errors Encountered

## File Extension Issue

Vite expects component files to use:

```
.jsx
```

instead of `.js`.

CRA is more flexible and allows `.js`.

---

## Component Naming Rule

React components **must start with a capital letter**.

Correct:

```jsx
<Chai />
```

Incorrect:

```jsx
<chai />
```

If the name starts with lowercase, React assumes it is an **HTML tag**, not a component.

---

# JSX Rule: Only One Root Element

A React component must return **only one root element**.

Incorrect example:

```jsx
return (
  <h1>Hello</h1>
  <p>Paragraph</p>
)
```

Correct approach using a wrapper:

```jsx
return (
  <div>
    <h1>Hello</h1>
    <p>Paragraph</p>
  </div>
)
```

Better approach using **Fragment**:

```jsx
return (
  <>
    <h1>Hello</h1>
    <p>Paragraph</p>
  </>
)
```

Fragments allow multiple elements without adding extra DOM nodes.

---

# Best Practices for React Components

1. Component names should use **PascalCase** (capitalized)
2. File names should also be **capitalized**
3. Use `.jsx` when returning JSX
4. Use `.js` for plain JavaScript logic
5. Always export components

Example:

```javascript
export default ComponentName
```

6. Always import components before using them

---

# Why React Apps Are Called Single Page Applications

React applications contain only **one HTML file**.

```
index.html
```

Instead of loading new pages, React:

* Updates the DOM dynamically
* Changes components based on routes

This creates the **illusion of multiple pages**, but technically everything runs inside **one page**.

---

# What I Will Learn Next

Upcoming topics include:

* JSX in detail
* Building small projects
* Understanding Virtual DOM practically
* State and state management
* Props and component communication

The learning approach will continue to be **project-based**.

---

# My Key Takeaways

* JavaScript must always be injected into HTML using a `<script>` tag
* CRA automatically injects scripts using React Scripts
* Vite loads scripts directly in `index.html`
* `index.js` or `main.jsx` acts as the entry point of a React app
* React uses a **Virtual DOM** to optimize updates
* Components must start with **capital letters**
* JSX requires **one root element**
* React applications are **Single Page Applications (SPA)**
