---
"@cloudflare/autoconfig": patch
"@cloudflare/containers-shared": patch
"@cloudflare/deploy-helpers": patch
"@cloudflare/shared-ast-primitives": patch
"@cloudflare/workers-auth": patch
"@cloudflare/workers-utils": patch
---

Fix `types` condition ordering in `package.json` `exports` and `@cloudflare/workers-utils` browser build platform

Placing `"types"` after other conditions could prevent TypeScript from resolving declaration files according to the Node.js specification, and building `@cloudflare/workers-utils` browser entry points with `platform: "node"` risked bundling Node.js shims. Type declarations now resolve reliably and browser entry points remain free of Node.js shims.
