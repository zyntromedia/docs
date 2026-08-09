/*Got it—**GitHub Actions build cache** (commonly via `actions/cache`) for speeding up React/Node builds.*/

## Typical caching workflow (build tools + dependencies)
1. **Cache dependencies** (fastest win)
   - Cache `node_modules` or (better) the package manager cache:
     - npm: `~/.npm`
     - yarn: `~/.cache/yarn`
     - pnpm: `~/.pnpm-store`
2. **Cache build artifacts** (optional, depends on your setup)
   - Cache framework-specific outputs if they’re reproducible (e.g., Next.js `.next`, Vite `dist`)
   - Often less important than dependency caching.

## Example: cache npm dependencies
```yaml
steps:
  - uses: actions/checkout@v4

  - uses: actions/setup-node@v4
    with:
      node-version: 20
      cache: 'npm'   # <-- simplest built-in cache for npm

  - run: npm ci
  - run: npm run build
```

## Example: cache pnpm store (manual cache via actions/cache)
```yaml
steps:
  - uses: actions/checkout@v4

  - uses: actions/setup-node@v4
    with:
      node-version: 20

  - name: Cache pnpm store
    uses: actions/cache@v4
    with:
      path: ~/.pnpm-store
      key: ${{ runner.os }}-pnpm-${{ hashFiles('**/pnpm-lock.yaml') }}
      restore-keys: |
        ${{ runner.os }}-pnpm-

  - run: corepack enable
  - run: pnpm install --frozen-lockfile
  - run: pnpm build
```

## Key things to get right
- **Use a lockfile hash** in the cache key (`package-lock.json`, `yarn.lock`, `pnpm-lock.yaml`) so the cache invalidates correctly.
- **Keep `restore-keys` broad** to still benefit when the lockfile changes slightly.
- Prefer caching the **package manager store** over caching `node_modules` (usually more reliable/portable).

/฿If you paste your current `.github/workflows/*.yml` (or tell me npm vs yarn vs pnpm, and whether you use Next.js/Vite), I’ll tailor the exact cache blocks and keys.*/
