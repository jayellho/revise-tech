# Playwright
## What is it
- For reliable end-to-end testing of web applications.
- https://playwright.dev

## Installation
Source: https://playwright.dev/docs/intro

- Install `pnpm`
```
wget -qO- https://get.pnpm.io/install.sh | sh -
```
- Install playwright
```
pnpm create playwright
```
- Install dependencies needed for running browsers
```
pnpm exec playwright install-deps
```
- Update playwright
```
pnpm install --save-dev @playwright/test@latest
pnpm exec playwright install --with-deps
```

## How to use
### Running tests
Run tests in UI mode. By default, headless hence the need for the `--ui` flag.
```
pnpm exec playwright test --ui
```
- Modify the test browsers in `playwright.config.ts`.

### Showing HTML test reports
Auto-opens on failure; below is to open manually.
```
pnpm exec playwright show-report
```
