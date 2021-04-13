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

- Learned of its existence from [Explaining Computers](https://youtu.be/ZZn30-b9Cj0)
  {{<youtube ZZn30-b9Cj0>}}
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
- Pre-built android, Ubuntu Mate, Ubuntu Server, Debian Buster, and CoreELEC images are available.
 
 ## The Quick Way to Display System and Shell Information in Powershell on Windows 10

 - I have added the following to my `$Profile`:
    
    ```powershell
    Write-Host @"
    ______________________________________________________________
      __          ___           _                     __  ___  
      \ \        / (_)         | |                   /_ |/ _ \ 
       \ \  /\  / / _ _ __   __| | _____      _____   | | | | |
        \ \/  \/ / | | '_ \ / _` |/ _ \ \ /\ / / __|  | | | | |
         \  /\  /  | | | | | (_| | (_) \ V  V /\__ \  | | |_| |
          \/  \/   |_|_| |_|\__,_|\___/ \_/\_/ |___/  |_|\___/ 

      ____    ___       ______ _ _     _   _                      
     / ___|  /   |      | ___ (_) |   | | | |                     
    / /___  / /| |______| |_/ /_| |_  | |_| | ___  _ __ ___   ___ 
    | ___ \/ /_| |______| ___ \ | __| |  _  |/ _ \| '_ ` _ \ / _ \
    | \_/ |\___  |      | |_/ / | |_  | | | | (_) | | | | | |  __/
    \_____/    |_/      \____/|_|\__| \_| |_/\___/|_| |_| |_|\___|
                                                                  
                                                                  
    "@ -ForegroundColor Green

    $operatingsystem = Get-CimInstance -ClassName CIM_OperatingSystem

    Write-Host "Version: $($operatingsystem.Version)`n" -ForegroundColor Green
    Write-Host "Last Boot-up time for $($operatingsystem.CSName): $($operatingsystem.LastBootUpTime)" -ForegroundColor Green
    Write-Host "______________________________________________________________`n -ForegroundColor Green"
    Write-Host "PowerShell version: $($PSVersionTable.PSVersion)" -ForegroundColor Red
    Write-Host "______________________________________________________________`n -ForegroundColor Green"

    ```
    Now when I start my PowerShell I am greeted by the following:
    ![New Terminal](/static/TIL/7/WindowsTerminal.png)


- There are other options like `Get-ComputerInfo` and `Get-WinEvent`(depreceated from PowerShell 6 onwards). This one worked best for me. YMMV.
- I genenerated the ASCII art from [this tool](https://textkool.com/en/ascii-art-generator)
- Learned a fair bit of PowerShell scripting today. I think can understand a PowerShell script now. 
