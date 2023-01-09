---
title: "Screenshots via SSH"
---

To take a screenshot of another X session running:

```sh
DISPLAY=:0 scrot
```

To download the screenshot via `scp`:

```sh
scp username@hostname:/path/to/remote/file /path/to/local/file
```

Useful with [[linux/pocketchip/|Pocket C.H.I.P.]]
