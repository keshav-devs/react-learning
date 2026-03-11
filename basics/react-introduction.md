React Introduction & Learning Notes
Starting My React Journey

Today I started learning React, one of the most popular JavaScript libraries for building user interfaces.

This series I’m following is called “Chai aur React”, and the approach is project-based learning instead of only theory. That means I will build projects early and understand concepts through practice.

From the start, the main idea was clear:

React is not just about writing UI — it is about keeping UI and data in sync automatically.

Why React Exists

Before React, developers mainly used:

Vanilla JavaScript

jQuery

These worked well for simple websites, but as applications became bigger and more dynamic, managing UI became difficult.

The main issue was:

Keeping the UI consistent with the application data (state).

Developers had to manually update the DOM every time data changed, which often caused bugs.

The Facebook "Ghost Message" Problem

React was originally created by engineers at Facebook.

They faced a problem called the Ghost Message problem.

What happened?

Imagine Facebook Messenger:

You see 3 unread messages on the notification bar.

You click the chat.

The message count disappears in one place but still shows somewhere else.

So the UI became inconsistent.

Why did this happen?

Because:

JavaScript variables (state) were not properly synchronized with

DOM elements (UI).

React was created to solve this.

Key Idea

React automatically ensures:

State → UI synchronization

Whenever state changes, React updates the UI automatically.

When to Start Learning React

React should not be the first thing someone learns.

Before React, it's important to understand JavaScript fundamentals.

Important JS concepts needed before React:

Execution context

Call stack

Event loop

Variables and scope

Functions

Objects

DOM manipulation

Basic ES6 concepts

If JavaScript fundamentals are weak, React will feel confusing because React is essentially JavaScript with some additional tools.

Learning React: Two Approaches

There are mainly two ways to learn React.

1. Theory First Approach

This approach focuses on concepts first:

Virtual DOM

Reconciliation

React Fiber

Hooks

State management

This gives deeper understanding but may feel slow for beginners.

2. Project-Based Approach

This approach focuses on building projects first.

Concepts are introduced while building applications.

Benefits:

Faster confidence

Practical understanding

Easier to remember concepts

The series I’m following uses this project-first approach.

React: Library vs Framework

React is a library, not a framework.

Framework

Examples:

Angular

Django

Frameworks usually:

Enforce strict rules

Have fixed structure

Control how the project should be built

Library

React is a UI library.

Libraries:

Give flexibility

Let developers choose their own structure

Can be combined with other tools

Example tools commonly used with React:

React Router

Redux

Context API

So React focuses mainly on building UI components.

Core Concepts I Will Learn in React

The series will focus on several core React concepts.

1. Components

React applications are built using components.

A component is a reusable piece of UI.

Example components:

Navbar

Button

Card

Footer

Product item

Instead of writing one large UI file, React encourages breaking UI into small reusable pieces.

2. JSX

JSX stands for:

JavaScript XML

It allows writing HTML-like syntax inside JavaScript.

Example:

function App() {
  return <h1>Hello World</h1>;
}

Important point:

JSX is not HTML.
It is JavaScript syntax that gets converted into React elements.

3. State

State represents data that can change over time.

Examples:

Counter value

Input field text

User login status

API data

React automatically updates the UI when state changes.

Example idea:

State change → React re-renders UI

This is one of the most powerful ideas in React.

4. Props

Props means properties.

Props are used to pass data between components.

Usually:

Parent component sends data

Child component receives it

Example concept:

Parent Component → props → Child Component

This allows components to stay reusable.

5. Hooks

Hooks are special React functions.

They allow functional components to use features like:

State

Lifecycle events

Side effects

Examples of hooks:

useState

useEffect

Hooks made functional components more powerful, replacing most use cases of class components.

Passing State and Data Between Components

As applications grow, many components need to share data.

React allows:

Passing data using props

Triggering UI updates when state changes

Understanding how data flows between components is very important in React.

Additional Tools Used With React

React itself focuses only on UI rendering, so additional tools are often used.

React Router

React apps are usually Single Page Applications (SPA).

In SPA:

Page does not reload

Only components change

React Router helps with:

Navigation

Changing URLs

Showing different pages without refreshing

Example pages:

Home

About

Contact

State Management (Redux / Context API)

In large applications, passing props through many components becomes messy.

This problem is called prop drilling.

To solve this, developers use state management tools.

Popular options:

Context API

Built into React.

Good for small to medium applications.

Redux

External library used for large applications.

Helps manage global state in a predictable way.

However, these tools should only be learned when the need arises.

Class Components (Legacy React)

Originally React used class components.

Example structure:

class Component extends React.Component

But modern React uses functional components with hooks.

Still, it is useful to understand class components because many older projects still use them.

Backend Integration

Frontend apps often need backend services.

Instead of building backend from scratch, developers can use Backend-as-a-Service (BaaS) platforms.

Examples:

Firebase

Supabase

These provide:

Authentication

Databases

APIs

Hosting

This allows building full-stack apps quickly.

React Frameworks

React itself is only a library.

To build large applications more easily, frameworks are built on top of React.

Examples:

Next.js

Provides:

Server-side rendering

File-based routing

API routes

SEO improvements

Gatsby

Used for static websites.

Remix

Focused on performance and server rendering.

These frameworks extend React to make production apps easier.

Possible Career Paths After Learning React

After learning React, there are multiple directions.

Frontend Developer

Focus on:

React

UI performance

Accessibility

Testing

Full Stack Developer

Learn:

Node.js

Express

Databases

API development

Combine with React for full-stack apps.

Next.js Full Stack

Next.js allows both:

Frontend

Backend

inside one framework.

My Key Takeaways

React exists to keep UI synchronized with application state.

Strong JavaScript fundamentals are essential before React.

Learning React through projects makes concepts easier.

React is a library, not a framework.

Components, state, props, and hooks are the core building blocks.

Real-world apps require additional tools like React Router, Redux, and backend services.

My Learning Plan for React

I plan to follow a project-first learning approach and gradually build applications while understanding core concepts.

Goal:

Understand React fundamentals

Build multiple projects

Learn modern React (hooks, functional components)

Eventually explore frameworks like Next.js
