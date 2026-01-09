## Nuxt Testing Utils (NTU)

- provide Nuxt context in test suites
- built-in mocks (e.g., **IndexedDB**)
- helpers (e.g., **mockNuxtImport** to mock auto-imports)
- mount Vue components with **mountSuspended** 
    - within the Nuxt environment
    - allowing async setup and access to injections from your Nuxt plugins
- write unit tests and end-to-end (e2e) tests

---

## Vitest Testing Environment

- [https://vitest.dev/guide/environment](https://vitest.dev/guide/environment)
- Vitest provides environment option to run code inside a specific environment:
    - "nuxt"
    - "jsdom"
    - "happy-dom"
    - "node"