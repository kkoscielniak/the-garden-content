---
title: Burp Sequencer
---

_Sequencer_ allows us to measure the randomness of tokens.

Let's say we wish to analyse the randomness of a session cookie or a [CSRF](/knowledge/OffSec/glossary/CSRF.md)  token protecting a form submission. If it turns out that these tokens are not generated securely, then we can (in theory) predict the values of upcoming tokens. If the algorithm is not generating secure random values, then this could open up some devastating avenues for attack.