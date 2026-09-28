# Case Converter

A macOS app that changes the case of text and fixes text typed with the wrong keyboard layout
active (a word like `ghbdtn` becomes the word you meant). Works in any application via a hotkey,
from the menu bar and through the Services menu.

**Download:** [latest release](https://github.com/Damon4/case-converter-releases/releases/latest) → `CaseConverter-x.y.z.dmg`.
Requires macOS 14 or newer. Apple Silicon and Intel.

**Web version**, nothing to install: https://damon4.github.io/case-converter-releases/ — the same
case modes and layout switch right in the browser.

## Installation

1. Open the DMG and drag `CaseConverter.app` into Applications.
2. On first launch macOS will say the developer cannot be verified: the app is signed without
   an Apple certificate. System Settings → Privacy & Security → scroll down → "Open Anyway".
   Terminal alternative:
   ```sh
   xattr -dr com.apple.quarantine /Applications/CaseConverter.app
   ```
3. For hotkeys in other apps and layout auto-correction, allow access when macOS asks:
   System Settings → Privacy & Security → Accessibility → CaseConverter.

The app lives in the menu bar (the "Aa" icon). Open the converter window from there.
Updates are checked automatically (Sparkle); you can switch it off in Settings.

## What it does

| Mode             | Example                    |
|------------------|----------------------------|
| UPPER CASE       | `HELLO, WORLD`             |
| lower case       | `hello, world`             |
| Title Case       | `Hello, World`             |
| Sentence case    | `Hello, world. How are you?` |
| iNVERT cASE      | `hELLO, wORLD`             |
| Switch layout    | `ghbdtn` → the word you meant; works both ways |
| For developers   | camelCase, PascalCase, snake_case, kebab-case, CONSTANT_CASE |

- **In the app window**: select a fragment and press a mode; with nothing selected the whole text
  changes. Offline spell check with the macOS dictionaries.
- **In any application** via hotkeys (change them in Settings ⌘,):
  ⌥⇧U upper, ⌥⇧L lower, ⌥⇧T title, ⌥⇧S sentence, ⌥⇧I invert,
  ⌥⇧C next case (cycles), ⌥⇧X switch layout. They act on the selection, or without one on the
  word under the caret.
- **Layout auto-correction** (toggle in the menu bar): a word typed in the wrong layout, like
  “ghbdtn”, is replaced with the word you meant the moment you type a space, and the input source
  switches. The macOS dictionaries decide, so real words are left alone. Never runs in
  password fields.
- **Without any permission**: select text → right click → Services → Case Converter.

## Feedback

Bugs and ideas → [Issues](https://github.com/Damon4/case-converter-releases/issues).
