---
title:  "How to install Erlang 24 with asdf on Manjaro"
date:   2022-03-12 19:37:21 +0100
categories: Erlang and Elixir
layout: post
---

# The problem

I was trying to install erlang 24 with asdf on Manjaro and saw the following warning.

```shell
APPLICATIONS INFORMATION (See: /home/eltonplima/.asdf/plugins/erlang/kerl-home/builds/asdf_24.3/otp_build_24.3.log)
 * wx             : wxWidgets was not compiled with --enable-webview or wxWebView developer package is not installed, wxWebView will NOT be available
 *         wxWidgets must be installed on your system.
 *         Please check that wx-config is in path, the directory
 *         where wxWidgets libraries are installed (returned by
 *         'wx-config --libs' or 'wx-config --static --libs' command)
 *         is in LD_LIBRARY_PATH or equivalent variable and
 *         wxWidgets version is 3.0.2 or above.
```

# The solution

1. Install base-devel `sudo pacman -Syu base-devel`
2. Install `wxgtk3-dev` with `pamac install wxgtk3-dev`
