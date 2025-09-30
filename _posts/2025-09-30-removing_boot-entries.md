---
title: "Removing EFI Entries"
date: 2025-09-30 7:00:00 +0500
categories: [General]
tags: [environment,learning]
---
# Removing Ubuntu UEFI Boot Entries Permanently

If you uninstalled Ubuntu but its entry still shows in the UEFI boot menu, here are two reliable methods to remove it.

---

## Method 1 – Delete EFI Partition and Bootloader Entry

### Step 1 – Delete Ubuntu EFI Partition with Diskpart

Open **Command Prompt (Admin)** and run:

```bash
diskpart
list disk
select disk <number>
list partition
select partition <number>   # EFI/Ubuntu partition (100–500MB FAT32)
delete partition override
exit
```

This deletes the EFI partition where Ubuntu stored its bootloader files.

### Step 2 – Delete Bootloader Entry with BCDEdit

Still in Command Prompt:

```bash
bcdedit /enum firmware
```

Find the entry labeled **Ubuntu**, note its **identifier** (GUID like `{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}`), and remove it:

```bash
bcdedit /delete {identifier}
```

This clears the UEFI boot manager entry.

---

## Method 2 – Remove Only Ubuntu Folder from EFI Partition

### Step 1 – Mount EFI Partition

```bash
diskpart
list disk          # check available disks
select disk 0      # usually your primary system disk
list partition     # shows partitions
select partition 1 # example: EFI System Partition
assign letter=x    # mounts EFI as drive X:
exit
```

### Step 2 – Navigate and Delete Ubuntu EFI Files

```bash
x:                 # switch to EFI partition
dir
cd efi
dir                # list folders (Windows, Boot, Ubuntu, etc.)
rd ubuntu /S       # delete Ubuntu folder recursively
y                  # confirm deletion
```

This method keeps the EFI partition but removes only the **Ubuntu folder** inside it.

---

## Explanation

* **Method 1** completely deletes the Ubuntu EFI partition and its boot entry. Use this if the partition was created on a seperate drive **from windows**. If deleted with windows inside, the windows will **NOT BOOT**.
* **Method 2** mounts the EFI system partition, navigates inside, and deletes only the `ubuntu` folder. Use this if you share the EFI partition with Windows (common on most dual-boot setups).
* **BCDEdit** ensures leftover boot entries pointing to non-existent files are removed.

Both methods ensure the Ubuntu entry disappears from your BIOS/UEFI boot menu permanently.
