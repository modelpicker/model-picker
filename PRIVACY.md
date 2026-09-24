# Privacy Policy: Model Picker

This policy covers the Model Picker browser extension. It was last updated on September 24, 2026.

Everything runs on your device. The extension makes no network requests, and it never stores prompt text it read from the page. The only prompts it keeps are the ones you press save on yourself, and those stay in your own browser.

## What the extension reads

The extension runs only on claude.ai. There it reads the prompt you are drafting and the small amount of page text it needs to advise you: the length of the visible conversation, the label on the model picker button, and the presence of the send control. Reading happens transiently, in memory, on your device, each time it prepares a suggestion and each time you send a prompt. Nothing read from the page is kept because it was read: the prompt you are drafting is used to decide a suggestion and then discarded, and the model picker's label is compared in memory and then discarded, with only whether it changed to match a suggestion ever recorded. The one thing that is kept is a prompt you explicitly saved, which is described below.

## What the extension stores

The extension stores four kinds of things in your browser's local extension storage (chrome.storage.local), and nothing anywhere else:

- Your own settings: the switches, sliders, theme, plan, badge position and size, and the per chat choices (mute, lock) you set in the popup and the options page. A few of these are short fixed words rather than numbers (your theme choice, your plan name, which corner the badge is pinned to), and the per chat mute and lock lists are keyed by the conversation's own address on claude.ai, so the record durably names which conversations you chose to mute or lock. Stored alongside them are seven things that are not settings you chose: they are the state of the extension's own request that you rate it. How many times it has asked, a day number before which it will not ask again, whether it has finished asking for good, how many times the badge has shown it in the current round, one count each for the two answers you can give it on the badge, not now and the press that opens the store, and whether you pressed the popup's own "I already rated it", which takes that standing offer away for good. Every one is a whole number or a true or false value, and they record only what happened on our own badge and in our own popup. None of this is prompt text, conversation text, or any other free text.
- Anonymous derived counters: how many suggestions were shown and sent per category, your feedback votes, and a count of the suggestions you acted on. Your feedback votes are stored as anonymous per category counters you can inspect in plain storage. The count of suggestions you acted on is one number: when you send a prompt, the extension compares the model it suggested with the model your picker is set to, and remembers only whether they came to agree. Neither name is written down.
- Operational health: whether the extension can still find the parts of the claude.ai page it reads from. This is stored as counts, booleans, and timestamps only, never as any text read off the page, so a broken reader can be detected without ever recording what it read.
- Prompts you saved: your prompt library. This is the only place the extension keeps any text you wrote, and a prompt gets there in one way only, because you pressed save on it. Either you clicked the save control on the badge while that prompt was in front of you, or you typed one into the field on the settings page, or you imported a file you had exported earlier. A saved prompt's words change afterwards only if you edit it yourself on the settings page and press Save changes. Nothing is added because the extension read your screen. Each saved prompt is kept as four things: its text, the time you last saved or edited it, the kind of task the classifier thought it was, and a number to tell it apart from the others. The classifier works out that kind of task on your device, including when you type or edit a prompt on the settings page, and nothing is sent anywhere to do it. The model and effort it suggested are not kept, and nothing about which conversation you were in is kept. Everything here stays on this device. Saved prompts are kept as ordinary unencrypted text in this browser's extension storage on this computer. They are not uploaded and not synced, so anyone who can use this computer, or read this browser profile's files, can read them. Uninstalling the extension removes them, and Export is how you keep a backup. The settings page says the same thing at the top of the list. You can read the whole list, copy any of it, edit any of it, delete any of it, and export all of it to a file on your own computer, from the settings page. You can also take a prompt straight back out from the badge, by pressing the save control a second time on the draft you just saved. Exporting writes a file to your computer and sends nothing anywhere. Deleting is immediate and cannot be undone.

It never stores conversation text or any other string read from the page, and it never stores a prompt because it read one: the only prompt text it holds is what you saved on purpose. Everything above stays on your device; see "What the extension transmits" below.

## What the extension transmits

Nothing. The extension contains no network code path, and that covers your saved prompts exactly as it covers everything else: they are never sent anywhere, to the developer or to anyone else, and they are never synced to another device or another browser profile. It requests exactly one browser permission, storage. It runs one content script on claude.ai, and one small background script whose only job is to open this extension's own page on the Chrome Web Store, in a new tab, when you click the button on the badge that asks you to rate it. The address of that page is written into the background script itself and nothing sent to it can change it, so it can open that one page and no other. It reads no storage and makes no network request of any kind. It cannot send data anywhere, to the developer or to anyone else, and it uses no cookies, no analytics, and no third party service.

The extension can invite you to rate it on the Chrome Web Store. After you have used it for a while, the badge may come back after you send a prompt with a short line and one button, reading "Rate on the Chrome Web Store". The small close control beside that button means later. It asks at most twice in the life of an install, and then never, and pressing the button also stops it ever asking. A permanent button in the popup, reading the same "Rate on the Chrome Web Store", lets you rate whenever you want to, and pressing it also stops the extension ever asking. Under it, once you have been to the store from either button, "I already rated it" does the same and takes that popup button away for good. Pressing either rate button opens the store listing in a new tab, which is your browser going where you told it to go, and nothing opens unless you press one. Neither carries an identifier or any information about you or your use of the extension, and the extension itself sends nothing when you press one.

## Limited use

Model Picker's use of the data it handles complies with the Chrome Web Store User Data Policy, including the Limited Use requirements.

- Nothing the extension handles is ever sold.
- Nothing the extension handles is used or transferred for any purpose unrelated to its single purpose, which is helping you spend your claude.ai quota deliberately on the prompts you write there, by suggesting a model and an effort level for the prompt you are drafting and by keeping the prompts you choose to save.
- Nothing the extension handles is used or transferred to determine creditworthiness or for lending purposes.

## Contact

Questions, concerns, and reports are welcome on the public repository's issue tracker at https://github.com/modelpicker/model-picker/issues. No email address is required.

## Affiliation

Model Picker is an independent tool. It is not affiliated with, endorsed by, or sponsored by Anthropic. Claude is a trademark of Anthropic, PBC.
