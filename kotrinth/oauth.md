---
title: OAuth

template: base
---

> OAuth is going to be in Modrinth's v3 api which is currently
> under development, thus marking it experimental.

Using Modrinth's OAuth with Kotrinth.

## Setup Guide

### 1. Set Up the OAuth Class

```kotlin
package com.example

import me.theclashfruit.kotrinth.v2.Kotrinth
import me.theclashfruit.kotrinth.experimental.OAuth

suspend fun main() {
  // ...

  // Create a new OAuth instance.
  val oauth = OAuth(
    kotrinth,
    clientId = "...",
    clientSecret = "..."
  )
} 
```

### 2. Create the Auth Uri

```kotlin
package com.example

import me.theclashfruit.kotrinth.v2.Kotrinth
import me.theclashfruit.kotrinth.experimental.OAuth
import me.theclashfruit.kotrinth.enums.Scope

suspend fun main() {
  // ...
  
  // Create the uri.
  val uri = oauth.createAuthUrl(
    "https://example.com/api/auth",
    setOf(
      Scope.USER_READ_EMAIL,
      Scope.USER_READ,
      Scope.USER_WRITE
    )
  )
  
  // Print the uri.
  println(uri)
} 
```

### 3. Get the Auth Token

```kotlin
package com.example

import me.theclashfruit.kotrinth.v2.Kotrinth
import me.theclashfruit.kotrinth.experimental.OAuth
import me.theclashfruit.kotrinth.enums.Scope

suspend fun main() {
  // ...
  
  // Get the auth token.
  val res = oauth.token("https://example.com/api/auth", code)
  
  // Print the token.
  if (res != null) {
    println(res.accessToken)
  }
} 
```