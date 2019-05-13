---
id: overview
title: Overview
---

## Forms components

Most of the time you'll be using either `AutoForm` or `ValidatedForm`, but there are also other form components (rather low-level ones) with different capabilities.

|      Component       |     Self-generated?      |      Self-managed?       |     Self-validated?      |
| :------------------: | :----------------------: | :----------------------: | :----------------------: |
|      `AutoForm`      |    :heavy_check_mark:    |    :heavy_check_mark:    |    :heavy_check_mark:    |
|      `BaseForm`      | :heavy_multiplication_x: | :heavy_multiplication_x: | :heavy_multiplication_x: |
|     `QuickForm`      |    :heavy_check_mark:    | :heavy_multiplication_x: | :heavy_multiplication_x: |
|   `ValidatedForm`    | :heavy_multiplication_x: | :heavy_multiplication_x: |    :heavy_check_mark:    |
| `ValidatedQuickForm` |    :heavy_check_mark:    | :heavy_multiplication_x: |    :heavy_check_mark:    |

## Fields components

This is a guaranteed set of fields - every theme package will implement these, but also can provide additional ones.

|    Component    |                   Description                   |
| :-------------: | :---------------------------------------------: |
|   `AutoField`   |      Automatically renders a given field.       |
|  `AutoFields`   |       Automatically renders given fields.       |
|   `BoolField`   |                    Checkbox.                    |
|   `DateField`   |          HTML5 `datetime-local` input.          |
|  `ErrorField`   |        Error message for a given field.         |
|  `ErrorsField`  | Error message with a list of validation errors. |
|  `HiddenField`  | Hidden field (with possibility to omit in DOM). |
| `ListAddField`  |     An icon with action to add a list item.     |
| `ListDelField`  |   An icon with action to remove a list item.    |
|   `ListField`   |             List of nested fields.              |
| `ListItemField` |            Single list item wrapper.            |
| `LongTextField` |                    Textarea.                    |
|   `NestField`   |             Block of nested fields.             |
|   `NumField`    |                 Numeric input.                  |
|  `RadioField`   |                 Radio checkbox.                 |
|  `SelectField`  |      Select (or set of radio checkboxes).       |
|  `SubmitField`  |                 Submit button.                  |
|   `TextField`   |      Text (or any HTML5 compatible) input.      |
