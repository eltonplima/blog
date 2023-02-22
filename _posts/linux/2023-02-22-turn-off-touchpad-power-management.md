---
title:  "How turn off touchpad power management"
date:   2023-02-22 14:23:21 +0100
categories: Linux
layout: post
---

Add a new systemd service:

```shell
sudo vim /etc/systemd/system/disable-touchpad-pm.service
```

With the following content:

```shell
[Unit]
Description=disables Acer aspire v3 572g touchpad PM to work around input delays

[Service]
Type=oneshot
ExecStart=/bin/sh -c "echo on > /sys/bus/i2c/devices/i2c-0/device/power/control"

[Install]
WantedBy=multi-user.target
```

then execute

```shell
sudo systemctl daemon-reload && sudo systemctl enable disable-touchpad-pm
```
