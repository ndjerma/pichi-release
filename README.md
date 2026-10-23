# 🍑 Pichi

Hold a key, talk, and your words get typed wherever your cursor is, in any app.
Speech recognition runs entirely on your Mac using [whisper.cpp](https://github.com/ggml-org/whisper.cpp). No account, no subscription, and your audio never leaves your Mac.

Understands English and Serbian, detecting which one you're speaking automatically.

## Requirements

- Mac with Apple Silicon (M1 or newer)
- macOS 13 Ventura or newer
- About 200 MB of free space

## Install

Open **Terminal** (press ⌘ Space, type "Terminal", press Return), paste this, and press Return:

```bash
curl -fsSL https://github.com/ndjerma/pichi-release/releases/latest/download/install.sh | bash
```

This puts Pichi in your Applications folder, downloads the speech model (~190 MB, one time only), and opens the app.
If it asks for your password, that's macOS asking for permission to write to Applications.

## First-time setup

1. **Allow permissions.** Pichi needs three, all in System Settings → Privacy & Security:
   - **Microphone**: to hear you
   - **Accessibility**: to paste the text where your cursor is
   - **Input Monitoring**: to notice when you hold the Fn key

   After turning them on, quit Pichi (menu bar mic icon → Quit Pichi) and open it again from Applications.
2. **Free up the Fn / 🌐 key.** System Settings → Keyboard → "Press 🌐 key to" → **Do Nothing**.
   Otherwise holding Fn opens the emoji picker or switches your keyboard language.

## How to use

| Do this | What happens |
|---|---|
| Hold **Fn**, speak, release | Your words are typed where the cursor is |
| Press **Fn + Space** | Hands-free mode: keep talking without holding anything |
| Press **Fn + Space** again | Hands-free stops and your words are typed |
| Press **Esc** during hands-free | Cancels without typing anything |

The mic icon in the menu bar shows what Pichi is doing: idle, recording, or transcribing.

**Tip:** to help Pichi spell names and technical terms correctly, add them (one per line) to
`~/Library/Application Support/Pichi/vocabulary.txt`.

## Update

Run the same install command again. Your permissions and settings are kept.

## Uninstall

Quit Pichi, then in Terminal:

```bash
rm -rf /Applications/Pichi.app ~/Library/Application\ Support/Pichi
```

## Troubleshooting

- **Nothing happens when I hold Fn.** Check that Input Monitoring and Accessibility are on for Pichi, then quit and reopen it.
- **The emoji picker opens.** See step 2 of first-time setup.
- **It doesn't type into password fields.** That's expected: macOS blocks this on purpose.
