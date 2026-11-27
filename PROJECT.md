# Translation glossary: project brief

The source of truth for what this project is and what was agreed. The owner keeps
it current; agents read it before every change, and change "Agreed scope",
"Milestones" or "Decisions" only when the owner asks. Gaps are marked `TODO(ask):`.

Personal details stay out: a first name is enough. Terms live in the owner's
portal (Clients), not in this repository.

## Client

- Who: Mona, who works in translation (French, Arabic and English)
- How the owner and the client talk: WhatsApp (agents never contact the client)
- Time zone: TODO(ask): hers
- Terms: TODO(ask): between the owner and Mona; the details live in the owner's portal

## What it is for

Mona keeps her own glossary of verified terms in a spreadsheet. She wants it as a
web app for her colleagues and other professionals, "for instant translation":
when they miss a word mid-sentence, they find it in the other language. She will
keep adding words, has files for other sectors (military, medical, legal,
professional) and terminology that differs by country, and the prayers go in once
she has re-checked the process.

## Who uses it

- Mona: adds, corrects and verifies entries, from her phone or a laptop; invites colleagues.
- Her colleagues: search mid-assignment, mostly on a phone, sometimes with no signal.
- Later, perhaps, other professionals (see "Free or paid" under Decisions).

## Languages and words

- Entries: French, Arabic (right to left) and English, French and Arabic on almost
  every entry, English on about a fifth today.
- Interface languages: TODO(ask): French, Arabic, or both? (pages are in English
  until she says)
- Right to left: yes, for Arabic text everywhere it appears.
- Her own terms (never renamed):
  - sector: the top level (religion, military, medical, legal, professional)
  - section: her own outline inside a sector, in her order
  - to check / verified: the status of an entry (her sheet marks doubts by hand)

## Agreed scope

Proposed to Mona on 2026-11-27 (the features document); TODO(ask): her yes before
anything is built.

### First version: a free pilot

Mona edits in the app, and the colleagues she invites search it on their phones,
online or off.

- [ ] Her spreadsheet loads into the app: each row an entry with its French,
  Arabic and English terms, the variants (her " - " lists) kept as variants, the
  pronunciation, note and sources, its sector and its section from her numbering,
  and the status "to check". A report lists terms whose translation differs
  between tabs.
- [ ] Search everything: one box for every language, variant, pronunciation and
  note, with results as she types, on the phone itself (see "How search behaves").
- [ ] Answer at a glance: the equivalent shows large at the top of the results,
  readable mid-sentence without opening anything.
- [ ] Entry page: French, Arabic (right to left) and English side by side, with
  variants, the note, sources as links, and a copy button on each term.
- [ ] Sectors: religion, military, medical, legal and professional as top-level
  sections, and a sector filter on search.
- [ ] Browse by topic: each sector as a tree, in her order.
- [ ] Works offline: installs on the phone; every published entry lives on the
  device, so search works with no signal.
- [ ] Colleague access: colleagues sign in with an email link she sends, and see
  verified entries only.
- [ ] Her editor: add, correct and verify entries (variants, sector, country, note,
  source, status), from phone or laptop, with a warning when a new translation
  clashes with an existing one.
- [ ] Missing-word requests: when a search finds nothing, one tap sends the word to
  her list. Nothing else about searches is stored.

### Later (not agreed yet)

Second version, once the pilot runs:

- Prayers and the Mass: French and Arabic side by side, in order, kept as drafts
  until she marks them checked.
- Print or PDF: a sector or section as a book, with contents and Arabic set right
  to left (she plans a printed copy).
- Country and community labels: which country, church or community uses a variant,
  and a filter by it.
- Suggest a correction: a colleague proposes a fix that only she can accept.
- People and places: indexes of names in every language.
- Feasts page: each feast with its date in both calendars, or its rule.
- Export: CSV or TBX, for colleagues who keep glossaries in other tools.

After that, if the pilot shows demand: paid access, feast dates worked out each
year (Coptic and Western), her tags across sections, favourites and recent
searches kept on the phone.

### Not doing

- No machine translation: every entry is hers and checked.
- No open sign-up at first: she invites, so entries still being checked never
  reach strangers.
- No search history on the server: searches stay on the phone (interpreters work
  under confidentiality).
- No native app: the web app installs like one.
- No public comments: corrections arrive as suggestions only she sees.

## How search behaves

- Results appear as you type, from the phone itself, with no wait for the network.
- Accents and capitals don't matter: "epitre" finds "Épître".
- Arabic vowel marks, tatweel and the hamza forms of alef don't matter: الانجيل
  finds الإنجيل. ة matches ه, and ى matches ي.
- Any variant opens its entry, and pronunciations count.
- A sector filter narrows results.
- The exact term first, then variants, then mentions in notes, each with the
  matching language on top.

## Design

- Source: no design file; build from this brief. Mona sees each screen on a preview
  before it goes live.
- Brand: TODO(ask): a name for the app, colours she likes, a logo if any.
- Devices: phone first (360 to 412 px), then tablet and laptop for her editing.
- Arabic is set right to left and large enough to read at a glance; long terms wrap.

## Data and privacy

- What the app stores: the glossary (entries, variants, notes, sources, sectors,
  sections, status), colleagues' accounts (email) and the missing words they send.
- Personal data: colleagues' email addresses, for sign-in and invitations only.
  Searches are never stored on the server. A privacy notice before the pilot
  starts: TODO(ask).
- Her existing data: the spreadsheet she shared (and later her sector and country
  files), kept in `client-files/` on the owner's machine, never committed. The
  import reads it from a path given when it runs.
- Rights: some texts (prayers, Bible translations, notes from websites) may belong
  to a publisher or a church body. To check before anything is charged for.
- Third parties the browser may contact: none (the security policy blocks
  everything else).
- Cookies: sign-in only.

## Accounts and hosting

| Service | Account owner | Notes |
| --- | --- | --- |
| Cloudflare (Workers) | TODO(ask): Mona, with the owner invited | Free plan for the pilot |
| Supabase (database, sign-in) | TODO(ask): Mona, with the owner as Developer | Two projects: preview and production; the Free plan pauses after a quiet week |
| Domain | TODO(ask) | |
| GitHub | the owner (private repository) | |

## Milestones and sign-off

| Milestone | What Mona accepts | Status |
| --- | --- | --- |
| First version (free pilot) | She searches and edits her own entries on staging, on her phone, offline too | not started |
| Pilot | A few invited colleagues use it for a few weeks | not started |
| Second version | TODO, after the pilot | not started |

## Decisions

- 2026-11-25: It is for her colleagues and other professionals, for instant
  translation; she will keep adding words and sectors; the prayers wait until she
  has re-checked the process. (Mona)
- 2026-11-27: Built on the same stack as the owner's portal, hosted on Cloudflare.
  (owner)
- 2026-11-27: Proposed: a free pilot by invitation first, with sign-in from day one
  so that charging later is a switch, decided after the pilot from weekly use and
  missing-word requests. TODO(ask): Mona's yes. (owner)

## Questions for the client

- Is the first version above what you want first? Anything to swap?
- Can you send your files for the other sectors, and your country lists? The shape
  of an entry depends on them.
- Which countries does your country-specific terminology cover?
- How many colleagues would join a first pilot?
- Should colleagues only suggest corrections, or may trusted ones edit too?
- Which language should the app's own buttons and menus be in?
- What would you like the app to be called?
- Could you open free Cloudflare and Supabase accounts in your name and invite me?
  That way the app stays yours.
