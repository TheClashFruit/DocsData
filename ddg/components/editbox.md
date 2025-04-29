---
title: EditBox

template: base
---

An edit box for entering text.

## Example

```xml
<EditBox id="config" width="300" height="200" placeholder="Enter you thoughts here..." />
```

## Attributes

| Attribute      | Type                     | Description                               |
|----------------|--------------------------|-------------------------------------------|
| `position`     | `(int; int)`             | The position of the edit box in the menu. |
| `id`           | `string`                 | The id of the edit box.                   |
| `width`*       | `int`                    | The width of the edit box in pixels.      |
| `height`*      | `int`                    | The height of the edit box in pixels.     |
| `placeholder`* | `string`                 | The placeholder text for the edit box.    |
| `value`        | `string` or `action`[^1] | The default value of the edit box.        |

\* Required.

---

[^1]: An action that inherits from `ddg:editbox_value` can be used to set the value of the edit box. The action must return a string.