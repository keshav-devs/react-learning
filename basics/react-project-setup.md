# React Project Setup & Environment

## 🚀 Continuing My React Learning

In this lecture I moved from theory to **actually creating a React project**.

Instead of only discussing concepts, the instructor started building a small project to explain:

* How React projects are created
* Tools required
* Difference between CRA and Vite
* What happens inside a React project

This lecture mainly focused on **setting up the development environment and understanding the basic project structure**.

---

# Tools Required for React Development

React development is **platform independent**, meaning it works on:

* Windows
* macOS
* Linux

The main tools required are:

---

## 1️⃣ Code Editor

Any code editor can be used to develop React applications.

Examples:

* VS Code (most commonly used)
* Vim
* Sublime Text

In this lecture, **VS Code** was used.

---

## 2️⃣ Node.js

Normally **JavaScript runs inside browsers**.

Node.js provides a **runtime environment** that allows JavaScript to run **outside the browser**.

You can compare it with other programming environments:

* Python → Python interpreter
* Java → JVM
* JavaScript outside browser → Node.js

Node.js is required because tools like **npm, Vite, and other build tools** run on Node.

Example version used in the lecture:

```
Node v19.3.0
```

Both **LTS and current versions work fine**.

---

# GitHub Repository Setup

A GitHub repository was created to store all the code related to the series.

Repository name:

```
chai-aur-react
```

Description:

```
Chai aur React Series YouTube
```

---

# Git Commands Used

### Initialize Git repository

```bash
git init
```

### Add README file

```bash
git add README.md
```

### Create first commit

```bash
git commit -m "Start of React Series"
```

### Rename branch

```bash
git branch -M main
```

### Connect repository to GitHub

```bash
git remote add origin <repo-url>
```

### Push code to GitHub

```bash
git push -u origin main
```

This allows students to **access and follow the project code easily**.

---

# React Official Documentation

The instructor visited the official React documentation:

```
https://react.dev
```

Important note:

There used to be **older React documentation**, but now the official documentation is on **react.dev**.

The documentation contains sections like:

* Quick Start
* Thinking in React
* API Reference

Important advice:

> Developers should **learn from official documentation**, not rely only on video tutorials.

---

# Observation About React Docs

The official React docs recommend frameworks such as:

* Next.js
* Remix
* Gatsby

However, beginners should first understand **basic React concepts** before jumping into frameworks.

---

# Understanding the React Ecosystem

React is part of a **larger ecosystem of libraries**.

### Core React Libraries

| Library           | Purpose                                   |
| ----------------- | ----------------------------------------- |
| react             | Core library for components, hooks, state |
| react-dom         | Connects React with browser DOM           |
| react-native      | Used for building mobile apps             |
| react-three-fiber | Used for 3D graphics with Three.js        |

Important concept:

> If you understand **React fundamentals**, you can apply them in both **web apps and mobile apps**.

---

# Two Ways to Create a React Project

There are mainly **two ways to create a React application**.

---

# Method 1: Create React App (CRA)

Command:

```bash
npx create-react-app 01basicreact
```

---

## Understanding NPM vs NPX

### NPM (Node Package Manager)

Used to **install packages**.

Example:

```bash
npm install react
```

---

### NPX (Node Package Executor)

Used to **run packages without installing them globally**.

Example:

```bash
npx create-react-app
```

---

## Problems With Create React App

CRA used to be popular, but it has some drawbacks:

* Installation is **slow**
* Many **unnecessary dependencies**
* Larger bundle size
* Not the modern preferred approach

Because of this, newer tools are recommended.

---

# Method 2: Vite (Modern Approach)

Modern React projects are usually created using **Vite**.

Command:

```bash
npm create vite@latest
```

---

# Steps Followed During Setup

### 1. Enter project name

```
01vitereact
```

### 2. Select framework

```
React
```

### 3. Select variant

```
JavaScript
```

### 4. Navigate to project folder

```bash
cd 01vitereact
```

