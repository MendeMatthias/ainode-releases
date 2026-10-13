# AInode for Mac

**Open AI models, fetched over the BTX model network, checked piece by piece,
and run on your own Mac. No account. Nothing you type leaves your Mac.**

This repository holds the signed downloads and their release notes. Feedback
is welcome in [Issues](../../issues), or in the BTX chat (reach it from
[@btx_ecosystem](https://t.me/btx_ecosystem)).

## Download

The latest version is on the [Releases](../../releases/latest) page:
`AInode-<version>.dmg`, for Apple Silicon Macs (M1 or newer) on macOS 13 or later.
It is signed with a Developer ID and notarized by Apple, so it opens without
a warning. Each release lists the file's SHA-256: compare it with

```bash
shasum -a 256 ~/Downloads/AInode-*.dmg
```

## What it does

1. **You choose how much disk it may use.** Nothing is written before that.
2. **Start.** It runs the BTX model engine (`btx-modeld` from the official BTX
   release, unmodified) with post-quantum TLS. It never listens on the network
   and never shares what it downloads.
3. **Get a model from the store.** A model is a `btx://` link that names its
   exact bytes. It arrives in 4 MiB pieces, each checked before it is kept.
   Today: IBM Granite 4.2 3B (any Mac), Qwen3 8B (16 GB), OpenAI gpt-oss 20B
   (24 GB), all Apache-2.0.
4. **Chat.** The model runs on your Mac with llama.cpp. It can look things up
   offline (BTX's own docs, an encyclopedia) and in files you add.

AInode only downloads. It never serves, pays or earns. "Checked" means the
bytes are intact, not that a model is safe or correct: read each model's licence.

## Why

BTX has a native network for AI models: anyone can host one, anyone can fetch
it, and every piece is verified. AInode is a simple way to use it, and a first
step towards the rest of BTX's plan: bounties that pay for models people want,
and campaigns that release them openly. The first bounty, 5 BTX for a model
that explains BTX correctly, is here:
[MendeMatthias/btx-bounty-1](https://github.com/MendeMatthias/btx-bounty-1).

## Licence

AInode is MIT-licensed. It bundles third-party software under its own licences
(listed in each release's notes): BTX `btx-modeld` (MIT), llama.cpp (MIT),
OpenSSL (Apache-2.0), pdf.js (Apache-2.0), Tauri (MIT or Apache-2.0), and an
offline encyclopedia from Wikipedia (CC BY-SA 4.0). AInode is not affiliated
with the BTX developers, IBM, Alibaba, OpenAI or Mozilla.
