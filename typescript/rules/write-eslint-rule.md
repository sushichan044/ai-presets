---
attach: agent-requested
description: When you write an ESLint custom rule, always read this document.
---

# ESLint Custom Rule

Always use `@typescript-eslint/utils`.
Read <https://typescript-eslint.io/developers/custom-rules> for additional examples.

```ts
import { ESLintUtils } from '@typescript-eslint/utils';

const createRule = ESLintUtils.RuleCreator(
  name => `https://example.com/rule/${name}`,
);

export const useUpperCaseFunctionDeclaration = createRule({
  create(context) {
    return {
      FunctionDeclaration(node) {
        if (node.id != null) {
          if (/^[a-z]/.test(node.id.name)) {
            context.report({
              messageId: 'uppercase',
              node: node.id,
            });
          }
        }
      },
    };
  },
  name: 'uppercase-first-declarations',
  meta: {
    docs: {
      description:
        'Function declaration names should start with an upper-case letter.',
    },
    messages: {
      uppercase: 'Start this name with an upper-case letter.',
    },
    type: 'suggestion',
    schema: [],
  },
  defaultOptions: [],
});
```

## Testing

You must write ESLint Rules with TDD.
Use `@typescript-eslint/rule-tester` to test ESLint Rules.

Read <https://typescript-eslint.io/packages/rule-tester#type-aware-testing> for detailed APIs.

```ts
import * as vitest from 'vitest';
import { RuleTester } from '@typescript-eslint/rule-tester';

RuleTester.afterAll = vitest.afterAll;

// If you are not using vitest with globals: true (https://vitest.dev/config/#globals):
RuleTester.it = vitest.it;
RuleTester.itOnly = vitest.it.only;
RuleTester.describe = vitest.describe;
```
