---
title:  "How to disable Ecto logging"
date:   2022-06-21 06:09:21 +0100
categories: Erlang and Elixir
layout: post
---

Sometimes ecto debug logging flood our terminal and this make us to waste more time
than the necessary to find what we need. The solution that I use on my daily basis
is basically disable the ecto logging.

```elixir
# config/dev.exs
config :my_app, MyApp.Repo,
  log: false
```
