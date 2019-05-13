---
id: bridges-simple-schema
title: SimpleSchema
---

**Note:** remember to import `uniforms-bridge-simple-schema` first.

```js
import {SimpleSchema} from 'aldeed:simple-schema';

const PersonSchema = new SimpleSchema({
  // ...

  aboutMe: {
    type: String,
    uniforms: MyText, // Component...
    uniforms: {
      // ...or object...
      component: MyText, // ...with component...
      propA: 1 // ...and/or extra props.
    }
  }
});
```
