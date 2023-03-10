---
title: Burp Suite
---

_Burp Suite_ is a framework that is the industry standard tool for web app [[private/cybersec/pentesting/|pentesting]].

Burp Suite is also commonly used when assessing mobile applications, as the same features which make it so attractive for web app testing translate almost perfectly into testing the APIs powering most mobile apps.

Burp can capture and manipulate all of the traffic between an attacker and a webserver: this is the core of the framework. After capturing requests, we can choose to send them to various other modules of Burp. This ability to intercept, view, and modify web requests prior to them being sent to the target server (or, in some cases, the responses before they are received by our browser), makes Burp Suite perfect for any kind of manual web app testing.

There are various different editions of Burp Suite available:

- Burp Suite Community edition
  - free to use for any (legal) non-commercial use.
- Burp Suite Professional
  - unrestricted version of Burp Suite Community, has additional features:
    - automated vulnerability scanner
    - a fuzzer/bruteforcer that isn't rate limited
    - saving projects for future use
    - report generation
    - A built-in API to allow integration with other tools
    - unrestricted extensions support
    - Burp Suite Collaborator (a unique request catcher self-hosted/running on a Portswigger server)
    - $399/user/year
- Burp Suite Enterprise
  - used for automated, continuous scanning (periodically), similarly to how [[Nessus]] performs automated infrastructure scanning

## Burp Suite Community features

- [[cybersecurity/knowledge/tools/burp/proxy]]
- [[cybersecurity/knowledge/tools/burp/repeater]]
- [[cybersecurity/knowledge/tools/burp/intruder]]
- [[cybersecurity/knowledge/tools/burp/decoder]]
- [[cybersecurity/knowledge/tools/burp/comparer]]
- [[cybersecurity/knowledge/tools/burp/sequencer]]
- Extensions support through [[cybersecurity/knowledge/tools/burp/extender]] module

## See also

- [[cybersecurity/knowledge/tools/burp/configuration|Useful configuration settings]]
