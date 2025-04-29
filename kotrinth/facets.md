---
title: Facets

template: base
---

Modrinth uses their so-called facets for filtering search results.

### Usage

```kotlin
package com.example

import me.theclashfruit.kotrinth.v2.Kotrinth
import me.theclashfruit.kotrinth.util.Facet
import me.theclashfruit.kotrinth.enums.ProjectType
import me.theclashfruit.kotrinth.enums.Operation

suspend fun main() {
  // ...

  val facets = Facet.builder()
    .and(Facet.ProjectType, ProjectType.Mod)
    .or(Facet.Version, "1.20", "1.20.1")
    .exclude(Facet.Category, "forge")
    .op(Facet.Downloads, Operation.GreaterOrEqual, 10)
    .build()
    
  println(kotrinth.search(
    facets = facets
  ))
}
```