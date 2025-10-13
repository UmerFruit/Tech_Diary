---
title: "Installing Windows"
date: 2025-10-13 7:00:00 +0500
categories: [Setup]
tags: [windows, installation, tools]
---
# Manual to install Windows

### Install qBittorrent:

1. Go to: [https://sourceforge.net/projects/qbittorrent/files/qbittorrent-win32/](https://sourceforge.net/projects/qbittorrent/files/qbittorrent-win32/)
2. Click **Download latest version** button.
3. **Quickly** click **Problems downloading** and select **Auto-select** under *choose a different mirror*.
4. All the defaults are good, so just click **Next** and install. (You may choose other options if you know what you are doing.)

---

### Downloading Windows ISO:

1. Go to: [https://www.teamos.xyz/](https://www.teamos.xyz/)

2. Make your own account using **Sign Up**.

3. Click **Torrents**.

4. Search for **Windows 11** (or **Windows 10** if you prefer).

5. Click the **green up arrow** in the middle right to sort by *seeders*. (This just means you get better download speeds.)

6. Look for a proper full OS, not Lite or other custom builds. Get the right Pro version. For me I preferred this ISO, but yours may be a newer version in the future:

   **Windows 11 Professional 24H2 26100.4656 EN-US X64 Bypassed & Pre-activated -=TeamOS=- by Dark Wolf**
   His builds are really good and reliable; I've been using them for a long time without issues.

   > If you have an older laptop that might not run the latest Windows 11, try Windows 10 or an earlier Windows 11 build using the same process. Check your system requirements first.

7. With that top result, click the small **green u icon** to the right of the torrent name. This will download a `.torrent` file.

8. In your **Downloads** folder, double-click the `.torrent` file. It should open in **qBittorrent**.

9. Click **Next** to any dialog box that might appear.

10. Wait until the download finishes.

---

### Extracting the ISO:

1. The download should be a `.7z` file containing the Windows ISO.

2. Before extracting:

   * Press **Windows key** → search **Virus & Threat Protection**.
   * Under *Virus & Threat Protection settings*, click **Manage settings**.
   * Scroll down → under *Exclusions*, click **Add or remove exclusions**.
   * Add an **exclusion** for the folder where you downloaded the `.7z` file.
   * *(Reason: Antivirus removes some files it thinks are viruses. To the best of my knowledge, these are safe and tested. Still, cracked software = your own risk.)*
3. Download **7-Zip** from: [https://www.7-zip.org/](https://www.7-zip.org/)

   * Install it (Windows version, run `.exe`).
4. Right-click the **Windows `.7z` file** → `7-Zip > Extract Here`.

5. You should now have a `.iso` file.

---

### Creating Bootable USB with Rufus:

1. Get a **USB drive** (at least 8GB, preferably 16GB or more).

   * **Warning: All data on this USB will be erased.**
2. Download **Rufus** from: [https://rufus.ie/](https://rufus.ie/)

   * Click **Rufus (portable version)** for a no-install option.
3. Run **Rufus**.

4. Under **Device**, select your **USB drive**.

5. Under **Boot selection**, click **SELECT** and choose your **Windows `.iso` file**.

6. Make sure the following options are selected:

   * **Partition scheme:** GPT
   * **Target system:** UEFI (non-CSM) — or UEFI
   * **File system:** NTFS

   Rufus usually auto-detects these, but confirm them before clicking **START**.

7. Click **START**.

8. If prompted about ISO Image or DD Image mode, choose **ISO Image mode**.

9. If a compatibility/pop-up appears asking about TPM, Secure Boot, or hardware checks (Rufus may warn Windows 11 requires TPM 2.0 / Secure Boot):

    * Choose the option to **Disable checks** or **Proceed (bypass)** in Rufus if available.
    * If Rufus doesn't offer a bypass, you will need to **disable TPM and Secure Boot** temporarily in your PC's BIOS/UEFI before installing.
    * Common BIOS locations:
       * Security → TPM or PTT (Intel) or fTPM (AMD) — set to **Disabled** or **Off**
       * Boot → Secure Boot — set to **Disabled**
       * Save and Exit, then retry booting the USB.

    * Note: Re-enable TPM and Secure Boot after installation if you want them active.

10. If asked to download additional files, click **Yes**.

11. Wait for Rufus to finish creating the bootable USB.

---

### Accessing BIOS and Boot Menu:

**Different laptop brands use different keys to access BIOS and Boot Menu. Here are the common ones:**

| Brand | BIOS Key | Boot Menu Key |
|-------|----------|---------------|
| **HP** | `Esc` then `F10` | `Esc` then `F9` |
| **Dell** | `F2` | `F12` |
| **Lenovo** | `F2` or `Fn + F2` | `F12` |
| **Acer** | `F2` or `Del` | `F12` |
| **Asus** | `F2` or `Del` | `Esc` or `F8` |
| **MSI** | `Del` | `F11` |
| **Gigabyte** | `Del` | `F12` |
| **Toshiba** | `F2` | `F12` |
| **Samsung** | `F2` | `Esc` or `F12` |

> **Tip:** Press the key repeatedly right when you turn on your laptop.

---

### Installing Windows:

1. **Insert the bootable USB** into your laptop.

2. **Restart** your computer.

3. As soon as the manufacturer logo appears, press the **Boot Menu key** for your brand (see table above).

4. From the Boot Menu, select your **USB drive**.

   * It might be listed as:
     * `USB HDD`
     * `UEFI: [Your USB Name]`
     * `Removable Device`
     * Or by the USB brand name (e.g., `SanDisk`, `Kingston`)
5. Press **Enter**.

6. The **Windows installation screen** will appear.

**That's it! Follow the on-screen prompts to install Windows from here.**

---
