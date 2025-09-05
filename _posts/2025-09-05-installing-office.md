---
title: "Installing Office"
date: 2025-09-05 7:00:00 +0500
date: 2025-09-05 7:00:00 +0500
categories: [Setup]
tags: [environment, tools]
---
# Manual to install MS office

### Install qBittorrent:

1. Go to: [https://sourceforge.net/projects/qbittorrent/files/qbittorrent-win32/](https://sourceforge.net/projects/qbittorrent/files/qbittorrent-win32/)
2. Click **Download latest version** button.
3. **Quickly** click **Problems downloading** and select **Auto-select** under *choose a different mirror*.
4. All the defaults are good, so just click **Next** and install. (You may choose other options if you know what you are doing.)

---

### Installing Office:

1. Go to: [https://www.teamos.xyz/](https://www.teamos.xyz/)

2. Click **Login** and use these credentials:

    <Redacted>

    or make your own account using **Sign Up**.

3. Click **Torrents**.

4. Search for **Microsoft Office**.

5. Click the **green up arrow** in the middle right to sort by *seeders*. (This just means you get better download speeds.)

6. At the time of writing, my top result was:

   **Microsoft Office Professional Plus 2024 VL 2408 Build 17928.20082 (x86 x64) Final *TeamOS* by Mr Spacely**
   His builds are really good and reliable; I’ve been using them for a long time without issues.

   > If you have an older laptop that might not run this latest Office build, or if you face laggy system issues, try a previous year’s build using the same process. Hopefully you’ll find the right one for your system.

7. With that top result, click the small **green u icon** to the right of the torrent name. This will download a `.torrent` file.

8. In your **Downloads** folder, double-click the `.torrent` file. It should open in **qBittorrent**.

9. Click **Next** to any dialog box that might appear.

10. Wait until the download finishes.

---

### Extracting the Files:

1. The download should be a `.7z` file.

   * (If not, you’ll need to figure out installation for your specific application.)
2. Before extracting:

   * Press **Windows key** → search **Virus & Threat Protection**.
   * Under *Virus & Threat Protection settings*, click **Manage settings**.
   * Scroll down → under *Exclusions*, click **Add or remove exclusions**.
   * Add an **exclusion** for the folder where you downloaded the `.7z` file.
   * *(Reason: Antivirus removes some files it thinks are viruses. To the best of my knowledge, these are safe and tested. Still, cracked software = your own risk.)*
3. Make a **new empty folder**.
4. Move the `.7z` file into this folder.
5. Download **7-Zip** from: [https://www.7-zip.org/](https://www.7-zip.org/)

   * Install it (Windows version, run `.exe`).
6. Right-click the **MS Office file** → `7-Zip > Extract Here`.

---

### Installing and Activating Office:

1. Run the **Setup**.

2. After setup, Office will be installed (verify by pressing Windows key and typing *Word*).

3. Office is installed but **not activated**. To activate:

   * Extract the `activator.zip` (comes with Office setup).
   * Run the activator file.
   * Click **Yes**.
   * If **Defender blocks this**:

     * Press **Windows key** → search **Virus & Threat Protection**.
     * Under *Virus & Threat Protection settings*, **disable real-time protection** temporarily.
   * Run the file again.
   * Click **Yes**, then **Start**.
   * *(Fun fact: This activator can also activate Windows as well as Office.)*

4. **Well done, you have activated Office (and optionally Windows).**

---
