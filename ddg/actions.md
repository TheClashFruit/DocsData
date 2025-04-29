---
title: Actions

template: base
---

An action looks something like this:

```json
{
  "type": "ddg:open_screen",
  "action": {
    "screen": "ddg:screen/example.xml",
    "title": "Hello, World!"
  }
}
```

### Advanced

#### Actions with Classes (Coming Soon™)

You can call classes that implement `JavaAction`. This is useful for actions that require more complex logic or state.

Example:
```json
{
  "type": "ddg:java_action",
  "parent": "ddg:editbox_value",
  "action": {
    "class": "me.theclashfruit.ddg.example.EditBoxValueAction"
  }
}
```

`EditBoxValueAction.java`:
```java
package me.theclashfruit.ddg.example;

import java.util.HashMap;
import java.util.Map;

import me.theclashfruit.ddg.api.action.JavaAction;

public class EditBoxValueAction implements JavaAction {
    @Override
    public Map<String, Runnable> getFields() {
        Map<String, Runnable> action = new HashMap<>();
        action.put("returns", () -> "Hello World!");

        return action;
    }
}
```