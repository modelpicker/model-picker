# Changelog

All notable changes to this project are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Versioning is informal (nobody pins a version of this extension the way a
package consumer would; the Chrome Web Store always serves the latest
approved version), but each entry corresponds to the `manifest.json`
`version` field at the time. The extension has been public on the Chrome
Web Store since August 5, 2026, item id `hilolfchpmjmkjfnpjcedfeochdnlddk`.

## [Unreleased]

## [1.0.5] - 2026-10-28

### Added

- A welcome page when you first install the extension. Installing it opens a
  page of the extension's own once, in three short steps. The first asks which
  Claude plan you use, and on Team which seat you have, or on Enterprise which
  seat you have and which models and highest effort levels your organization
  allows. The second asks for the badge's theme and size and shows the whole
  badge as it will look; resting the pointer on any of its buttons, or tapping
  one, says what it does, and the Tab key reaches each of them too, with its
  explanation, including when the compact badge opens under the pointer. The
  third shows the real suggestion badge reading one of five sample prompts
  with your plan applied, so you can see what it says before your first
  prompt. The last screen shows where to find the extension's icon and how to
  pin it, and a button opens Claude AI's new chat page in a new tab. The page
  is part of the extension and loads nothing from the internet. It stores only
  what you choose on it: your plan, your Team seat, your Enterprise seat, the
  models your Enterprise organization allows, the theme and the badge size.
  Reloading or updating the extension opens nothing. The settings page has a
  Welcome page row, under Theme, that opens it again.

- The welcome page in a narrow window. When the window is too narrow for its
  two columns side by side, the page stacks them with room between, and keeps
  its full size title and questions, the names of all three steps and the step
  count, so it reads as the same page rather than a squeezed one. Below about
  480 pixels the steps show the current one's name alone and the step count is
  left out. Whenever the page is taller than the window, the bar with Back and
  Continue stays at the bottom of the window, so the next step is always one
  press away; when the page fits the window, the bar is an ordinary part of
  it.

- Team and Enterprise as plan choices, and a truer note about Fable. The
  settings page now offers five plans: Free, Pro, Max, Team and Enterprise.
  Every model is either included in your plan, available by usage credits, or
  not on your plan at all, as Anthropic's own plan comparison lists them. A
  suggestion names only a model your plan includes. When a stronger model
  would have been ideal, the note says why it was not suggested, and names the
  effort the prompt needed, as in Opus at High would be ideal but is not on
  your plan: on Free, Fable "is not on your plan", and on Pro and on a
  standard Team seat, where Fable is available by usage credits, the note now
  says Fable "uses usage credits on your plan" instead of claiming it is not
  on your plan, which was not true. On Team you say which seat you have: a
  premium seat includes Fable within your weekly limit, and a standard seat,
  or Not sure, reads Fable as a usage credits model. On Enterprise a note
  appears only when your organization's own settings call for one, such as
  when it does not allow a model, when your standard seat puts Fable on usage
  credits, or when it caps the effort below what a prompt needs. The popup
  offers all five plans too. If you pick Team, choose your seat as well, under
  the plan on the settings page or on the welcome page: until you do, it reads
  as Not sure.

- Report an issue, in the popup's footer beside Privacy. Pressing it first
  puts your anonymous counters on your clipboard as plain lines of a label and
  a number, with the extension's version, your plan and the day counting
  began, and nothing you typed and no page you visited, and then opens the
  project's public issue form on GitHub in a new tab, which asks you to paste
  them. Nothing is sent unless you send it yourself. Privacy opens the privacy
  policy the same way. The settings page and the welcome page carry Privacy
  and Report an issue links too; they open the same two pages and put nothing
  on your clipboard.

- A version button in the popup. The popup now shows the extension's version
  beside its name, and pressing it asks Chrome to check for an update right
  away, the same check Chrome already makes on its own every few hours. It
  reads Checking, then Up to date, Checked recently or Updating; when an
  update is there, Chrome downloads it and the extension restarts into the
  new version. The next time you open the popup after an update, it says so
  once, where the line under the big number usually is, and asks you to
  reload any Claude AI tab that was open. The check is Chrome's own, and the
  extension itself still sends nothing.

- Your seat and your organization's models, right where you choose your
  plan. On the settings page the follow up question sits under the plan
  itself: on Team, which seat you have, and on Enterprise, which seat you
  have and which models and highest effort levels your organization allows,
  so suggestions stay inside what your model picker actually offers. In the
  popup, a small link beside the plan, Team seat or Model access, opens that
  part of the settings page.

- A live picture of the badge on the settings page. The Badge card now opens
  on the whole badge, the suggestion with its thumbs up and down, the save
  button, the lock and the close button, centred over a sample message box at
  any window width, and drawn in the same font Claude AI shows the badge in,
  Segoe UI on Windows, so it looks like the badge you will see there. It
  changes as you change the text size, the badge size, the fading and the
  theme, and the box around it grows and shrinks with the text size, so you
  can see what each setting does before you go back to Claude AI. Its buttons
  do nothing there, since it is a picture, and nothing is saved when you press
  them.

- Pinned saved prompts and choosing several at once. On the saved prompts page
  you can pin a prompt to keep it at the top, and the pin travels with an
  exported file. Select lets you choose several prompts to export or delete
  together, and either one ends the selection: the toolbar comes back, and
  after an export its Export button reads Exported for a moment. A deletion
  asks first, whether it is one prompt or many.

### Changed

- A quick fact suggests Haiku at Low effort now. The newest Haiku has an
  effort setting in Claude AI's model picker, so the badge names one, where it
  named Haiku alone before. In a long chat on an older Haiku, which has no
  effort setting, the badge still names no effort, and a badge that stays on
  Haiku in a long chat closes when the picker switches between that Haiku and
  the newest one.

- Long documents and creative writing suggest Sonnet alone. Their badges also
  named a second model in brackets beside Sonnet; every suggestion now names
  one model and one effort, and the badge names another model only when your
  plan lacks the one the prompt needs.

- The note about an expensive read gives new figures, worked out from
  Anthropic's published prices: Opus spends about 2x the quota of Sonnet per
  word and Fable about 5x, where the note said 5x and 10x.

