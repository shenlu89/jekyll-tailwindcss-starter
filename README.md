# Jekyll Tailwindcss Starter

A dead simple, comprehensive Jekyll boilerpalte styling with Tailwind CSS.

## Features

- Support [Tailwind CSS](https://tailwindcss.com/), including [PostCSS](https://postcss.org/), [PurgeCSS](https://purgecss.com/)
- Compatiable with **Mordern Browsers** except **IE 11+**
- Support **Pagination** powered by `jekyll-paginate`
- Support **Google Analytics**
- Support **Markdown** and via `kramdown` (rouge)
- Support **Syntax Highlighting** with [Typography](https://github.com/tailwindlabs/tailwindcss-typography)
- Support **Comments System** via [Disqus](https://disqus.com/)
- Support **Latex** syntax via [Mathjax](https://www.mathjax.org/)

## Philosophy

1. As simple as possible, as comprehensive as possible.
2. Only support modern browsers
3. Utility-first and style flexible

## Prerequisite

- [Node](https://nodejs.org/en/) >= 12
- [Jekyll](https://jekyllrb.com/) >= 4

## Installation

```sh
// Pull down Jekyll Tailwindcss Starter
git clone https://github.com/shenlu89/jekyll-tailwindcss-starter.git
// Get into the folder
cd jekyll-tailwindcss-starter
// Install node dependencies
yarn
// Generate main.css via tailwindcss
yarn css:build
// Preview the website
yarn jekyll:serve
```

## License

[MIT](https://github.com/shenlu89/jekyll-tailwindcss-starter/blob/main/LICENSE)