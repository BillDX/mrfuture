---
title: "Inside Voice"
date: 2026-09-13
url: /inside-voice/
layout: product
featured: true
icon: vacuum-tube
kicker: "Now in every modern home"
burst: "Free! For your Mac!"
summary: "Talk instead of type, on your Mac. Hold one key, say what you mean, let go: your words appear wherever you were typing. Nothing you say ever leaves your computer."
requirements: "For Macs with Apple Silicon (M1 or newer) on macOS 14 or later. Free for everyone, including at work."
status: shipped
download: "https://github.com/BillDX/InsideVoice/releases/latest/download/InsideVoice.dmg"
repo: "https://github.com/BillDX/InsideVoice"
tags: [voice, on-device, local-ai, mac]
more:
  - name: "User guide"
    url: "https://github.com/BillDX/InsideVoice/blob/main/USER-GUIDE.md"
  - name: "Changelog"
    url: "https://github.com/BillDX/InsideVoice/blob/main/CHANGELOG.md"
  - name: "All releases"
    url: "https://github.com/BillDX/InsideVoice/releases"
  - name: "Report a problem"
    url: "https://github.com/BillDX/InsideVoice/issues"
---

Inside Voice is push-to-talk dictation for the Mac. Click wherever you want to type, hold down the **Option key to the right of the space bar**, speak, and let go. Your words appear a moment later, in email, documents, chat, web pages: any app where you can type.

## How to start

1. **Download and install.** Open the `InsideVoice.dmg` file and drag Inside Voice into Applications.
2. **Follow the setup.** A setup window walks you through a one-time download of the speech engine (669 MB) and the three macOS permissions it needs, each with a plain explanation.
3. **Hold the right Option key and talk.** Saying a lot? While holding Option, tap the right Command key to lock it on hands-free, then tap Option once when you're done.

After setup it lives in the menu bar as a small waveform circle. Click it for settings.

## Private by design

- **Nothing leaves your Mac.** The speech engine runs on your computer and works the same with Wi-Fi off. The only time it uses the internet is the model download you approve during setup.
- **Nothing is saved.** Your voice is never recorded to a file, and nothing you say is logged or kept.
- **No account, no subscription, no ads.**

## Why I built it

Inside Voice is a working demonstration of sovereign, on-device AI: a complete speech product with no cloud dependency, models checked against their publishers' published hashes, and no data exhaust. I built it to show that useful AI can run entirely on your own computer, and to take that idea all the way to an app anyone can download.

## Under the hood

Speech is transcribed on the Mac by NVIDIA Parakeet TDT, or OpenAI Whisper large-v3-turbo via whisper.cpp, accelerated with Metal. In *Auto* mode it picks per utterance: Parakeet for speed and plain-English accuracy, Whisper when your personal word list is active or the language needs it. It understands English and 24 other European languages out of the box, and an optional second engine adds 99 languages.

Builds are signed with a Developer ID and notarized by Apple, and every release ships a SHA-256 checksum next to the download. It also installs with Homebrew:

```bash
brew tap BillDX/tap
brew install --cask inside-voice
```

The full details, including the privacy model and troubleshooting, are in the [user guide](https://github.com/BillDX/InsideVoice/blob/main/USER-GUIDE.md).
