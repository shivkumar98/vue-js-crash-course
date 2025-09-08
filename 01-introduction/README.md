# 🧠 1 Introduction

## 🟥 1.1 What is Vue.js?
* Progressive JS framework for building user interfaces and **SPA** (Singe Page Applications)
* Designed to be simple, flexible and incrementally adoptable
* Can be used for projects of different sizes
* Reactive data-binding and **component-based architecture**

## 🟥 1.2 Prerequisites
* Fundamental JavaScript (loops, functions, objects, etc)
* Events and DOM manipulation
* Fetch API and basic HTTP
* Arrow Functions, High-Order Arrayh Methods, Destructuring
* NPM

## 🟥 1.3 The Role of Frontend Frameworks
* **Enhance UI/UX**: Enhanced user experience, easy to create dynamic and interactive UI
* **Organisation**: The UI is broken down to components rather than pure JS being unstructured causing friction in collaboration
* **Perforamance**: optimised and built in feature such as Virtual DOM (i.e. the DOM can be manipulated WITHOUT rebuilding the DOM each time)
* **Modularity**: modules allows reusability

## 🟥 1.3 Why Vue
* Very simple and approachable with flat learning curve
* Can be incremented into projects gradually
* Performance and lightweight library
* Component-based Architecture - allows modularity and reusable code
* Rich ecosystem with plugins

## 🟥 1.4 Vue Components
* Reusable, self-contained pieces of code
* This is what a vue file would look like:
   ```js
   <script>
      // JavaScript Logic
   </script>

   <template>
      <!-- output render-->
      <div>
         <h2>Hello from Vue!</h2>
         <p>This is a simple Vue component</p>
      </div>
   </template>

   <style scoped>>
      /* CSS Styling Here */
   </style>
   ```
* This consists of:
   - Logic
   - Dynamic HTML output
   - Scope styling
* There are two ways of constructing: **Options API** and **Composition API**
* This Options API is the classic way to do this
* The Composition API is only in Vue 3 and is the latest way to do it. It offers more features like lifecyle hooks

## 🟥 1.5 Getting Setup
* CDN - using a CDB URL in a script tag
* Vue CLI - no longer recommended
* Create Vue - uses Vite, which has hot-reloading, out of the box TypeScript and an ecosystem of plugins
* Nuxt.js & Gridstone - SSR and SSG frameworks which use Vue