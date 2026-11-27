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

Mona keeps her own glossary of verified terms in spreadsheets: a religion sheet,
and files for legal, medical and military terms and for military ranks by country.
She wants it as a web app for her colleagues and other professionals, "for instant
translation": when they miss a word mid-sentence, they find it in the other
language. She will keep adding words and sectors (professional is still to come),
many terms differ by country, and the prayers go in once she has re-checked the
process.

Her files point to interpreting in asylum interviews: a military lexicon named for
OFPRA, rank ladders for nine countries, and notes on countries' regions and
security services. TODO(ask): confirm the setting; it decides the print view and
the devices to build for.

## Who uses it

- Mona: adds, corrects and verifies entries, from her phone or a laptop; invites colleagues.
- Her colleagues: search mid-assignment, mostly on a phone, sometimes with no
  signal. Where devices are not allowed in the room they bring a printed page, and
  beside a video interview they use a laptop or tablet (the EUAA's guide for
  interpreters advises both).
- Later, perhaps, other professionals (see "Free or paid" under Decisions).

## Languages and words

- Entries: French, Arabic (right to left) and English. Her religion sheet has
  French and Arabic on almost every entry and English on about a fifth; some rank
  tabs give English and Arabic only.
- Transcriptions: Arabic in Latin letters, spelled many ways (Arif, Aarif, Earif).
  Interpreters at OFPRA and the CNDA are expected to know a term's transcription in
  French.
- Interface languages: TODO(ask): French, Arabic, or both? (pages are in English
  until she says)
- Right to left: yes, for Arabic text everywhere it appears.
- Her own terms (never renamed):
  - sector: the top level (religion, military, medical, legal, professional)
  - section: her own outline inside a sector, in her order
  - to check / verified: the status of an entry (her sheet marks doubts by hand)

## Agreed scope

Proposed to Mona on 2026-11-27 (the features document) and revised the same day
after her four new files; TODO(ask): her yes before anything is built.

### First version: a free pilot

Mona edits in the app, and the colleagues she invites search it on their phones,
online or off, or print what they need.

- [ ] Her files load into the app: the religion sheet and the legal, medical,
  military and rank files, through a map per tab of which column holds what. Each
  row becomes an entry with its French, Arabic and English terms, the variants
  (her " - " lists), transcription, note, sources, sector, section, country and,
  for ranks, service, all marked "to check". Each tab is marked as hers or as
  pasted from a published glossary. A report lists terms translated differently
  within one sector and country.
