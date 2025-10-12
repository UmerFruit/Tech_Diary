---
title: "charge limits on linux"
date: 2025-10-12 7:00:00 +0500
categories: [Setup]
tags: [environment,learning]
---
Keeping your laptop battery healthy on Linux is easy: use tlp to enable battery conservation or set charge thresholds.

1-minute steps

- Install tlp (Debian/Ubuntu):

```bash
sudo apt update
sudo apt install tlp
sudo systemctl enable --now tlp
```

- Edit the configuration:

```bash
sudo nano /etc/tlp.conf
# look for START_CHARGE_THRESH_BAT0 and STOP_CHARGE_THRESH_BAT0
```

- Check what your hardware supports:

```bash
tlp-stat -b
```

Look for a line like:

Parameter value range:
* STOP_CHARGE_THRESH_BAT0: 0(off), 1(on) -- battery conservation mode

If your machine supports only 0/1 then setting

STOP_CHARGE_THRESH_BAT0=1

will enable conservation mode (on Lenovo/Ideapad this writes to a kernel driver file). For hardware that supports numeric thresholds you can set values like `START_CHARGE_THRESH_BAT0=40` and `STOP_CHARGE_THRESH_BAT0=80`.

- Apply and verify:

```bash
sudo tlp start
sudo tlp-stat -s -c -b
# you should see "Battery Care" / "conservation_mode = 1" or your configured thresholds
```

Notes

- tlp applies settings at boot when the service is enabled. If a vendor kernel module (eg. `ideapad_laptop`) is used, `tlp` will toggle the driver's conservation_mode.
- If you see only on/off support, use the safe default (enable conservation). If thresholds are supported, pick conservative numbers (40–80%).
- Always double-check `tlp-stat -b` output before changing settings.

That's it — a quick way to reduce long-term battery wear on Linux.