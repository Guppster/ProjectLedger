---
layout: post
title: "Redesigning a Crypto Library"
date: "2018-01-20 09:31:02 -0400"
---

In the past few weeks I have been dedicating my time to redesigning a JVM
library used to interact with the Ark Blockchain. The library handles many
cryptographic operations and was originally written in groovy. I redesigned it
in Kotlin with extra features, an improved test suite, and real documentation.
This post will explain how I feel about the non-functional elements of
a repository and the drastic effects of improving them.

### The Repository
Ark-Java is the JVM library that I was working on. It allows JVM applications
an easy interface with the Ark blockchain. While using this library in my IoT
infrastructure project I realized many big problems in this library which were
mostly the result of a poorly designed and small test suite. For example, the
library was testing it's functions using the live network which meant many
unpredictable network issues influenced the status of the build. The library
was also not being updated as often as issues were being fixed on master which
resulted in many people using outdated versions of the library.

### Groovy To Kotlin
Upon examining the code it was apparent why so many unexpected issues were
showing up. The library was designed more as a script and didn't expect the
user of the library to pass any illegal parameters. This issue was exaggerated
by the fact the library had no real documentation to provide users with
guidance. Essentially this made the library useless without reading the entire
code base and understanding it before hand.

### Unexpected Problems
One major problem I encountered after finishing the redesigned library was the
compatibility limitation enforced by kotlin coroutines. The library is intended
to be compatible with all JVM languages but when using the library in anything
other than Kotlin, the coroutine code was very hard to interact with. Since
almost all functions in the library are async using coroutines, this was a very
critical problem. A few possible solutions to this problem are: changing the
coroutine code to JVM futures (CompletableFuture), adding synchronous methods
as an alternative to avoid coroutines, and keeping this version for kotlin
projects and packaging a separate version for JVM projects.

Changing the code to utilize the CompletableFuture library instead of
coroutines for the async operations seems like the best solution to me. Perhaps
this could be combined with the idea of packaging a separate version for
Kotlin. Although, packaging two versions would double the amount of code to
maintain which is a sensitive topic for an open source organization with
limited developers like Ark.

Adding synchronous utility methods seems like a temporary fix because ideally
any large JVM project using this library will want to have async network
operations
