---
layout: post
title: How to Setup Jekyll with Tailwind CSS
subtitle: Setup Jekyll with Tailwind CSS, including PostCSS and PurgeCSS
date: 2021-08-05 -0500
image: '/assets/images/tailwindcss.85c0ff9.jpg'
---

As a front-end developer, the most annoying things I have had is to name a mass of CSS classes, which are specified to one project normally, but can not always be used to others. So next time, you still need waste plenty of time to struggle for giving one class a new name. To solve this problem, I decided to integrate **Tailwind CSS** into my later projects.

Tailwind CSS is a utility-first CSS framework that provides a constraints of a system instead of littering your stylesheets with arbitrary values. The website integrated with Tailwind will be consistent with color choices, spacing, typography, shadows, and everything else that makes up a well-engineered design system.

In the last article, [Build Your First Jekyll Website from Zero](/2021/08/02/build-your-first-jekyll-website-from-zero.html), I had created an empty jekyll scaffold. Let's learn how to get Tailwind CSS up and running in it.

### Install Tailwind CSS with PostCSS and Autoprefixer

Beside installing Tailwind, we need install **PostCSS** and **Autoprefixer** alongside it:

```sh
cd your_website_name
yarn add -D tailwindcss@latest postcss@latest autoprefixer@latest
```

1. `PostCSS` is a tool for transforming styles with JS plugins that can lint your CSS, support variables and mixins, transpile future CSS syntax, inline images, and more.
2. `Autoprefixer` can automatically add vendor prefixes to the bundled CSS via Tailwind plugin in `PostCSS`.

### Add Tailwind as a PostCSS plugin

Before applying `Autoprefixer` and `Tailwind` in your project, we should add a `postcss.config.js` at the root of the project:

```sh
touch postcss.config.js
```

Then add `Tailwind` and `Autoprefixer` as a `PostCSS` plugin into it.

```js
// postcss.config.js
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  }
}
```

### Create Tailwind configuration file

For customizing Tailwind installation, you can generate a config file for your project using Tailwind CLI.

```sh
npx tailwindcss init
```

a minimal `tailwind.config.js` fill had been generated at the root of your project.

```js
// tailwind.config.js
module.exports = {
  purge: [],
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {},
  plugins: [],
}
```

### Build the default Tailwind CSS file

<!-- Tailwind CLI  -->

First, you can edit some pages in project, like like `index.md`, to test if the generated CSS file by Tailwind works well:

```html
<h2 class="text-blue-700 text-2xl">You're ready to go!</h2>
```

And remove the `main.scss` file and `_sass/` folder from the scaffold and run this command:

```sh
npx tailwindcss -o ./assets/css/main.css
```

Serve and browse it again.

![]({{ site.github.url }}/assets/images/jekyll-tailwindcss-scaffold.png)

Now it works.

### Optimize building Tailwind CSS file in production mode

Tailwind v2.2+ uses [PurgeCSS](https://purgecss.com/) and [cssnano](https://cssnano.co/) as build-in plugins:

1. `PurgeCSS` is a tool to remove unused CSS
2. `cssnano` formats CSS to ensure as small as possible for a production environment.

To remove unused CSS, you can configure the `purge` option in your `tailwind.config.js` file with all files path that contain CSS.

```js
// tailwind.config.js
module.exports = {
  purge: [
     './src/**/*.{html,md}',
  ],
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {},
  plugins: [],
}
```

Moreover, you can set the mode option to `jit` to speed up the CSS file generation of Tailwind

```js
// tailwind.config.js
module.exports = {
  mode: 'jit',
  purge: [
     './src/**/*.{html,md}',
  ],
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {},
  plugins: [],
}
```

and then minify your CSS with `cssnano` just by adding the `--minify` flag, a new feature starting from [Tailwind v2.2](https://blog.tailwindcss.com/tailwindcss-2-2), at the end of `npx tailwindcss -o ./assets/css/main.css`.

```sh
npx tailwindcss -o ./assets/css/main.css --minify
```

Finally, you can create your own npm scripts, `dev` and `build` scripts, in `package.json`:

```javascript
// package.json
"scripts": {
    "jekyll:dev": "bundle exec jekyll serve --incremental --watch",
    "css:build": "npx tailwind -o ./assets/css/main.css --minify",
  }
```

You can build CSS file and browse in <http://127.0.0.0:4000> if it could work well.

```sh
yarn css:build # generate tailwind-style css for production
yarn jekyll:dev # gnerate site and preview it
```

Now you can be free to use Tailwind in this Jekyll project.