---
title: Search

template: base
---

Modrinth's search is quite robust but a bit complex.

### Usage

```kotlin
package com.example

import me.theclashfruit.kotrinth.v2.Kotrinth
import me.theclashfruit.kotrinth.enums.Sort

suspend fun main() {
  // ...
    
  println(kotrinth.search(
    query = "create mod",
    [[[facets = facets]]](/kotrinth/facets),
    index = Sort.Relevance,
    offset = 0,
    limit = 25
  ))
}
```