---
attach: agent-requested
description: Read when you want to get statistics on the time and memory the TypeScript Compiler used to process a specific implementation.
---

# Get TypeScript Diagnostics

1. Create tmp directory and `cd` to it.

2. Create `tsconfig.json` like this in root of tmp directory. Always extend project config.

    ```json
    {
      "extends": "<path to project tsconfig>",
      "include": ["main.ts"]
    }

3. Create `main.ts` in the same directory and paste full implementations you want to check.

4. Run tsc with `npx tsc -p <path to tmp tsconfig> --diagnostics`
