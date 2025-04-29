---
title: Data Driven GUIs

template: base
---

Developer docs for the Data Driven GUIs mod.

## Getting Started

### Import The Library

Add the repository and dependency to your `build.gradle.kts`:

<details>
  <summary>Stable (Releases Repo)</summary>

```kotlin
maven {
    name = "TheClashFruit's Maven Releases"
    url = uri("https://mvn.theclashfruit.me/releases")
}
```
</details>

<details>
  <summary>Beta, Alpha (Snapshots Repo)</summary>

```kotlin
maven {
    name = "TheClashFruit's Maven Snapshots"
    url = uri("https://mvn.theclashfruit.me/snapshots")
}
```
</details>

```kotlin
implementation("me.theclashfruit:ddg-$mc_version-fabric:$version")
```

## Creating a GUI

The menus are stored in `data/modid/screen/<menu_name>.xml` and the actions are stored in `data/modid/action/<action>.json`.

An example menu would look like this:
```xml
<Root> <!-- Evaluated like html and puts elements bellow one another. (Uhh I forgor so not yet™) -->
  <Button postion="(10;10)" width="100" height="20">Either a translation key or a string.</Button>
  <!--    ^^^^^^^^^^^^^^^^^ If a position is defined it fill be a "fixed" element. -->
  <Button action="modid:action">Another button</Button> <!-- The default button size is `200x20`. -->
  <!--    ^^^^^^^^^^^^^^^^^^^^^ Actions can be defined with action and the id for the action file. -->

  <Text>Some text</Text>
</Root>
```

> You can kind of think of it like a web page, where the root element is the body and the elements are like divs, buttons, inputs and paragraphs.

Some built in action types are:
* `ddg:open_menu` - Opens a menu.
<!--
* `ddg:close_menu` - Closes the current menu. &mdash; Can also be called directly from the menu.
* `ddg:run_command` - Runs a command.
-->

## Opening a Menu From a Server

**From a mod using the mod's api**:
```java
ServerPlayNetworking.send(player, new OpenCustomScreenPayload(Identifier.of("modid", "menu_name"), "title"));
```

**With a command with the mod installed**:
```plaintext
/ddg open <screen> <title> [<player>]

# Example:
/ddg open modid:screen/menu_name.xml "Title"
```