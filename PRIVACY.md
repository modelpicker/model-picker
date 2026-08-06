# Privacy Policy: Model Picker

This policy covers the Model Picker browser extension. It was last updated on August 6, 2026.

Everything runs on your device. The extension makes no network requests and never stores your prompt text.

## What the extension reads

The extension runs only on claude.ai. There it reads the prompt you are drafting and the small amount of page text it needs to advise you: the length of the visible conversation, the label on the model picker button, and the presence of the send control. Reading happens transiently, in memory, on your device, each time it prepares a suggestion. Nothing read from the page is kept anywhere.

## What the extension stores

The extension stores three kinds of things in your browser's local extension storage (chrome.storage.local), and nothing anywhere else:

- Your own settings: the switches, sliders, theme, plan, badge position and size, and the per chat choices (mute, lock) you set in the popup and the options page. A few of these are short fixed words rather than numbers (your theme choice, your plan name, which corner the badge is pinned to), and the per chat mute and lock lists are keyed by the conversation's own address on claude.ai, so the record durably names which conversations you chose to mute or lock. None of this is prompt text, conversation text, or any other free text.
- Anonymous derived counters: how many suggestions were shown and sent per category, and your feedback votes. Your feedback votes are stored as anonymous per category counters you can inspect in plain storage.
- Operational health: whether the extension can still find the parts of the claude.ai page it reads from. This is stored as counts, booleans, and timestamps only, never as any text read off the page, so a broken reader can be detected without ever recording what it read.

It never stores prompt text, conversation text, or any other string read from the page. Everything above stays on your device; see "What the extension transmits" below.

## What the extension transmits

Nothing. The extension contains no network code path. It requests exactly one browser permission, storage, and it runs one content script on claude.ai. It cannot send data anywhere, to the developer or to anyone else, and it uses no cookies, no analytics, and no third party service.

## Limited use

- Nothing the extension handles is ever sold.
- Nothing the extension handles is used or transferred for any purpose unrelated to its single function, which is suggesting a model and an effort level for the prompt you are drafting.
- Nothing the extension handles is used or transferred to determine creditworthiness or for lending purposes.

## Contact

Questions, concerns, and reports are welcome on the public repository's issue tracker at https://github.com/modelpicker/model-picker/issues. No email address is required.

## Affiliation

Model Picker is an independent tool. It is not affiliated with, endorsed by, or sponsored by Anthropic. Claude is a trademark of Anthropic, PBC.
