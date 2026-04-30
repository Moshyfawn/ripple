---
"@tsrx/language-core": minor
"@tsrx/typescript-plugin": patch
"@ripple-ts/language-server": patch
---

Extract shared Volar language plugin and utils into a new `@tsrx/language-core` package.

`language.js` and `utils.js` were deep-imported from `@tsrx/typescript-plugin/src/`. While this worked in the workspace via pnpm symlinks, it broke for npm consumers because the typescript-plugin artifact only ships `dist/`. Shared logic now lives in `@tsrx/language-core`, consumed via its public package entry.
