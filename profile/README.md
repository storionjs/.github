## StorionJS

Storion is a **friendly, framework‑agnostic client‑side database for the browser**.  
Think of it as a tiny, in‑browser data layer that feels like a real database but lives entirely on the client side.

- **GitHub (library)**: [github.com/storionjs/storion](https://github.com/storionjs/storion)
- **npm**: [@storion/storion](https://www.npmjs.com/package/@storion/storion)

With Storion you can:

- **Model your data** with a simple, JSON‑friendly schema for tables and columns
- **Read and write data** using straightforward CRUD APIs (`createTable`, `insert`, `fetch`, `update`, `delete`)
- **Filter and sort** using expressive JSON queries (`where`, `orderBy`, `limit`, `offset`)
- **Keep UIs in sync** via change subscriptions, so components update automatically when data changes

You can drop Storion into new or existing front‑end apps when you:

- Want a local, persistent data store (for example, backed by `localStorage`)
- Prefer working with JSON and TypeScript types instead of raw browser storage APIs
- Need a small, predictable alternative to heavier state‑management or offline‑first stacks

For in‑depth docs, query examples, and CRUD workflows, see the main documentation in `storion-docs/`.

---

## Sample framework integrations

This repository also contains small sample projects that show how to use Storion in popular front‑end frameworks. Each sample focuses on:

- Initializing a Storion database (usually backed by `localStorage`)
- Defining a simple `todos` table
- Inserting, listing, and updating rows from UI components
- Patterns for sharing a single database instance and wiring change subscriptions into the framework’s state model

### Angular (`angular-storion`)

The `angular-storion` sample demonstrates:

- **Service‑based integration**: an injectable `StorionDbService` that wraps `createDatabase` and exposes `getDb()`.
- **Component usage**: a `TodosComponent` that creates a `todos` table, inserts rows, and fetches data via the service.
- **Recommended patterns**: using a singleton service per app, exposing RxJS observables backed by `db.subscribe`, and optionally driving schema from a JSON config.

See `angular-storion/README.md` for full code snippets and setup instructions.

### React (`react-storion`)

The `react-storion` sample demonstrates:

- **Custom hook**: a `useStorionDb` hook that initializes Storion once and returns the database instance.
- **Stateful components**: a `TodoList` component that creates the `todos` table, inserts rows, and keeps React state in sync with the database.
- **Recommended patterns**: a single shared database instance (for example via context), and using `db.subscribe` inside `useEffect` to drive live UIs.

See `react-storion/README.md` for detailed usage.

### Vue 3 (`vue-storion`)

The `vue-storion` sample demonstrates:

- **Composable integration**: a `useStorionDb` composable that initializes Storion and exposes a reactive `db`.
- **Composition API usage**: a Vue component that creates the `todos` table, inserts data, and renders a `Todos` list.
- **Recommended patterns**: wiring `db.subscribe` into Vue reactivity and using a config‑driven schema with `createDatabase({ name, storage, config })`.

See `vue-storion/README.md` for full examples.

---

## Getting started

- **New to Storion?** Start with `storion-docs/README.md` for an overview of query syntax, CRUD operations, and subscriptions.
- **Trying a framework sample?** Open the corresponding subfolder (`angular-storion`, `react-storion`, or `vue-storion`) and follow its `README.md` to run the demo locally.

