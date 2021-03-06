---
id: typescript-vue-apollo
title: TypeScript Vue Apollo
---

This plugin generates @vue/apollo-composable composition functions with TypeScript typings. It extends the basic TypeScript template [`@graphql-codegen/typescript`](typescript) and thus shares a similar configuration.


{@import ../plugins/client-note.md}

## Installation

```bash
$ yarn add @graphql-codegen/typescript-vue-apollo @vue/apollo-composable@4.0.0-alpha.8 @vue/composition-api
```

## Usage

For the given input:

```graphql
query Test {
  feed {
    id
  }
}
```

We can use the generated code like this in Vue 2 ([with composition api plugin](https://github.com/vuejs/composition-api)):

```vue
<template>
  <div>
    {{ result.feed.id }}
  </div>
</template>

<script lang="ts">
import { createComponent } from "@vue/composition-api";
import {
  useTestQuery,
} from "../generated/graphqlOperations";

export default createComponent({
  setup() {
    const { result } = useMessagesQuery();

    return { result };
  }
});
</script>
```

## Configuration


{@import ../generated-config/base-visitor.md}

{@import ../generated-config/client-side-base-visitor.md}

{@import ../generated-config/typescript-vue-apollo.md}