- [ ] Search everything: one box for every language, variant, transcription,
  abbreviation and note, with results as she types, on the phone itself (see "How
  search behaves").
- [ ] Answer at a glance: the equivalent shows large at the top of the results,
  with its sector and country, readable mid-sentence without opening anything.
- [ ] Entry page: French, Arabic (right to left) and English side by side, with
  variants and their countries, the transcription, the note, sources as links, and
  a copy button on each term.
- [ ] Sectors: religion, military, medical, legal and professional as top-level
  sections, and a sector filter on search.
- [ ] Country labels: each variant can name the countries, churches or communities
  that use it, and search filters by country.
- [ ] Rank ladders: each country's ranks by service, lowest to highest, with the
  transcription, the insignia in her words, and the NATO code (OF-1 to OF-10,
  OR-1 to OR-9) that lines ranks up across countries.
- [ ] Browse by topic: each sector as a tree, in her order.
- [ ] Works offline: installs on a phone, tablet or laptop; every published entry
  lives on the device, so search works with no signal.
- [ ] Print view: any sector, country or rank ladder as a clean page to print, for
  rooms where devices are not allowed.
- [ ] Colleague access: colleagues sign in with an email link she sends, and see
  her verified entries only, never a pasted glossary.
- [ ] Her editor: add, correct and verify entries (variants, sector, country,
  transcription, note, source, status), from phone or laptop, with a warning when
  a translation clashes with another in the same sector and country.
- [ ] Missing-word requests: when a search finds nothing, one tap sends the word to
  her list. Nothing else about searches is stored.

### Later (not agreed yet)

Second version, once the pilot runs:

- Prayers and the Mass: French and Arabic side by side, in order, kept as drafts
  until she marks them checked.
- Print as a book: a sector or section as a book, with contents and Arabic set
  right to left (she plans a printed copy).
- Country pages: her background notes per country (regions, security services),
  linking to public reports such as OFPRA's country notes rather than copying them.
- Insignia pictures: a picture of each rank's insignia beside her description,
  where the picture's licence allows it.
- Suggest a correction: a colleague proposes a fix that only she can accept.
- People and places: indexes of names in every language.
- Feasts page: each feast with its date in both calendars, or its rule.
- Export: CSV or TBX, for colleagues who keep glossaries in other tools.

After that, if the pilot shows demand: paid access, feast dates worked out each
year (Coptic and Western) and a converter for dates given in another calendar,
her tags across sections, favourites and recent searches kept on the phone.

### Not doing

- No machine translation: every entry is hers and checked.
- No open sign-up at first: she invites, so entries still being checked never
  reach strangers.
- No search history on the server: searches stay on the phone (interpreters work
  under confidentiality).
- No native app: the web app installs like one.
- No public comments: corrections arrive as suggestions only she sees.
- No pasted glossaries for colleagues: what she pasted from published glossaries
  stays in her own view until each one's licence is checked.
- No copies of public reports: country pages link to them.

## How search behaves

- Results appear as you type, from the phone itself, with no wait for the network.
- Accents and capitals don't matter: "epitre" finds "Épître".
- Arabic vowel marks, tatweel and the hamza forms of alef don't matter: الانجيل
  finds الإنجيل. ة matches ه, and ى matches ي. These five are the rules of Lucene's
  Arabic normalizer.
- The Persian ی matches ي too (her rank file uses it in a few words).
- Transcriptions match loosely: Arif, Aarif, Earif and ‘arīf all find عريف;
  apostrophes, macrons and doubled vowels don't matter.
- Abbreviations find their entries: JLD, AVC, OF-6.
- Any variant opens its entry, and pronunciations count.
- Sector and country filters narrow results.
- Each result names its sector and country, so the same word in two sectors (canon:
  the church's, or the gun) never reads as one.
- The exact term first, then variants, then mentions in notes, each with the
  matching language on top.

## Design

- Source: no design file; build from this brief. Mona sees each screen on a preview
  before it goes live.
- Brand: TODO(ask): a name for the app, colours she likes, a logo if any.
- Devices: phone first (360 to 412 px), then tablet and laptop for her editing and
  for video interviews.
- Arabic is set right to left and large enough to read at a glance; long terms wrap.
- Printed pages: one column, Arabic right to left, no navigation, the sector and
  country on every page.

## Data and privacy

- What the app stores: the glossary (entries, variants, transcriptions, notes,
  sources, sectors, sections, countries, status), colleagues' accounts (email) and
  the missing words they send.
- Personal data: colleagues' email addresses, for sign-in and invitations only.
  Searches are never stored on the server. A privacy notice before the pilot
  starts: TODO(ask).
- Her existing data: her religion sheet and her legal, medical, military and rank
  files, kept in `client-files/` on the owner's machine, never committed. The
  import reads them from a path given when it runs.
- Rights: about three quarters of the legal file's rows are pasted from published
  glossaries, and some medical entries follow a published dictionary. In France a
  database's maker can stop others extracting or reusing a substantial part of it,
  so pasted material stays in her own view until each source's licence is checked.
  Some texts (prayers, Bible translations, notes from websites) may also belong to
  a publisher or a church body. TODO(ask): is the military lexicon her own work or
  a document OFPRA gave her, and may colleagues see it?
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
- 2026-11-27: Proposed after her four new files: country labels, rank ladders and a
  print view join the first version, and pasted glossaries stay in her own view.
  TODO(ask): Mona's yes. (owner)

## Questions for the client

- Is the first version above what you want first? Anything to swap?
- Which of your files and tabs are checked, and which are still to check?
- Where do the pasted glossaries in the legal and medical files come from, and may
  they stay in your own view only?
- Is the military lexicon your own work or a document OFPRA gave you, and may
  colleagues see it?
- Are your colleagues allowed a phone, tablet or laptop in the interview room, and
  in video interviews?
- Which of the nine countries in the rank file matter most to your colleagues?
- Do the colours in your files mean anything, such as checked or doubtful?
- Should there be a glossary on sexual orientation and gender identity? Your files
  hold 4 cells on it.
- How many colleagues would join a first pilot?
- Should colleagues only suggest corrections, or may trusted ones edit too?
- Which language should the app's own buttons and menus be in?
- What would you like the app to be called?
- Could you open free Cloudflare and Supabase accounts in your name and invite me?
  That way the app stays yours.
