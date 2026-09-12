# ShopPOS

ShopPOS is a simple point-of-sale (POS) / billing system for a retail shop (NOVAMART).

## Project structure

- `index.html` — the main POS web app (single file containing HTML, CSS, and JavaScript UI)
- `shoppos/` — the application folder:
  - `index.html` — main POS application UI
  - `data.json` — store data: shop settings, categories, products, and related records
  - `server.ps1` — lightweight PowerShell web server for local development
- `.gitignore` — Git ignore rules

## Development workflow

- The app requires no build step. Open `shoppos/index.html` in a browser, or run the local server:
  ```
  powershell -ExecutionPolicy Bypass -File shoppos/server.ps1
  ```
  which serves the app at `http://localhost:5173/`.
- `shoppos/data.json` is the persistent data file. It uses `"settings"`, `"categories"`, and product-ish arrays with `id` fields and millisecond `createdAt` timestamps.
- Currency is PKR (`₨`).

## Conventions

- Keep the app dependency-free (no build tools, no npm packages).
- Maintain data as JSON arrays keyed by `id`.
- Changes to `data.json` should preserve existing fields to avoid breaking the UI.