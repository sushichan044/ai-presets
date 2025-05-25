---
attach: glob
globs:
  - "**/*.js"
  - "**/*.jsx"
  - "**/*.ts"
  - "**/*.tsx"
  - "**/*.cjs"
  - "**/*.cts"
  - "**/*.mjs"
  - "**/*.mts"
---

# TDD in TypeScript

Place test files with the `.test.ts` extension in the same directory as the implementation files.
Whenever making further modifications to the code, always ensure that `npm test` passes.

```ts
import { describe, it } from "vitest"
import { mul } from "./mul"

describe("mul",() => {
  it("muls", () => {
    expect(mul(3, 5)).toBe(15)
  })

  it("results zero if one is zero", () => {
    expect(mul(3, 0)).toBe(0)
  })
})
```
