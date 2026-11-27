# First version: the issues to open

Drafts, in build order, for the first version in `PROJECT.md`. Open them once
Mona has said yes to that scope: one Feature issue each (the template asks for
the same three things), then `@claude` on the first. Each builds on the one
before it. Delete this file when they are all open.

## 1. Load her files

- **Scope line:** Her files load into the app.
- **Outcome:** The entries from her religion sheet and her legal, medical,
  military and rank files are in the database, in her sectors, sections and
  countries, all marked "to check", each tab marked as hers or as pasted from a
  published glossary. A report lists the terms translated differently within one
  sector and country.
- **Checks:**
  - A map per tab says which column holds what (French, Arabic, English,
    variants, transcription, note, sources, country, service), and which rows are
    headings rather than entries. A unit test loads a made-up file in each of her
    four shapes: the religion outline with numbered lines, a two- or
    three-language glossary tab, a country tab where terms sit among background
    notes, and a rank ladder with service headings and a transcription column.
  - Variants joined by " - " are split, except where " - " joins a rank and its
    insignia ("rank - description"), as in some rank tabs: the map says which, per
    column, and both parts are kept. Web addresses are kept as sources.
  - Loading the same files twice changes nothing (each row keeps its file, tab
    and row as its source key).
  - A tab marked pasted never reaches a colleague; editors and admins read every
    entry; a signed-in colleague reads only her verified entries; a visitor reads
    none (pgTAP).
- **Notes:** the loader reads the files from a path given when it runs
  (`client-files/`), never from the repository, and the tests use made-up files.
  Her legal file is about three quarters pasted glossaries, so the hers-or-pasted
  mark is part of the model, not a later extra.

## 2. Search everything

- **Scope line:** Search everything.
- **Outcome:** One box finds an entry from any of its languages, variants,
  transcription, abbreviation or note, as you type, on the phone.
- **Checks:** "How search behaves" in `PROJECT.md`, one unit test per rule
  (accents, the five Arabic rules, the Persian ی, transcriptions spelled several
  ways, abbreviations, variants, the order of results), and an end-to-end test
  that types and sees results in under a second at 360 px.

## 3. Answer at a glance

- **Scope line:** Answer at a glance.
- **Outcome:** The best match's equivalent shows large at the top of the results,
  with its sector and country.
- **Checks:** at 360 px the equivalent, its sector and its country are readable
  without scrolling or opening anything; Arabic shows right to left; axe passes.

## 4. Entry page

- **Scope line:** Entry page.
- **Outcome:** French, Arabic and English side by side, with variants and their
  countries, the transcription, the note, sources as links and a copy button on
  each term.
- **Checks:** copy puts the exact term on the clipboard; sources open as links;
  Arabic is right to left; the layout holds at 360 px.

## 5. Sectors and the filter

- **Scope line:** Sectors.
- **Outcome:** The five sectors as top-level sections, a sector filter on search,
  and the sector named on every result.
- **Checks:** filtering by a sector shows only its entries; an empty sector says
  so; a word in two sectors (a made-up homonym) shows as two results, each with
  its sector.

## 6. Country labels

- **Scope line:** Country labels.
- **Outcome:** A variant can name the countries, churches or communities that use
  it, and search filters by country.
- **Checks:** an entry with a different variant per country shows each with its
  country; filtering by a country shows that country's variants and the variants
  with no country; the label survives a reload after she edits it.

## 7. Rank ladders

- **Scope line:** Rank ladders.
- **Outcome:** Each country's ranks by service, lowest to highest, with the
  transcription, the insignia in her words and the NATO code (OF-1 to OF-10,
  OR-1 to OR-9).
- **Checks:** a made-up ladder shows in its order, by service; two made-up
  countries line up by NATO code; a rank without a code says so rather than
  guessing (her tabs carry codes for two countries only); the ladder holds at
  360 px with Arabic right to left.

## 8. Browse by topic

- **Scope line:** Browse by topic.
- **Outcome:** Each sector as a tree, in her order.
- **Checks:** the tree follows each file's outline and tab order; every entry is
  reachable.

## 9. Works offline

- **Scope line:** Works offline.
- **Outcome:** The app installs on a phone, tablet or laptop, keeps every
  published entry on the device, and searches with no signal.
- **Checks:** with the network cut, search still answers from the device; after a
  new entry is verified, the device has it on its next visit online.

## 10. Print view

- **Scope line:** Print view.
- **Outcome:** Any sector, country or rank ladder prints as clean pages, for rooms
  where devices are not allowed.
- **Checks:** the printed page has no navigation, keeps Arabic right to left and
  names the sector and country on every page; a PDF of a made-up ladder lists
  every rank in order; a colleague's print holds verified entries only.

## 11. Colleague access

- **Scope line:** Colleague access.
- **Outcome:** Colleagues sign in with an email link she sends, and see her
  verified entries only.
- **Checks:** an invited colleague signs in and sees verified entries; a "to
  check" entry or a pasted tab never reaches them, online, on the device or in
  print (pgTAP and end-to-end).

## 12. Her editor

- **Scope line:** Her editor.
- **Outcome:** She adds, corrects and verifies entries from her phone or a
  laptop, and marks a tab as hers or pasted.
- **Checks:** a new entry, a correction and a verification each show at once and
  survive a reload; a translation that clashes with another in the same sector
  and country warns her before saving, while the same word in another sector does
  not; colleagues cannot edit (pgTAP).

## 13. Missing-word requests

- **Scope line:** Missing-word requests.
- **Outcome:** When a search finds nothing, one tap sends the word to her list.
- **Checks:** the word reaches her list; nothing else about the search is stored
  (pgTAP: the table holds the word, the sector and country filters and the day,
  nothing more).