- The note about an expensive read now ends by saying a new chat started
  from a short summary of this one saves quota, and never suggests a lighter
  model, since switching models in the middle of a chat makes the new model
  read the whole conversation again. In a new chat with no earlier messages
  the note ends after its first sentence.

- The long chat tip gives two numbered steps: ask this chat for a short
  summary of what matters, then start a new chat and paste it. It never
  suggests a lighter model any more.

- When the extension can no longer read how long a chat is, the popup's
  notice now says long chat advice and combined read warnings are off, since
  the advice to stay on your model in a long chat stops too.

- The welcome page and the settings page say the badge names a model by
  its family, Opus for example, and means the newest version when your
  model picker lists more than one.

- The popup's count of suggestions at low or medium effort now includes
  quick facts, which carry Low effort.

- Importing saved prompts uses the page's own Choose file button now, with
  the name of the file you chose beside it, in the page's own words. Before,
  the control was the browser's, in the browser's language, and it read No
  file chosen again right after a file was imported. Once a file is imported
  the button waits until you press Done, and the same file can be chosen
  again whenever you like.

- The badge no longer appears on Claude Code on the web (claude.ai/code).
  Its suggestions are written for chat prompts, and that page's model and
  effort controls are not the chat's, so the extension now stays out of it
  entirely: it does not watch the message box there, shows nothing, and
  counts nothing. Chat pages work as before.

- A new look for the popup. At the top, the name, the version and a chip that
  reads On or Off; under it the share of your prompts that didn't need a
  premium model, with a bar, or Nothing counted yet before your first prompt;
  then the settings, the This chat switches and the rows for Saved prompts and
  All settings; then your stats in a card of their own; and at the foot the
  privacy sentence with Privacy and Report an issue.

- Reset stats moved next to the numbers it resets, at the top of the stats
  card, and it asks first: Reset all counts?, with Keep and Reset. Your
  settings and saved prompts stay either way. It used to sit in the footer and
  clear every count on one click with no way back. After a reset the keyboard
  focus lands on the stats card's top line, so you can go on moving through
  the popup with the keyboard; choosing Keep, or pressing Escape, returns it
  to Reset stats.

- A cleaner settings page. It opens on the same top bar as the welcome page:
  the extension's mark and name, and a chip that reads On or Off with a small
  dot before it, green when the extension is on and grey when it is off. A
  sidebar with an icon for each part, General, Badge, Warnings and Muted
  chats, then Saved prompts, Privacy and Report an issue, takes the place of
  the switch between Settings and Saved prompts at the top of the page. Every
  setting has its own small icon, and the cards are set apart a little more
  clearly.

- The two fade sliders, Faded badge visibility and Fade delay, now sit inside
  the Fade the badge when idle row, under its switch, and as before they are
  greyed out while fading is off.

- The Size warnings setting now says what each level means in numbers: at
  Standard, a prompt over about 800 words or a chat over about 2,500 words,
  and the numbers move as you pick Earlier or Later.

- A rebuilt saved prompts page. Each saved prompt shows its kind of task as
  a small icon, its first two lines and the day you saved it, with four
  buttons: copy, edit, delete and pin. One toolbar holds the search, Select,
  Import, Export and Add a prompt; the kinds of task sit as chips above the
  list, six at a time with More for the rest; press / to jump to the search.
  The numbers in front of each prompt are gone.

- A new look for the badge. Every suggestion now starts with the extension's
  mark, the same lime square as its toolbar icon, on one row with the word
  Suggested and the button that closes it; under them the model it suggests in
  larger type, with the effort in a small chip beside it, and the reason under
  that. Notes about a long prompt or a long chat sit in a tinted box of their
  own. The compact pill starts with the mark too, so a suggestion on Claude
  AI's page says whose it is. Clicking the mark does what clicking anywhere
  else on the badge does. The request to rate the extension keeps its close
  button in the same place as the badge's, and its button is lime.

- One design for the popup, the settings page and the welcome page, in light
  and dark, set in the Inter typeface, which is packaged with the extension
  and never loaded from the internet. In dark, the cards, the controls and
  their outlines stand a step lighter than the page behind them, so the parts
  of each page read apart. Longer descriptions run to the end of their lines
  and are justified, so a paragraph reads as one even block, while short hints
  beside a control stay left aligned.

- The settings page in a narrow window. When the window is under about 900
  pixels wide, the sidebar becomes a slim column of icons with short names, so
  every part of the page stays one click away and the settings keep their full
  width. In a very narrow window, a setting with a choice of levels or a
  slider puts its control under its name instead of squeezing it, and on the
  saved prompts page the toolbar and each prompt's buttons move onto a line of
  their own.

- The privacy policy now describes everything this version keeps and does: the
  settings the welcome page and the Enterprise choices store, a saved prompt's
  pin, what Report an issue puts on your clipboard, the three facts kept about
  the model picker's label and never the label itself, how many times the
  request to rate the extension can show, and that deleting a saved prompt
  asks first.

### Removed

- The popup's I already rated it button. The Rate on the Chrome Web Store
  row stays for good: the store keeps one review per Google account, which
  you can edit any time, so the row is a way back to your own review and
  never a request for a second one.

### Fixed

- A suggestion you close now stays closed. Closing the badge with its x,
  clicking on it, or voting on it used to hide it only until the page changed
  underneath it, so if you then opened Claude's settings, went on to the page
  for changing your plan and came back, the suggestion you had closed could
  appear again, on that page and over your conversation. The extension now
  remembers the draft you closed and shows no suggestion for it until you type
  something different or send it. Two small costs come with that: if you clear
  the box and paste the very same prompt back, or paste it into another
  conversation straight after closing its badge, no suggestion appears until
  you change a character. The draft you closed is remembered only on the open
  page and is never stored anywhere.

- A suggestion no longer follows you onto a page that has nothing to type
  into. When you left a conversation with a draft in its box for a page with
  no message box at all, such as the page for changing your plan, a suggestion
  for the draft you had left behind could appear there anyway, whether or not
  you had closed it. The extension now reads only a message box that is still
  on the page.

