# Express ES6 Starter

A minimal Express API skeleton written with modern ES6 module syntax (`import`/`export`), based on the structure produced by `express-generator` and compiled with Babel.

## What's inside

- Express application bootstrapped with ES6 `import`/`export` syntax throughout
- Babel build pipeline (`@babel/preset-env`) that transpiles `src` to a `dist` output for production
- Request logging via Morgan (`dev` format)
- CORS enabled for all routes
- Cookie parsing via `cookie-parser`
- JSON and URL-encoded body parsing
- Static file serving from the `public` directory
- Environment variables loaded via `dotenv`
- `nodemon` watch configuration for local development auto-reload

## Tech stack

- Node.js
- Express
- Babel (`@babel/core`, `@babel/preset-env`, `@babel/node`, `@babel/cli`)
- Morgan, CORS, cookie-parser, dotenv
- nodemon, npm-run-all, rimraf (dev tooling)

## Quickstart

Install dependencies with Bun (`bun.lock` is the single source of truth):

```bash
bun install
```

Run in development mode (starts the server directly from `src` via `babel-node`):

```bash
bun run dev
```

Run with auto-reload on file changes:

```bash
bun run watch
```

Build and run a production bundle (cleans `dist`, transpiles `src` to `dist`, then runs the compiled server):

```bash
bun run prod
```

Other available scripts:

```bash
bun run build   # transpile src -> dist with Babel
bun run clean   # remove the dist directory
bun run server  # run the server from src via babel-node (no NODE_ENV/DEBUG set)
```

The server listens on the port from the `PORT` environment variable, defaulting to `3000`.

## Project structure

```
src/
  app.js          # Express app setup (middleware, static files, routing)
  bin/www.js       # HTTP server bootstrap (port binding, error handling)
  routes/index.js  # Route definitions
public/            # Static assets served by Express
```

## Key endpoints

| Method | Path | Description |
| --- | --- | --- |
| GET | `/` | Returns a JSON payload identifying the API (`{ "info": "Express API" }`) |

Static assets under `public/` (e.g. `stylesheets/style.css`) are also served directly.
