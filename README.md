# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

Learn more about IDE Support for Vue in the [Vue Docs Scaling up Guide](https://vuejs.org/guide/scaling-up/tooling.html#ide-support).

### Setup Note

1. Create project

```
npm create vite@latest
```

### Deploy github

1. Add Base Public Path
   Add `base` in `vite.config.ts` file.

```
export default defineConfig({
  base: "/REPONAME/",
  plugins: [],
})
```

2. Create a ‘gh-pages’ branch containing /dist
   Run these commands to push up `/dist` into a new or existing gh-pages branch:

```
npm run build
git subtree push --prefix dist origin gh-pages
```

3. Update GitHub pages settings
   Go to your repository in github.com, and go to:

Settings -> Pages
Under Build and Deployment, for source -> pick Deploy from a branch
For your branch, pick gh-pages
click save

4. Install the gh-pages node module

```
npm install gh-pages --save-dev
```

5. Add below to `package.json`

```
"scripts": {
  ...
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist",
  ...
}
```

6. Run deploy if you want to deploy new changes

```
npm run deploy
```
