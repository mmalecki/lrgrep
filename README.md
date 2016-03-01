# lrgrep
Helper script for `grep`ing log rotated files. Searches both the current and
log rotated files with the same base name.

## Installation
```sh
npm -g i lrgrep
```

## Usage
```
$ ls -l
-rw-r--r-- 1 ubuntu ubuntu 493345802 Mar  1 13:52 registry-frontdoor.log
-rw-r--r-- 1 ubuntu ubuntu 161932953 Mar  1 06:25 registry-frontdoor.log.1.gz
-rw-r--r-- 1 ubuntu ubuntu  93318881 Feb 29 06:25 registry-frontdoor.log.2.gz
-rw-r--r-- 1 ubuntu ubuntu  80401821 Feb 28 06:25 registry-frontdoor.log.3.gz
$ lrgrep foobar registry-frontdoor.log
registry-frontdoor.log:foobar
registry-frontdoor.log.2.gz:foobar
```

Where otherwise you'd have to call `grep` and `zgrep` separately like:

```sh
$ grep foobar registry-frontdoor.log
foobar
$ zgrep foobar registry-frontdoor.log.*.gz
registry-frontdoor.log.2.gz:foobar
```
