---
title: TabLayout

template: base
---

A layout for arranging components in a tabbed interface.

> Note: Not yet available. This is a work in progress and will be available in a future release.

## Example

```xml
<TabLayout>
  <Tabs>
    <Tab id="one">Tab 1</Tab>
    <Tab id="two">Tab 2</Tab>
  </Tabs>
  <Pages>
    <HorizontalLayout id="one">
      <Text>Content for Tab 1</Text>
    </HorizontalLayout>
    <VerticalLayout id="two">
      <Text>Content for Tab 2</Text>
    </VerticalLayout>
  </Pages>
</TabLayout>
```

> **Note**: `Tabs` and `Pages` are so called "[descriptor](/ddg/components/#descriptor-components)" components and thus can only be used inside of `TabLayout`.

## Attributes

| Attribute | Type         | Description                                 |
|-----------|--------------|---------------------------------------------|
| `position`| `(int; int)` | The position of the layout in the menu.     |
| `gap`     | `int`        | The gap between the elements in the layout. |

\* Required.