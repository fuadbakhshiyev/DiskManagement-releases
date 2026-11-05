# DiskManagement downloads

DiskManagement is a disk analyzer and cleaner for macOS, Windows and Linux. It shows what takes up space on your disk and helps you clean it safely: nothing is removed until you review it in the Basket, and removed items go to the Trash or Recycle Bin by default.

**[Download the latest release](https://github.com/fuadbakhshiyev/DiskManagement-releases/releases/latest)**

> **0.0.1 is an unsigned test build.** It is meant for testers. macOS and Windows will warn you before the first launch; the steps below show how to get past the warning. Only send small, throwaway test files to the Trash or Recycle Bin, and do not use **Delete permanently** or **Empty Trash** in this build.

## Which file do I need?

| Your system | File |
|---|---|
| macOS 26 or later (Apple Silicon and Intel, universal) | `DiskManagement-0.0.1-mac.dmg` |
| Windows 10/11 x64 (recommended) | `DiskManagement-0.0.1-windows-x64-setup.exe` |
| Windows 10/11 x64 (alternative) | `DiskManagement-0.0.1-windows-x64.msi` |
| Linux x86_64, any distribution (portable) | `DiskManagement-0.0.1-linux-x86_64.AppImage` |
| Ubuntu 22.04+, Debian and derivatives, amd64 | `DiskManagement-0.0.1-linux-amd64.deb` |

The Linux builds need the **WebKitGTK 4.1** runtime. Most current desktop distributions already include it, and the `.deb` installs it for you.

## Install

### macOS

1. Open the DMG and drag **DiskManagement** to **Applications**.
2. Open DiskManagement from Applications. macOS will say it "cannot verify" the app. Click **Done** (not "Move to Trash").
3. Open **System Settings → Privacy & Security**, scroll down to the message about DiskManagement and click **Open Anyway**. Confirm with your password or Touch ID.
4. Open the app again and click **Open** when asked.

For complete scan totals, give the app **Full Disk Access** in **System Settings → Privacy & Security → Full Disk Access**, then quit and reopen it. This test build is ad-hoc signed, so you have to grant Full Disk Access again after installing a newer test build.

### Windows

1. Run `DiskManagement-0.0.1-windows-x64-setup.exe` (or the MSI).
2. SmartScreen will show "Windows protected your PC". Click **More info → Run anyway**.
3. The app needs the Microsoft Edge WebView2 runtime. Windows 11 already has it; otherwise the installer downloads it, so stay online during installation.
4. Start DiskManagement from the Start menu.

### Linux: AppImage

```bash
chmod +x DiskManagement-0.0.1-linux-x86_64.AppImage
./DiskManagement-0.0.1-linux-x86_64.AppImage
```

If it fails with an error about FUSE (`libfuse.so.2`), install FUSE 2: `sudo apt install libfuse2` (Ubuntu 22.04 / Debian) or `sudo apt install libfuse2t64` (Ubuntu 24.04 and later).

### Linux: .deb (Ubuntu 22.04+, Debian, Mint, Pop!_OS)

```bash
sudo apt install ./DiskManagement-0.0.1-linux-amd64.deb
```

`apt` installs the dependencies, including WebKitGTK 4.1. Start DiskManagement from the app menu. To remove it:

```bash
sudo apt remove disk-management
```

## Check the download (SHA-256)

Download `SHA256SUMS` from the same release into the folder with your file, then run:

```bash
shasum -a 256 -c SHA256SUMS --ignore-missing     # macOS
sha256sum -c SHA256SUMS --ignore-missing         # Linux
```

On Windows (PowerShell), compare the output with the line for your file in `SHA256SUMS`:

```powershell
Get-FileHash .\DiskManagement-0.0.1-windows-x64-setup.exe -Algorithm SHA256
```

## Known limitations of 0.0.1

- The builds are not code-signed yet.
- Windows and Linux are Beta and have fewer features than the Mac app.
- There is no auto-update. Download new test builds from the [releases page](https://github.com/fuadbakhshiyev/DiskManagement-releases/releases).