- The popup's page health notice now also watches project pages for a missing
  message box. It already watched new chats and conversations, but a project
  page, which has a message box of its own, was left out, so if a change to
  claude.ai's page stopped the extension finding that box there, the popup
  said nothing about it.

- The popup's page health notice is easier to read in both themes. It is now
  a warning box, the same shape the badge uses for its own notes, with a
  warning sign at its left.

## [1.0.4] - 2026-09-25

The September 9 and September 24, 2026 cuts of this version were never
published.

### Added

- A keyboard shortcut. Alt+M (Option+M on Mac) opens the extension's popup,
  so the stats, the quick settings, and the per chat mute and lock switches
  are reachable without a mouse. The chord can be remapped from Chrome's own
  shortcuts page (chrome://extensions/shortcuts). Ctrl+Shift+M was not used
  because Chrome reserves it for its own profile menu on Windows and will not
  hand it to an extension. The default also avoids Ctrl+M, which other
  extensions in this space already bind, and Command+M, which macOS uses to
  minimize windows.

- An invitation to rate the extension. After you send a prompt, and only then,
  the badge you already use can come back with a short line naming the
  extension and one button, reading Rate on the Chrome Web Store, filled and
  pill shaped in the badge's own colors, with the extension's icon at the end
  of its row so it is clear whose card it is. It never appears while you are
  typing, it goes away the moment you type your next word, and nothing about
  it touches the page: it is the same small box in the same corner, saying
  something else. Escape closes it, Tab reaches its buttons, and a screen
  reader is told politely that it is there.

  The button does what it says, in one click. It opens the store's reviews
  page for this extension in a new tab, right beside your claude.ai tab, and
  closing that tab puts you back where you were, with the reply still
  arriving. A screen reader hears that it opens in a new tab before you press
  it. Nothing opens by itself: the tab is what happens when you press that
  button, and at no other time, and its address carries no identifier of any
  kind.

  Only a choice counts. The small close control and Escape are a choice, since
  you aimed at them, and they mean later, which is about two weeks. Typing
  your next word puts the line away without answering it, and opening or
  closing the popup changes nothing at all, since the popup never asks.

  The whole request is bounded: it asks at most twice in the life of an
  install, each round can put the line on the badge at most three times before
  that round ends by itself as a later, and then it stops for good. Pressing
  the button stops it immediately, because nobody should be asked again after
  being sent to the store.

  It asks only people it has actually helped: fifteen sent prompts, three
  days, and at least one sign that a suggestion landed, either a thumbs up or
  a model you switched to after the badge suggested it. Everybody who reaches
  that bar is asked the same way. Nothing about your votes decides whether you
  are asked, in either direction, and nothing is offered in exchange.

  The popup carries a permanent button with the same words, Rate on the Chrome
  Web Store, for anyone who wants to rate at a moment of their own choosing.
  It carries the extension's icon the same way, and its words are in the
  popup's accent color inside a lighter outline of the same color. It spans
  its card the way the popup's other rows span theirs, with the same small
  arrow those rows carry at its right, in a card of its own near the bottom of
  the popup, above the footer. It opens the store in a new tab, which a screen
  reader hears before you press it, and pressing it also stops the extension
  ever asking.

  Under it, once you have been to the store, from the badge or from this
  button, is a button reading I already rated it, framed like Reset stats and
  as wide as the button above it. Press it and that whole card goes away for
  good, and the extension stops asking as well. Until you have been to the
  store it does not appear, since there is nothing yet for it to say you have
  done.

- A prompt library. Keep the prompts you want to use again, without leaving
  claude.ai to do it.

  There is a save control on the badge, beside the thumbs. One tap while the
  prompt is in front of you keeps it, and the badge says so where you tapped
  rather than opening anything. Tap it again on the same draft and it takes
  that prompt back out, so a save you did not mean costs one tap to undo: it
  removes the prompt that tap saved and nothing else, and the badge says which
  of the two happened. It says it on screen, where you tapped: for a couple of
  seconds a short line takes the place of the suggestion's explanation,
  reading Saved to your library., Already in your library. or Removed from
  your library., and then the explanation comes back. Nothing on the badge
  moves while it does. When a save is refused, that line shows the reason in
  the same words the settings page uses. If you changed that saved prompt on the settings page
  in the meantime, the second tap leaves it where it is rather than deleting
  words you have just refined: the save control goes back to its plain shape,
  a screen reader is told why, and the library still shows the prompt. Once
  you type your next word it is back to plain save, and tapping it then keeps
  the new draft rather than removing anything. It is a shortcut: the settings
  page is where the library actually lives, and you can type a prompt straight
  into it there if you would rather. A prompt typed there is sorted into its
  kind of task by the same classifier the badge uses, and the sorting happens
  on your computer.

  Saving a prompt you have already saved does not make a second copy. It moves
  the one you have to the top of the list, and it tells you so, in these
  words: Already saved. It moved to the top of your library, where Delete
  removes it. The last part is there because the badge only takes back a
  prompt its own tap just saved, so removing an older one is done in the
  library. The settings page shows that message in words. On the badge the
  save control takes its saved shape, the short line reads Already in your
  library., and a screen reader hears the fuller message. Importing a file
  never moves anything, so a file cannot reorder your library.

  The settings page now has two views, Settings and Saved prompts, with a
  switch at the top to move between them, so you no longer scroll through
  one to reach the other. The Saved prompts row in the popup opens the second
  view directly. The arrow keys move the switch, and the address of each view
  can be bookmarked.

  The Saved prompts view opens with one plain line: Saved prompts stay only in
  this browser on this computer, unencrypted. Export is your backup. A Details
  button beside it opens the full statement of where your saved prompts live
  and who can read them. They live only in this browser's extension storage on
  this computer, as ordinary unencrypted text. Nothing is uploaded or synced.
  Anyone who can use this computer, or read this browser profile's files, can
  read them. Uninstalling Model Picker deletes them, which is why the
  statement names Export as your backup. Neither calls any of this secure,
  because storage that anyone at your computer can open is not that. The view
  opens with the details closed every time.

  Under that line you get the list, newest first, each prompt numbered, and
  ten at a time unless you choose twenty or fifty under Prompts per page, with
  Newer and Older to move through the rest, and the first line of each prompt
  and the kind of task it was. The numbers carry on from page to page, so the
  second page of ten starts at 11, and a search numbers what it found from 1.
  Your choice of page size is kept, and changing it takes you back to the
  first page. One search box filters by any word in a prompt
  or by its kind, and clicking a prompt's kind fills that box for you, so the
  list narrows to that kind and clearing the box brings everything back. Copy
  puts a prompt back on your clipboard. Edit opens a prompt in place, the
  whole text and not only its first line, with Save changes and Cancel under
  it, one prompt at a time. When you save an edit the prompt is sorted into
  its kind again, since the words changed, and it goes to the top of the list.
  An edit that would leave a prompt empty, make it too long, overfill the
  library, or make it the same as another saved prompt is refused in plain
  words, nothing is changed, and what you typed stays in the editor. So is an
  edit over a prompt that changed in another tab while your editor was open:
  the newer words are kept rather than overwritten, and Edit always opens on
  the prompt as it is stored at that moment. Every one of these messages is
  shown on the page and also announced to a screen reader. Delete removes one,
  straight away and with no undo, which is why Export is there: it writes the
  whole library to a file on your computer, and Import adds a file's prompts
  back without replacing anything you already have.

  The Saved prompts view is built from the same rows, buttons and fields as
  the rest of the settings page, in two groups: Your library, which is what
  you have, and Add prompts, which is how more arrive, typed in or imported
  from a file. Each group reports what happened beside the control you
  pressed: the message for an edit appears with the list, the message for a
  prompt you save, or one that cannot be saved, appears directly under Save
  prompt, and the message for a file you import appears directly under
  Import.

  **Saved prompts never leave this machine.** They sit in the same local
  storage as your settings, as ordinary unencrypted text, they are not synced
  to another device or another browser, and there is still no network code in
  the extension at all: it cannot send them anywhere. Sorting a prompt into
  its kind is done here too, by the same classifier the badge uses, which the
  settings page now loads from inside the extension. Exporting writes a file
  to your own disk, and nothing goes anywhere when you do it. Deleting a
  prompt deletes it here, and that is all there is to it.

  The extension is still read only on the claude.ai page. It never writes a
  saved prompt back into the box for you, and it never clicks, sends, or edits
  anything: saving reads what you typed and leaves your draft exactly as it
  was. A prompt only enters the library because you pressed save on it, and
  nothing about the page you were on is kept beside it, not the conversation,
  not the model, not the effort level.

  There is a size limit, and it is there to protect the rest of the extension:
  one prompt can be up to ten thousand characters and the library about a
  megabyte in all, which is a small share of what the browser allows. At the
  limit a save is refused and told to you plainly. Nothing is ever deleted to
  make room.

  A new row in the popup, under the This chat group, shows how many prompts
  you have saved and opens the page that lists them.

- One small background script, `background.js`. It exists so the button on
  the badge can open the store, which a script running in the page is not able
  to do. It opens one Chrome Web Store tab, on its own address and no other:
  this extension's page on the store is written into the file itself, and
  nothing the page sends it can change where it goes. It is one message
  listener, and it still has no storage, no script injection, and no network
  request of any kind.

- The extension now counts, as a single anonymous number, how often you
  switched to the model it suggested before sending. It compares the two names
  in memory at the moment you send and records only whether they came to
  match; neither name is ever written down.

### Changed

- The Fable family is now named Fable, with no version number, in every
  suggestion, plan note and quota note, exactly as Opus, Sonnet and Haiku
  have always been named. Claude's model picker offers Fable 5.1 beside
  Fable 5, so a badge naming one version read as out of date. Which model
  and effort the badge recommends, and when, is unchanged.

- In dark mode the small text is easier to read. Captions, hints, the line
  under the popup's big number, the settings page's notes and the
  suggestion's explanation on the badge are brighter, enough to meet the
  stricter seven to one contrast level against what they sit on. In light
  mode those captions and hints now use the same grey as the rest of the
  secondary text, a shade darker than before. The lighter grey is kept for
  controls that are switched off, so a switched off control still looks
  switched off.

- The suggestion appears sooner. The badge used to wait about a second after
  you stopped typing before it showed anything; it now waits about a third of
  a second. It still never appears while you are typing, because every key
  you press starts that short wait again.

- In a long conversation the badge no longer suggests switching to a
  different model. Each model keeps its own cache of the conversation, so a
  switch in the middle of a long one makes the new model read the whole
  conversation again, which costs more than a lighter model saves. At the
  same length where the long conversation tip appears, roughly 2,500 words of
  history unless you changed Size warnings, the badge shows the model you are
  already on instead, with the reason in these words: Long chat. Staying on
  this model avoids re reading the whole conversation. For a lighter task,
  start a new chat. The effort it suggests still follows what you are asking.

  It does this only when it can read which model claude.ai's model picker
  shows, and only when your plan in the extension's settings includes that
  model; otherwise the badge suggests exactly as it did. When it does, the long
  conversation tip and the note about a heavier model's reading cost both
  point to a fresh chat and never to a lighter model, including when the
  suggestion already was the model you are on. If you switch models after the
  badge appears, it goes away rather than point you back, and your next word
  brings it back for the model you chose. It reads the picker's label and
  nothing more: it never clicks it, never changes it, and never stores what
  it says.

  Two counts in the popup follow the badge more closely because of it. A
  prompt you send is counted as the suggestion the badge showed you for it,
  even if you changed models after it appeared. And staying on the model a
  long conversation is already on is never counted as following a suggestion.

### Fixed

- The popup no longer stops halfway when its stored usage figures are
  incomplete. If the record behind the dashboard was missing its breakdown by
  kind of task, or held something unreadable there, the popup stopped partway
  through: the big number could read as not a number, and the settings, the
  switches and the page notice below it never appeared. The popup now reads
  that record the same careful way the badge always has, so anything missing
  or unreadable counts as zero and the rest of the popup works as usual.

- A short prompt no longer gets advice meant for a long one. Typing something
  like "summarize the deviations from the plan" into an empty box could bring
  up the suggestion written for a pasted document, so a prompt of six words
  was answered as though it were a long one, in these words: Big input. A
  cheaper model at low effort reads it for a fraction of your quota. That
  sentence now appears only when the input really is big. When you name a
  document yourself but have not pasted one, the same suggestion explains
  itself without saying anything about size. The suggestion for reading
  through a lot of text now only appears when there really is a lot of text,
  or when you have named a document yourself, with words like "summarize this
  document" or "review this contract". Otherwise you get the extension's next
  best reading of what you are asking for, or its ordinary answer when it is
  not sure. Nothing changed about what happens when you do paste something
  long.

- If you have asked your computer to reduce motion, the switches in the popup
  and on the settings page now stay still when you flip them. Both pages
  already turned their small animations off for that setting, but the rule
  that did it missed the sliding part of a switch, so the switches kept
  sliding. It reaches them now, and the button on the new Import control
  with them.

## [1.0.3] - 2026-08-30

### Fixed

- Thread length is measured again on claude.ai's August 30, 2026 markup.
  The page virtualized its conversation transcript and stopped tagging
  messages the way one of the two measurement anchors depended on, so that
  anchor could read a long conversation as nearly empty. It now reads the
  transcript through the page's own accessibility structure, which covers
  every rendered message, user and assistant alike. The fallback anchor was
  unaffected, so warnings kept working in most conversations; this closes
  the gap before it could widen. Known limitation: claude.ai now renders
  only the recent portion of very long conversations, so the thread
  estimate and its warnings reflect the visible portion of the history.

- Thread length warnings now fire at their documented thresholds, so they
  will appear less often in long conversations, and never on new chat
  pages. Two defects stacked here, both convicted by the newchat overread
  autopsy. The thread measurement counted every assistant reply twice,
  because one selector set matches both a reply's container and that
  container's own child, so the long thread tip and the premium read note
  fired at roughly half the documented word counts in every real
  conversation. And the badge computed a thread estimate on every page,
  though a new chat has no conversation to measure. The measurement now
  counts each character once, and pages without a conversation contribute
  zero.
- A suggestion queued in the last second before switching chats can no
  longer appear after the switch: the pending classification is discarded
  when the page navigates.

## [1.0.2] - 2026-08-14

The suggestions are now made by a model trained for the job instead of by
lists of keywords. This is the largest change to what the extension actually
recommends since it was first published, and everything else in this entry
follows from it.

### Changed

- Hard problems now suggest Opus at High effort rather than Extra. The
  change comes from a blind study of the whole mapping table: an
  independent judge, working from the prompts alone with no sight of the
  extension, put every one of these prompts a rung lower on effort while
  agreeing on the model every time. Extra effort was buying quota rather
  than answers here.
- The five screenshots on the Chrome Web Store listing were remade for this
  version. Two of them showed a suggestion the extension had stopped making,
  so what the listing promised and what the product did had quietly come
  apart. They now show what this version actually recommends, and a check
  runs the pictured prompts through the real classifier so they cannot drift
  again without something noticing.

### Fixed

- A very short prompt no longer draws a premium suggestion. Asking a six
  word question, "what is the capital of Australia" phrased in German, could
  suggest the most expensive model at maximum effort, which is the opposite
  of the point of this extension. Under twelve words the two premium
  suggestions are now replaced by the general one, because there is not
  enough in a short prompt to justify spending premium quota on it. Longer
  prompts are untouched, and so is every suggestion that was not premium to
  begin with.

### Added

- Two new kinds of request the suggestions can name: Explanations and
  Translation, both Sonnet at medium effort. Before this they fell through
  to the general default, which happened to suggest the same thing without
  being able to say why.
- **The learned classifier is in the extension.** Suggestions now come from
  a small model trained on the developer's own labeled examples, which
  reads overlapping fragments of your words rather than looking for fixed
  phrases, so it recognizes requests the keyword lists never covered and
  reads languages other than English. It ships as one data file inside the
  extension. There is still no network access of any kind, no download, and
  no prompt text stored anywhere.
- When the model is not sure enough about a prompt, it hands the decision
  back to the original keyword matching rather than guessing, so an unclear
  draft gets the same safe general suggestion it always did.
- If the model file were ever missing or damaged, the extension keeps
  working on keyword matching alone and the popup says so, instead of the
  suggestions quietly getting worse.

## [1.0.1] - 2026-08-01

### Fixed

- The thread reading selectors are updated for the claude.ai page change of
  July 31, which renamed the container the assistant's replies render in.
  Without the update the long conversation tip and the combined read size
  basis of the premium model warning would slowly go quiet; suggestions
  themselves were never affected. The old selector stays as a fallback so a
  page rollback keeps working too.

## [1.0.0] - 2026-07-31

### Changed

- The extension icon is redrawn in a lime palette.
- The extension is renamed to its store listing title.
- The manifest description now uses the effort vocabulary.

### Fixed

- A single failed write could silently stop all later saves of the same
  kind for as long as the page stayed open. Settings, stats, and the page
  health record each queue their writes so two arriving together cannot
  overwrite each other, but a queue that hit an error stayed stuck in that
  state, so everything queued behind it was dropped with nothing to show
  it. Locking a chat could then appear to do nothing until a reload, and
  more seriously the health record could stop noticing page changes, which
  is the one thing it exists to do. All three queues now recover.

- Stats could be lost when a vote and a sent prompt landed at the same
  moment. Both were written by reading the whole stats record, changing
  one number, and writing it back, so two of them happening in the same
  instant each read the record before the other had saved, and whichever
  saved second overwrote the first. In practice that meant voting on a
  suggestion and then immediately sending the prompt could drop the vote,
  or the prompt count, with nothing to show it had happened. Writes are
  now queued so each one sees the previous one's result.

## [0.9.0] - 2026-07-28

The page resilience batch (PLAN.md's approved spec): the extension now
notices when claude.ai's page changes underneath it, instead of failing
silently until someone happens to look.

### Added

- The toolbar popup now says, in plain words, when a change to
  claude.ai's page has broken something the extension reads: what
  stopped, what still works, and that an update will adapt. One line per
  problem, worst first, and nothing at all while everything is healthy.
  What the extension keeps to decide this is anonymous counters on your
  device only, never any text from the page, and there is still no
  network access of any kind.
- The popup also notes when Claude's model picker shows a model this
  version does not recognize yet, so you know suggestions may lag the
  newest lineup until an update. The note never names the unknown model,
  because nothing read from the page is ever stored.

### Fixed

- Two of the new page checks could record their findings at the same
  moment and overwrite each other, so the record behind the popup's
  notices could quietly lose facts. Findings now land one at a time,
  each building on the last, and nothing is lost.
- The "prompt box cannot be found" notice could stay on forever when the
  page recovered only after a reload, because the all clear was tracked
  in page memory, which a reload empties. Recovery is now judged from
  the stored record, so the notice clears on the next load either way.

## [0.8.0] - 2026-07-27

The 0.8.0 UI batch (PLAN.md's approved four item spec), which opened the
per chat placement brief's evidence gate on logged owner friction rather
than on anticipation.

### Added

- Lock the badge from the badge itself: a padlock beside the 👍/👎 pins
  the conversation you are in, or releases it, without a trip to the
  popup. It shows an open padlock while the badge is free to drag and a
  closed one while it is pinned, so the state reads at a glance and from
  shape rather than color alone. The popup switch stays the way in when
  no badge is showing and remains the keyboard path; this is a shortcut
  for the pointer, not a replacement. It appears only inside a real
  conversation and only on the full badge, so the compact pill stays one
  uncluttered line. Like the vote buttons, it stays inert until you
  actually aim at it, so an expansion under a resting cursor can never
  pin a chat by accident.
- Badge size (Full or Compact) is now in the toolbar popup too, beside
  the plan and theme pickers, instead of only on the options page. Both
  surfaces write the same setting and each updates the moment the other
  changes it.

### Fixed

- Selecting a segmented picker no longer looks half animated: the text
  color now travels with the fill instead of snapping ahead of it. Both
  settings surfaces are held to one motion family by new checks, so a
  future control cannot quietly animate a layout property or drift to a
  different speed.

## [0.7.0] - 2026-07-25

The settings and interaction redesign (PLAN.md's approved seven question
spec), which reopened two 0.6.0 decisions with real use behind it: the
preset only magnitude controls and the global position lock.

### Added

- One control language across the popup and the options page: switches
  instead of checkboxes, segmented pickers instead of dropdowns, and
  sliders for the three settings that are really magnitudes, all of them
  plain browser inputs restyled rather than custom widgets, in one row
  layout with the label on the left and the control on the right. Because
  they are native inputs, keyboard operation comes from the browser:
  Space toggles a switch, arrow keys move a picker or step a slider, and
  Home and End jump to a slider's ends.
- Per-chat badge lock ("Lock badge here" in the popup's This chat group):
  pins the badge at its current spot for that conversation, so a chat
  with a code or artifact pane can keep it somewhere different from your
  usual place. A pinned badge cannot be dragged, dragging elsewhere still
  moves the global spot, and the options page gains "Unlock all badges"
  with a live count beside the existing bulk unmute.
- A brief "Noted, thanks" acknowledgment after a 👍/👎 vote, before the
  badge dismisses. Voting previously just dismissed the badge, which in
  real use read as nothing having happened. Still no score of any kind on
  any surface.
- An "All settings" row at the bottom of the popup's settings card,
  replacing the corner "Advanced…" link: the least discoverable element
  on the popup was the one gating most of the settings surface.
- The popup now updates live while it is open when settings change
  somewhere else.

### Changed

- Badge text size, faded visibility, and fade delay are sliders over real
  ranges instead of three presets each: 13 to 17 px, 30% to 85% visible,
  and 4 to 15 seconds. Fade strength is relabeled "Faded badge
  visibility", since the number now reads as visibility rather than as
  strength. Their floors moved into the schema (the input's range, a
  sanitizer applied on every read and every write, and a defensive clamp
  at the badge), so no reachable value can violate the 30% findability
  floor or the 4 second reading window, and a value stored by 0.6.0 as a
  preset converts to the matching number on first read.
- Mute moved off the badge into the popup as a switch in the This chat
  group. Muting hides the badge, so a mute control on the badge deleted
  its own undo and its own evidence, which is also why it is not coming
  back. The switch label stays "Mute this chat" in both states, since a
  switch has no second label, and "Unmute all" remains a button in
  options.
- A slider being adjusted is no longer overwritten by a settings change
  arriving from another window: it holds the value under your hand and
  catches up the moment you let go. Every other control still resyncs
  immediately, which is the rule this one exception is scoped against.
- The extension now declares a minimum browser version of Chrome 105. The
  settings pages draw the segmented picker's keyboard focus ring with the
  `:has()` selector, which shipped in Chromium 105, and on an older build
  that ring would silently not render at all. A stated requirement is
  better than an accessibility affordance that fails invisibly.

### Removed

- The global "Lock badge position" setting, replaced by the per-chat lock
  above. The stored key is stripped on first read. **Disclosed coverage
  loss:** the global lock also applied on the shared new chat routes (`/`
  and `/new`), and the per-chat lock deliberately does not, because
  pinning a shared route would silently inherit into every future new
  chat, the same reason mute has never been offered there. On a new chat
  the badge is always draggable at the global position.
- The transient note after a drop that named where the badge anchored
  ("Anchored to the bottom right corner", "Anchored to the center"). It
  was added in 0.6.0 because the deliberate no snap release left a
  mid screen drop with no visible outcome; sustained real use found the
  outcome IS the badge staying exactly where it was put, and which
  internal landmark holds it is bookkeeping that only matters at the next
  window resize. The no snap release itself is unchanged.
- The `<select>` element leaves both surfaces entirely, along with all of
  its styling.

## [0.6.0] - 2026-07-18

The badge presentation and comprehension work (PLAN.md's approved six
question spec), plus the defect batch its browser verification produced.

### Added

- Badge text size setting (Standard / Large / Extra large): the badge's
  text, hit targets, and spacing scale together from one preset, with a
  24px minimum floor on the controls at every size.
- Fade strength (Subtle / Medium / Strong) and fade delay (4 / 8 / 15
  seconds) settings for the idle fade. Four seconds stays the shortest
  delay by design, so the fade can never start while a suggestion is
  still being read.
- Lock badge position setting: dragging is disabled while everything
  else (controls, dismissal, the position reset) keeps working; a locked
  badge also lets touch scrolling pass through to the page.
- A center anchor: dropping the badge near the middle of the window now
  keeps it centered on every window size, instead of tying it to the
  nearest corner.
- A transient note after every drop stating where the badge anchored
  ("Anchored to the bottom right corner", "Anchored to the center"),
  since the deliberate no snap release otherwise gives a drop no visible
  outcome at all.
- `BOARDROOM.md`, the business and conventions handoff from planning
  chats, and the dash audit's documentation prose scan now covers it
  alongside README.md, CHANGELOG.md, and CLAUDE.md.
- Development tooling: a pre-push gate (`tools/verify/prepush_gate.py`,
  wired as a Claude Code hook) that runs the full verification battery
  before any push and blocks on failure, an adversarial verifier
  subagent definition (`.claude/agents/verifier.md`), and machine setup
  for the chrome-devtools browser MCP, which side-loads the unpacked
  extension into a dedicated Chrome test profile so BROWSER.md's
  mechanical scenarios can be automated.

### Changed

- Size warnings redesigned into two separate, self explaining signals,
  with thresholds in words instead of characters: a long prompt note
  ("Long prompt, about N words. Every model reads all of it...") that
  fires on any model past roughly 800 words, and a premium read cost
  note that names the suggested model, its quota ratio, and the combined
  reading per reply (prompt plus conversation), firing past roughly 600
  combined words. The old single flag warned on ordinary premium prompts
  past roughly 300 words and never explained itself. Word counts carry a
  character based floor so low whitespace pastes (CSV, minified code)
  still register. A plan downgrade to a non premium model silences the
  premium note, since the copy names the model actually shown.
- The long thread tip's threshold is now absolute (roughly 2,500 words
  for every model); the premium cost dimension lives in the new premium
  read note, which counts the thread into its combined basis.
- Opening the compact pill can no longer trigger an accidental vote or
  mute: the controls that appear under the cursor stay inert until the
  pointer actually moves toward one (4px of travel), replacing the
  interim fixed 250ms guard, which could also swallow fast deliberate
  clicks. On touch, only a fast same spot double tap is ignored.

### Removed

- The popup's accuracy percentage ("You agreed with N% of suggestions").
  Votes keep being collected on this device as tuning input, but they
  are no longer presented back as a score: users are learners forming
  judgment about model choice, not judges producing ground truth.

### Fixed

- The transient anchor note after a drag drop is now actually visible:
  the drop's own position save echoed back through the settings
  listener, which re-rendered the badge and wiped the note milliseconds
  after it appeared. The same no-op re-render also collapsed an expanded
  compact pill whenever any setting was written from the popup or
  options page; both survive now.
- The long thread tip and the premium read note's combined reading basis
  fire in real conversations again. claude.ai's current markup tags only
  user bubbles with a message test id, and the old selector logic let
  that tiny match suppress the fallback that measures the whole
  conversation, so the thread size read as nearly zero in every chat.
  Both selector sets are now measured and the larger yield wins.
- The two fade selects on the options page now gray out while "Fade the
  badge when idle" is unticked; they were functionally disabled but
  rendered identical to enabled controls, since the stylesheet grayed
  only disabled buttons.

## [0.5.0] - 2026-07-15

### Added

- Badge size setting (Full / Compact): Compact is a one line pill (model
  and effort, plus a warning dot when a note exists) that opens into the
  full badge on hover or tap and closes when the pointer leaves. Windows
  narrower than 720px always get the pill regardless of the setting.
  Controls that appear under an unmoved pointer during a hover expansion
  ignore clicks for a moment, so opening the pill can never register an
  accidental vote or mute.
- Idle fade setting (on by default): the badge holds full strength for a
  few seconds after each suggestion, then turns translucent until the
  pointer returns or new content arrives. Reading and interacting always
  happen at full opacity, keeping the contrast guarantees intact.
- Size warnings now derive from each model's relative quota cost (set in
  `config.js`): a premium suggestion flags a large paste or long thread
  sooner, Haiku later. A single "Size warnings" control (Earlier /
  Standard / Later) replaces the two raw character threshold inputs on
  the options page; previously customized numbers migrate to the nearest
  level automatically.
- Theme setting (System / Light / Dark), applied consistently across the
  badge, the popup, and the options page, with an explicit choice
  overriding the OS-driven `prefers-color-scheme` default.
- A unified, WCAG-AA-verified color token system, spacing scale, and type
  scale shared by all three surfaces (previously the options page ran a
  separate, incomplete palette).
- An explicit × close control on the badge, with hover/pressed states for
  every badge action (close, 👍/👎, mute).
- Drag-to-reposition for the badge: grab it and move it anywhere; its
  position is stored as a fixed distance from the nearest screen corner,
  so it lands in exactly the same spot on any monitor size. Positions
  saved by earlier unreleased builds (absolute pixels, then viewport
  fractions) migrate automatically. A "Reset badge position" control was
  added to the options page.
- A composer-scoped `MutationObserver` so text that arrives with no
  `input` event (claude.ai's voice dictation feature) still triggers a
  suggestion, without ever double-classifying ordinary typed input.
  Voice scope is now explicit: dictation into the composer is fully
  supported; claude.ai's conversational voice mode is deliberately out
  of scope (no draft exists to advise on before sending).
- A headless verification harness (`tools/verify/`) that runs the real
  extension JavaScript inside V8 via `py_mini_racer`, covering behavior a
  browser test page can't reach (settings, mute, theming, the badge's
  geometry, the compact pill, the idle fade). 312 checks run across nine
  suites, including the browser classifier suite executed headlessly;
  suites exit via a flushed `os._exit` to dodge a V8 shutdown hang on
  some Python builds.
- The dash audit gained two new scopes: the rendered text inside JS
  built HTML fragments (the badge's titles, labels, and text nodes;
  previously any string literal starting with an HTML tag was skipped
  wholesale), and dash as punctuation in the prose of README.md,
  CHANGELOG.md, and CLAUDE.md (list markers, code, links, and
  version/date headers stay exempt).
- Continuous integration: a GitHub Actions workflow runs the full
  verification battery (the classifier suite, all nine headless suites,
  and the dash audit) on every push and every pull request, one step per
  suite so a failure is attributable at a glance.
- A `SECURITY.md` stating the threat model (strictly read only on the
  page, a single `storage` permission, no network capability, anonymous
  counters only, prompt text never stored) and a private contact for
  vulnerability reports.

### Changed

- The badge has a fixed width (was shrink to fit), and a left placed
  badge is anchored by its left edge, so resizing the window can no
  longer squeeze and wrap its contents.
- Popup redesigned: leads with the usage dashboard, with settings grouped
  into a clearly sectioned card (toggles, preferences, a "This chat"
  mute sub-section with explicit muted/mutable/no-chat states) below it.
- The options page adopted the same design token system as the popup.
- Mute vocabulary unified to "Mute this chat" / "Unmute this chat"
  everywhere (the popup previously said "Pause"/"Resume" while the badge
  said "Mute").
- The popup now discovers which claude.ai chat is active by asking the
  content script directly, instead of reading the tab's URL. This also
  let the **`activeTab` permission be dropped entirely. The extension
  now requests only `storage`**.
- Effort ladder corrected to match claude.ai's real selector labels
  (Low / Medium / High / **Extra** / Max). There is no "Xhigh" tier in
  the UI; that key belongs to the Claude API, not the interface users
  actually click.
- Enter-to-send, paste, and mouse-send detection moved to document-level
  capture-phase listeners, since ProseMirror (claude.ai's editor) handles
  and suppresses those events on the composer element itself before an
  element-level listener would ever see them.

### Fixed

- A badge dragged to the left half of the screen wrapped its content
  when the window shrank (it was squeezed against its right edge
  anchor), and a badge placed near a corner drifted away from that
  corner on a larger monitor (a proportional distance grows with the
  screen). Both were consequences of the earlier fraction based
  position storage that the corner model replaces.
- Re-renders (hover expansion, size changes, window resizes) could snap
  the badge back to a stale position saved before the latest drag.
- Two adversarial review findings against the resize path: a window
  resize crossing the compact breakpoint while the badge sat idle faded
  could reveal never seen content at reduced opacity, and an expanded
  pill carried its expanded state across an upward crossing, leaving the
  full badge stuck on a narrow window after crossing back down.
- The badge staying visible after selecting all text in the composer and
  deleting it: ProseMirror can leave zero-width placeholder characters
  behind that `.trim()` doesn't strip, which fooled the classifiability
  check into treating an empty-looking composer as real text.
- The mute control silently disappearing after switching to a different
  chat in the same tab (a consequence of the `tab.url`-based lookup this
  release replaced).
- A short real prompt ("define entropy") being skipped by an overly strict
  minimum length before classification.
- The dashboard's submit counter double-counting or leaking a stale draft
  across sends, chat switches, or edits made within the typing-pause
  window.
- Six keyword misclassifications caused by substring rather than
  whole-word matching (e.g. "story" matching inside "history").
- A dragged badge position could be persisted to storage without being
  clamped to a valid range when migrated from the old pixel-based format.

## [0.4.0] - 2026-07-10

### Added

- Per-user settings: a master on/off switch, an analytics opt-out, and
  editable large-input / long-thread thresholds, editable from both the
  toolbar popup and a new full options page.
- Per-chat mute: silence the badge in one conversation without disabling
  it everywhere, restricted to real `/chat/…` conversations so the
  shared new-chat composer can't be muted for every future chat.
- Plan-aware recommendations: suggestions downgrade to the best model
  included in the user's claude.ai plan (Free / Pro / Max) when the ideal
  model isn't available, with a note explaining the substitution.
- 👍/👎 feedback voting on the badge, surfaced as an agreement-rate line
  in the popup dashboard.

### Fixed

- Mute silencing the shared new-chat route instead of only real
  conversations, and a stale badge lingering after switching chats via
  claude.ai's own single-page navigation.
- Gating semantics clarified and corrected: the master switch now
  reliably disables both the badge and counting together, the analytics
  toggle gates counting only, and per-chat mute affects the badge only
  (a muted chat still counts toward local stats).

## [0.3.1] - 2026-07-09

Initial tracked release: a read-only Manifest V3 extension for claude.ai
that suggests a model (Haiku / Sonnet / Opus / Fable 5) and effort level
per prompt, plus same-day correctness fixes to the classifier and the
submit-counting logic.

### Added

- Two-dial suggestions: model (capability) and effort (thinking depth),
  decided independently, in claude.ai's own vocabulary.
- A local, on-device usage dashboard (toolbar popup): prompts analyzed,
  the share that didn't need a premium model, and a category breakdown.
  Only anonymous counters are stored, never prompt text.
- Thread-length awareness: a one-time tip in long threads (~2,500+ words)
  suggesting a lighter model or a fresh chat, since every reply re-reads
  the whole conversation regardless of model.
- Large-input detection: a warning when a pasted prompt is big enough
  that a bigger model would burn quota fast reading it.
- Long-prompt handling: only the first and last 150 words of a very long
  prompt are classified (the instruction almost always lives at the
  ends; the middle is usually pasted material).
- Extension icons and a zero-dependency browser regression suite for the
  classifier.

### Fixed

- Haiku-tier recommendations no longer mention an effort level, matching
  claude.ai's real UI (the effort selector only exists for Sonnet and up).
- Keyword and reasoning-signal matching now requires whole-word
  boundaries, fixing misclassifications like "story" matching inside
  "history" or "prove" inside "improve".
- A silent category tie-break that favored quick-lookup keywords over
  genuine content evidence, and a large pasted document with an
  incidental reasoning keyword skipping the "just summarize this"
  downgrade it should have gotten.
- Submit-based analytics counted a prompt once per typing pause instead
  of once per actual send, and could log a stale or already-cleared
  draft; usage is now counted from the composer's live text at the
  moment of sending.
