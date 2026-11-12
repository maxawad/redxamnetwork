# EleventyOne

[![Netlify Status](https://api.netlify.com/api/v1/badges/056b4a67-70e6-4af4-9be5-dee151b8e906/deploy-status)](https://app.netlify.com/sites/eleventyone/deploys)

EleventyOne is a ready-made starting point for building a small website with the Eleventy static site generator. It gives you a skeleton site with posts, a search index, a CSS pipeline and example serverless functions, so you can start writing content straight away. This repository is a copy of Phil Hawksworth's open source template (see Credits).

## What it does

- Builds a static site from Markdown and Nunjucks templates into the `dist/` folder.
- Compiles CSS with PostCSS and inlines minified JavaScript.
- Generates a JSON search index at `/search.json` and a sitemap.
- Includes two example Netlify Functions (`hello` and `fetch-joke`) served under `/api/`.
- Can pull data from external feeds (a JSON feed and a Medium RSS feed) and save a local copy for offline development.

## Tech stack

JavaScript (Node.js), Eleventy 0.8, Nunjucks, Markdown, PostCSS, Luxon, Axios, Netlify Functions.

## Run it

You need Node.js and npm. The project is old, so an older Node version (10 to 14) is the safest choice for the pinned Eleventy 0.8.

```bash
npm install

# Development server with live reload, using the saved sample data in src/site/_data/dev
npm start

# Production build to static files in dist/ (fetches the feeds listed in src/site/_data/prod, so it needs internet access)
npm run build

# Refresh the saved sample data from the live feeds
npm run seed
```

No API keys are needed. To try the static output, serve the `dist/` folder with any static file server, for example `npx serve dist`. To also run the serverless functions locally, use Netlify Dev (see below).

## Status

Working template. It uses 2019 era dependencies and has not been updated since, so expect deprecation warnings.

## Credits

Created by [Phil Hawksworth](https://github.com/philhawksworth/eleventyone) and released under the MIT license (see `LICENSE`). Contributions from David Darnes, Nicolas Hoizey, Frank Taillandier, Daniel Schildt and others.

---

## Original notes

Phil's first port of call when starting another project using Eleventy.

This project scaffold includes:

- [Eleventy](https://11ty.io) with a skeleton site
- A date format filter for Nunjucks based on [Luxon](https://moment.github.io/luxon)
- A tiny CSS pipeline with PostCSS
- A tiny inline JS pipeline
- JS search index generator
- [Netlify Dev](https://www.netlify.com/products/dev) for testing [Netlify redirects](https://netlify.com/docs/redirects/)
- Serverless (FaaS) development pipeline with [Netlify Dev](https://www.netlify.com/products/dev) and [Netlify Functions](https://www.netlify.com/products/functions)


![Eleventy screenshot](./eleventyone-template.jpg)


## Instructions

To get your own instance of this 11ty starter project cloned and deploying to Netlify very quickly, just click the button below and follow the instructions.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/philhawksworth/eleventyone)


## Wait, what happens when I click that button?

Good question. Here's what it will do...

1. Netlify will clone the git repository of this project into your Github account. It will be asking for permission to add the repo for you.
2. We'll create a new site for you in Netlify, and configure it to use your shiny new repo. Right away you'll be able to deploy changes simply by pushing changes to your repo.
3. That's it really.


## Prerequisites

- [Node and NPM](https://nodejs.org/)
- [Netlify CLI](https://github.com/netlify/cli)

## Running locally

```bash
# install the dependencies
npm install

# External data sources can be stashed locally
npm run seed

# It will then be available locally for building with
npm start
```

## Add some Netlify helpers
Netlify Dev adds the ability to use Netlify redirects, proxies, and serverless functions.

```bash
# install the Netlify CLI in order to get Netlify Dev
npm install -g netlify-cli

# run a local server with some added Netlify sugar in front of Eleventy
netlify dev
```

A serverless functions pipeline is included via Netlify Dev. By running `netlify dev` you'll be able to execute any of your serverless functions directly like this:

- /.netlify/functions/hello
- /.netlify/functions/fetch-joke


### Redirects and proxies

Netlify's Redirects API can provide friendlier URLs as proxies to these URLs.

- /api/hello
- /api/fetch-joke

