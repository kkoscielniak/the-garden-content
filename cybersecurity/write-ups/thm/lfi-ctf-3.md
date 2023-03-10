---
title: LFI CTF 3
weight: 3
---

[Link to the exercise](https://tryhackme.com/room/fileinc)

## Goal

Similarly to [[cybersecurity/write-ups/thm/lfi-ctf-1]] and [[cybersecurity/write-ups/thm/lfi-ctf-2]], the goal is to capture the flag at `/etc/flag3` using [[cybersecurity/knowledge/pentesting/LFI]].

## Steps

### Recon

Similarly to [[cybersecurity/write-ups/thm/lfi-ctf-1]], we're dealing with the PHP application that includes the file. In this case the file is provided as a `GET` query param.

I've tried several filenames to see if there's something worthy looking, only to get to know that everything that is not the letter is escaped (numbers, special characters and dots are filtered out of the string). so the `GET` parameter was a no go.

However, the hint suggested that the website uses PHPs' `$_REQUEST` to accept HTTP requests. I am not a PHP developer, but from the [docs](https://www.php.net/manual/en/reserved.variables.request.php) I got to know that `$_REQUEST` had contents of both `$_GET` and `$_POST` (and `$_COOKIE`, but that's doesn't matter here).

### Exploitation

I've ran Burp Suite to intercept the `GET` request sent from the website form and edited it to be `POST` one with `welcome2` as a string. Fortunately, with `POST`, the PHP code tried to include the file without filtering out the number (`2`).

So I've tried to include `/etc/flag3%00` (flag file with [[cybersecurity/knowledge/pentesting/null-byte]]) with success:

![[assets/Screenshot 2023-01-04 at 20.41.45 1.png]]

## Flag

`PP0st_1s_w0rk1in9`
