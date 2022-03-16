---
title:  "Useful tools and libraries for Erlang and Elixir"
date:   2021-05-05 13:44:21 +0100
categories: Erlang and Elixir
layout: post
---

# Useful tools and libraries for Erlang and Elixir

## erlang.mk

erlang.mk is [a build tool for Erlang that just works](https://erlang.mk/guide/getting_started.html)

## perf
```shell
apt-get install linux-tools-common linux-tools-generic linux-tools-`uname -r`
```
```shell
sudo perf top -p `pgrep beam`
```

## test

[mix test.interactive](https://github.com/influxdata/mix_test_interactive)

# References

* http://www.brendangregg.com/perf.html
* https://www.youtube.com/watch?v=OR2Gc6_Le2U
