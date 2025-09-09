# 🧠 3 Using Vue via Create View

## 🟥 3.1 Creating and Building Example Vue Project
* From the terminal, I navigate to this folder.
* I call the following command:
   ```sh
   npm create vue@latest vue-crash-2025
   ```
* The terminal asks `Select features to include`, I select none for all the options (just pressed enter 3 times)
* For `Skip all example code and starte with a blank Vue project` I enter `No`
* The folder is created [here](./vue-crash-2025/)
* The contents of this folder:

   <img src="screenshots/2025-09-08-12-41-48.png" width="200px">
* I open this folder in VSCode, and install the Vue extension in market place (Vue (Official))
* Looking at the `package.json`:
  - we can see dependency for `vue`
  - We have `vite` as a devDependency
  - For scripts, we have `dev` which runs the local dev server, `build` for creating production buildm, and `preview` for previewing production build
* The `vite.config.js` file consists of the following:
   ```js
   // https://vite.dev/config/
   export default defineConfig({
   plugins: [
      vue(),
      vueDevTools(),
   ],
   resolve: {
      alias: {
         '@': fileURLToPath(new URL('./src', import.meta.url))
      },
   },
   })
   ```
* The author does not like the default server port of 5713, so he overrides it to 3000:
   ```js
   server: {
      port: 3000
   },
   ```
* Looking at `index.html`:
   ```html
   <!DOCTYPE html>
   <html lang="">
   <head>
      <meta charset="UTF-8">
      <link rel="icon" href="/favicon.ico">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Vite App</title>
   </head>
   <body>
      <div id="app"></div>
      <script type="module" src="/src/main.js"></script>
   </body>
   </html>
   ```
* I rename the title to `Vue Jobs`:
   ```html
   <title>Vue Jobs</title>
   ```

### 🔴 Building the Example Project

* I change directory into the `vue-crash-2025` folder, and I run the dev script via npm:
   ```sh
   npm run dev
   ```
* I get an error:
   ```sh
   > vue-crash-2025@0.0.0 dev
   > vite

   'vite' is not recognized as an internal or external command, operable program or batch file.
   ```
* I fix this by running `npm install`
* I rerun the dev script and get the following in the console showing its successful
* Now if I navigate to `localhost:3030`, I see the following page showing that I've successfully created and built the project:

   <img src="screenshots/2025-09-08-12-42-51.png" width="300px">

## 🟥 3.2 Using Directives via Options/Composition
### 🔴 Clearing up Project
* I want to modify the example project and get to a clean state, I take a copy of the folder and call it [shiv-vue-crash-2025](./shiv-vue-crash-2025/)
* I delete everything from the components folder
* I clear all the content from `App.vue` so that it only has the following content:
```js
<template>
  <h1>Vue Jobs</h1>
</template>
```
### 🔴 Basic Directives
* With Options API, I need to `export default`
* I start defining the module within a script tag:
```js
<script>
export default {
   data() {
      return {
         name: "Shiv Kumar",
         status: false
      }
   },
}
</script>
<template>
  <h1>Vue Jobs</h1>
</template>
```

* I now update the template to display the information using conditional **directives**:
```js
<template>
  <h1>{{name}}</h1>
  <p v-if="status === 'active'">User is Active</p>
  <p v-else-if="status === 'pending'">User is Pending</p>
  <p v-else>User is Inactive</p>
</template>
```
* Now when I run the app, I see the following:
![](screenshots/2025-09-09-08-22-25.png)

<br>

* There also is a directive for looping through an array.
* Suppose I wish to bullet point out tasks for an employee
* I first update the data so that it contains the task:
```js
return {
   name: "Shiv Kumar",
   status: false,
   tasks: ['Destroy all humans', 'Kill Flanders', 'Learn Vue']
}
```
* And then I update render using the `v-for` directive:
```js
<ul>
   <li v-for="task in tasks">{{task}}</li>
</ul>
```
* And the page lists out the tasks:
![](screenshots/2025-09-09-08-36-43.png)


### 🔴 v-bind Directive
* Suppose I want to add a link for going to google
* First I'll add the google link to my data:
* 

* While we COULD do this:
```js
<a href="https://www.google.com/">Click for Google</a>
```
* We use `v-bind` so that the `href` attribute's value is dynamic rather than be stuck at `https://www.google.com/`:
```js
<a v-bind:href="link">Click for Google</a>
```
* There is a shorthand for this:
```js
<a :href="link">Click for Google</a>
```
* The colon declares the link is not just `link` but dynamically set to what the `link` variable is in our data 💡
