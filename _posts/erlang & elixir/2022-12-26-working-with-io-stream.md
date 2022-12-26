---
title:  "How to use IO.Stream to test streams"
date:   2022-12-26 08:05:21 +0100
categories: Erlang and Elixir
layout: post
---

```elixir
# https://elixirforum.com/t/send-stringio-to-stream/31404/2
{:ok, pid} = StringIO.open("my stream content\nwith multiple lines")
IO.binstream(pid, :line)
|> YourModule.i_need_a_stream()
```
