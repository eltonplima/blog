---
title:  "Useful tools for Erlang and Elixir"
date:   2021-05-05 13:44:21 +0100
categories: Erlang and Elixir
layout: post
---

# Useful tools and commands

## perf
```shell
apt-get install linux-tools-common linux-tools-generic linux-tools-`uname -r`
```
```shell
sudo perf top -p `pgrep beam`
```

# References

* http://www.brendangregg.com/perf.html
* https://www.youtube.com/watch?v=OR2Gc6_Le2U