### 5. Install dependencies

```bash
npm install
```

### 6. Start development server

```bash
npm run dev
```

---

# Why Vite Is Preferred

Compared to CRA, **Vite has several advantages**:

* Much **faster startup**
* Lightweight dependencies
* Simpler configuration
* Only installs necessary packages like `react` and `react-dom`

Because of this, **Vite is now the preferred way to start React projects**.

---

# Understanding package.json

One important habit mentioned in the lecture:

> Whenever you open a new project, always read **package.json first**.

The `package.json` file describes the entire project.

Common fields inside it:

### name

Project name.

### version

Project version.

### dependencies

Libraries required for the project to run.

Example:

```
react
react-dom
```

### devDependencies

Libraries required only during development.

### scripts

Commands used to run tasks in the project.

---

# Important Scripts

| Script | Purpose                            |
| ------ | ---------------------------------- |
| start  | Runs development server            |
| build  | Creates production build           |
| test   | Runs tests                         |
| eject  | Removes CRA abstraction            |
| lint   | Shows code improvement suggestions |

Example command:

```bash
npm run dev
```

---

# browserslist

The `browserslist` configuration defines **which browsers the app should support**.

Example:

* Latest Chrome
* Latest Safari
* Latest Edge

This helps tools compile JavaScript compatible with those browsers.

---

# Build Process

Command used:

```bash
npm run build
```

This creates a **build folder** containing production-ready files.

### Build process

1. React code is compiled
2. JSX is converted into JavaScript
3. Assets are optimized
4. Static files are generated

The final build folder usually contains:

* HTML
* CSS
* JavaScript bundles

Important:

> Users never see your source code — they only receive the **compiled build output**.

---

# Cleaning the CRA Project

The instructor removed unnecessary files from the `src` folder.

### Deleted Files

```
setupTests.js
reportWebVitals.js
logo.svg
App.test.js
App.css
index.css
```

### Remaining Files

```
App.js
index.js
```

---

# Clean App.js Example

```javascript
function App() {
  return (
    <h1>Chai aur React</h1>
  )
}

export default App
```

---

# Cleaning the Vite Project

Similarly unnecessary files were removed.

### Deleted Files

```
assets/
App.css
index.css
unused imports
```

---

# Clean App.jsx Example

```javascript
function App() {
  return (
    <h1>Chai aur React | Hitesh</h1>
  )
}

export default App
```

Run development server:

```bash
npm run dev
```

---

# Important Observation: Page Source

When checking **View Page Source** in a React app:

The HTML looks almost empty.

Example:

```html
<div id="root"></div>
```

Why?

Because React applications are **Single Page Applications (SPA)**.

The browser loads a minimal HTML file and JavaScript dynamically renders the UI.

This means:

* The UI is injected using JavaScript
* HTML source does not contain the actual UI content

---

# SEO Consideration

Because the initial HTML is mostly empty, React SPAs are **not SEO-friendly by default**.

This is why frameworks like **Next.js** exist.

Next.js supports **Server-Side Rendering (SSR)** which improves SEO.

---

# Assignment Given in the Lecture

The instructor asked students to:

### 1️⃣ Modify the `<h1>` tag and add their name

Example:

```javascript
<h1>Chai aur React | Keshav</h1>
```

### 2️⃣ Write notes about the lecture

### 3️⃣ Share learning on LinkedIn

### 4️⃣ Comment under the video

---

# What I Expect to Learn Next

The next lecture will explain deeper concepts such as:

* How React projects work internally
* Execution order of files
* React scripts
* CRA vs Vite project structure
* How JSX is converted into JavaScript
* "Thinking in React"

---

# Key Takeaways

* React development requires **Node.js**
* **Vite is preferred over CRA** for creating modern React apps
* Always check **package.json** to understand a project
* React web development mainly uses **react + react-dom**
* The **build folder** contains production-ready code
* React apps appear empty in **View Page Source** because they are SPAs
* It is good practice to **clean unnecessary files** from a new project
