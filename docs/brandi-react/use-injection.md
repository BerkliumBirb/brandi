---
id: use-injection
title: useInjection
sidebar_label: useInjection
---

The `useInjection(token)` hook allows you to get a dependency
from a container provided through [`ContainerProvider`](./container-provider.md).

## Arguments

1. `token`: [`TokenValue`](../reference/pointers-and-registrators.md#tokentdescription).

## Returns

`TokenType<TokenValue>` — a dependency bound to the token.

## Example

```tsx
import { useInjection } from 'brandi-react';
import { FunctionComponent } from 'react';

import { TOKENS } from '../tokens';

export const UserComponent: FunctionComponent = () => {
  const userService = useInjection(TOKENS.userService);
  const logger = useInjection(TOKENS.logger.optional);

  /* ... */

  return (/* ... */);
}
```

The binding of `TOKENS.userService` was shown
in [the example](./container-provider.md#providing-a-modules-own-container) in `ContainerProvider` section.

For more information about `TOKENS.logger.optional` syntax,
see the [Optional Dependencies](../reference/optional-dependencies.md) documentation section.
