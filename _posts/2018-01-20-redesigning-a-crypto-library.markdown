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

