# Two Way Flow — Download & Install

Two Way Flow is a live sales-call coaching overlay for macOS (Apple Silicon). This repo hosts the downloads and the in-app update feed.

## Download

Grab the latest **`.dmg`** from the [Releases page](https://github.com/Tuned-Automation/two-way-flow-releases/releases/latest).

## Install (first time)

1. Open the downloaded `.dmg` and drag **Two Way Flow** into your **Applications** folder.
2. The app is not signed with an Apple Developer certificate yet, so macOS will warn you the first time. To open it:
   - **Right-click** the app in Applications → **Open** → **Open** again, **or**
   - If macOS blocks it: **System Settings → Privacy & Security**, scroll down to the message about "Two Way Flow", and click **Open Anyway**.
   - As a last resort, in Terminal:
     ```bash
     xattr -dr com.apple.quarantine "/Applications/Two Way Flow"*.app
     ```
3. On first launch, grant permissions when asked:
   - **Microphone** — for your side of the call (one click).
   - **Screen Recording** — for the prospect's audio. Toggle it on in **System Settings → Privacy & Security → Screen Recording**, then quit and reopen the app (screen-recording grants only apply after a restart).

## Add your API keys

Two Way Flow uses your own AI provider keys — nothing is shared or billed centrally. Open **Settings** (gear icon) → **Providers** and paste:

- **Gemini** (required) — powers live transcription + coaching.
- **Deepgram** (recommended) — prospect-side transcription. Without it, the app falls back to your-side-only audio. Enter this on **Settings → Audio → Speech-to-text**.
- **OpenAI / Anthropic** (optional) — alternative coach models.

## Updates

The app checks for updates automatically (and you can check any time in **Settings → General → Updates**). When a new version is available you'll see release notes and a **Download update** button. Because the app is unsigned, the update downloads inside the app and then opens Finder — just drag the new version into Applications and reopen.

## Uninstall

Dragging the app to the Trash leaves your data and macOS permission
entries behind. To remove **everything** (the app, your rubrics +
settings, caches, and the Microphone / Screen Recording permissions),
download [`uninstall.sh`](https://github.com/Tuned-Automation/two-way-flow-releases/blob/main/uninstall.sh) and run:

```bash
bash ~/Downloads/uninstall.sh
```

It asks for confirmation first. (Any update DMGs you downloaded stay in
your Downloads folder — delete those yourself if you want.)

Prefer to do it by hand? Drag **Two Way Flow** from Applications to the
Trash, then delete `~/Library/Application Support/Two Way Flow`, and
remove the app's rows under **System Settings → Privacy & Security →
Microphone** and **Screen Recording**.

## Privacy

Audio is processed by the AI providers whose keys you supply (Google Gemini, Deepgram, etc.). Transcripts and settings stay on your machine. Review each provider's policy for how they handle audio you send them.
