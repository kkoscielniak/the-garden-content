---
title: Burp Proxy
weight: 1
---

_Burp Proxy_ allows us to intercept and modify requests/responses between
ourselves and the target when interacting with web apps. These can then be manipulated or sent to other tools for further processing before being allowed to continue to their destination.

We can also do various other things with the request, such as

- copying it as a cURL command
- saving it to a file
- etc.

Burp will (by default) log requests made through the proxy, no matter if the intercept is on/off. Useful for going back and analysing prior requests, even if we didn't specifically capture them when they were made.

Burp will also log WebSocket communication, which can be helpful for web app analysis.

Requests can be sent to other modules through _HTTP/Websocket history_ -> _Right-click_ -> _Send to..._

## Proxy Options

### Intercept responses based on the following rules

The proxy will not intercept server responses by default unless we explicitly ask it to on a per-request basis. We can override this by selecting the _Intercept responses based on the following rules_.

The _Or Request Was Intercepted_ rule is good for catching responses to all requests that were intercepted by the proxy.

The _And URL Is in target scope_ is another very good default rule; we will look at scoping later in this room.

We can also make our own rules.

### Match And Replace

_Match And Replace_ section allows us to perform regexes on incoming and outgoing requests, eg. we can automatically change the user agent to emulate a different web browser in outgoing requests or remove all cookies being set in incoming requests.

We can also make our own rules.

## Connecting through the Proxy

There are two ways to proxy our traffic through Burp Suite:

- using the embedded browser
- using our local browser to proxy our traffic through Burp

### using embedded browser

`/* [...] */`

### using local browser

The Burp Proxy works by opening a web interface on `127.0.0.1:8080` (by default). We need to redirect all of our browser traffic through this port so we can start intercepting it.

We can do this by altering our browser settings (not recommended) or with a [FoxyProxy Basic](https://chrome.google.com/webstore/detail/foxyproxy-basic/dookpfaalaaappcdneeahomimbllocnb) extension.

We need to create Burp Proxy config in FoxyProxy and enable this proxy setting:

```
Title: Burp (or anything else)
Proxy IP: 127.0.0.1
Port: 8080
```

From now on we can intercept requests made by our browser.

## Intercepting Responses to particular requests

_HTTP History_ -> _Right-Click_ -> _Do Intercept_ -> _Response to this Request_
