---
id: bridges-graphql
title: GraphQL
---

```js
import {GraphQLBridge} from 'uniforms-bridge-graphql';
import {buildASTSchema} from 'graphql';
import {parse} from 'graphql';

const schema = `
    type Author {
        id:        String!
        firstName: String
        lastName:  String
    }

    type Post {
        id:     Int!
        author: Author!
        title:  String
        votes:  Int
    }

    # This is required by buildASTSchema
    type Query { anything: ID }
`;

const schemaType = buildASTSchema(parse(schema)).getType('Post');
const schemaData = {
  id: {
    allowedValues: [1, 2, 3]
  },
  title: {
    options: [{label: 1, value: 'a'}, {label: 2, value: 'b'}]
  }
};

const schemaValidator = model => {
  const details = [];

  if (!model.id) {
    details.push({name: 'id', message: 'ID is required!'});
  }

  // ...

  if (details.length) {
    throw {details};
  }
};

const bridge = new GraphQLBridge(schemaType, schemaValidator, schemaData);

// Later...

<ValidatedForm schema={bridge} />;
```
