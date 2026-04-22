# leah-maelane-site

Astro static site for [leahmaelane.com](https://leahmaelane.com), deployed to Cloudflare Workers with Static Assets.

## Project structure

```
/
├── public/              Static assets served as-is
├── src/
│   └── pages/           File-based routes
├── astro.config.mjs
├── wrangler.jsonc       Cloudflare Worker config
└── package.json
```

## Commands

| Command            | Action                                             |
| :----------------- | :------------------------------------------------- |
| `npm install`      | Install dependencies                               |
| `npm run dev`      | Start local dev server at `localhost:4321`         |
| `npm run build`    | Build production site to `./dist/`                 |
| `npm run preview`  | Preview the build locally                          |
| `npm run deploy`   | Build, then deploy to Cloudflare Workers           |

## Deployment

The site is served by a Cloudflare Worker using [Workers Static Assets](https://developers.cloudflare.com/workers/static-assets/). Configuration lives in `wrangler.jsonc`.

First-time setup:

```sh
npx wrangler login
```

Deploy:

```sh
npm run deploy
```

This runs `astro build` and then `wrangler deploy`, which uploads `./dist/` to Cloudflare.
