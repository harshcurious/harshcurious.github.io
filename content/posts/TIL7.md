---
title: "TIL7"
date: 2021-04-12T10:12:57+05:30
draft: true

# weight: 1
# aliases: ["/first"]
tags: ["TIL", "notes"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Desc Text."

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: false
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page

plotly: false #turn plotly support on and off
mathjax: false #turn mathjax support on and off

---

## Banana Pi M5

- Learned of its existence from [Explaining Computers](https://youtu.be/ZZn30-b9Cj0).
- Has onboard eMMC storage.
- SOC: Amlogic S905X3 with 4 x A55 cores (up to 2GHz), Mali-G31 MP2 GPU.
- Can boot from 16 GB eMMC or SD Card slot.
- Uses USB-C for power (5V @ 2A) and eMMC setup.
- Has 4 switch (The wiki says 3 : Reset, Power and U-Boot 😕).
- 4 GB LPDDR4 RAM.
- 10/100/1000 Mbit/s Ethernet. Wi-Fi/Bluetooth requires an optional USB dongle.
- One HDMI 2.0 (up to 4K@60Hz with HDR, CEC, EDID)
- Audio via 3.5 mm  jack and HDMI.
- 4 x USB 3.0 ports.
- 3-pin UART connector and 40-pin GPIO connectors. Similar layout to Raspberry Pi.
- IR receiver.
- No Camera (CSI) or display (DSI) connector.
- Need to use an Amlogic burning tool to write to the built-in eMMC storage.
- Pre-built android, Ubuntu Mate, Ubuntu Server, Debian Buster, and CoreELEC image is available.
 