---
id: bridges-json-schema
title: JSON Schema
---

```js
import Ajv from 'ajv';
import {JSONSchemaBridge} from 'uniforms-bridge-json-schema';

const schema = {
  title: 'Person',
  type: 'object',
  properties: {
    firstName: {
      type: 'string'
    },
    lastName: {
      type: 'string'
    },
    age: {
      description: 'Age in years',
      type: 'integer',
      minimum: 0
    }
  },
  required: ['firstName', 'lastName']
};

const validator = new Ajv({allErrors: true, useDefaults: true}).compile(schema);

const schemaValidator = model => {
  validator(model);

  if (validator.errors && validator.errors.length) {
    throw {details: validator.errors};
  }
};

const bridge = new JSONSchemaBridge(schema, schemaValidator);

// Later...

<ValidatedForm schema={bridge} />;
```
