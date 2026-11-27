# First version: the issues to open

Drafts, in build order, for the first version in `PROJECT.md`. Open them once
Mona has said yes to that scope: one Feature issue each (the template asks for
the same three things), then `@claude` on the first. Each builds on the one
before it. Delete this file when they are all open.

## 1. Load her spreadsheet

- **Scope line:** Her spreadsheet loads into the app.
- **Outcome:** The entries from her sheet are in the database, in her sectors and
  sections, all marked "to check", and a report lists the terms translated
  differently in different tabs.
- **Checks:**
  - A made-up sheet in the same shape (French, Arabic, English, variants joined by
    " - ", numbered outline lines, a sources column) loads into the entries a unit
    test expects: variants split, the outline kept as sections in order, web
    addresses kept as sources.
  - Loading the same sheet twice changes nothing (each row keeps its sheet and row
    as its source key).
  - Editors and admins can read every entry; a signed-in colleague reads only
    verified ones; a visitor reads none (pgTAP).
- **Notes:** the loader reads the file from a path given when it runs
  (`client-files/`), never from the repository, and the tests use a made-up sheet.
  The data model must fit other sectors and country labels too, not only religion.

## 2. Search everything

- **Scope line:** Search everything.
- **Outcome:** One box finds an entry from any of its languages, variants,
  pronunciation or note, as you type, on the phone.
- **Checks:** "How search behaves" in `PROJECT.md`, one unit test per rule
  (accents, Arabic marks and letter forms, variants, pronunciations, the order of
  results), and an end-to-end test that types and sees results in under a second
  at 360 px.

## 3. Answer at a glance

- **Scope line:** Answer at a glance.
- **Outcome:** The best match's equivalent shows large at the top of the results.
- **Checks:** at 360 px the equivalent is readable without scrolling or opening
  anything; Arabic shows right to left; axe passes.

## 4. Entry page

- **Scope line:** Entry page.
- **Outcome:** French, Arabic and English side by side, with variants, the note,
  sources as links and a copy button on each term.
- **Checks:** copy puts the exact term on the clipboard; sources open as links;
  Arabic is right to left; the layout holds at 360 px.

## 5. Sectors and the filter

- **Scope line:** Sectors.
- **Outcome:** The five sectors as top-level sections, and a sector filter on search.
- **Checks:** filtering by a sector shows only its entries; an empty sector says so.

## 6. Browse by topic

- **Scope line:** Browse by topic.
- **Outcome:** Each sector as a tree, in her order.
- **Checks:** the tree follows the sheet's outline order; every entry is reachable.

## 7. Works offline

- **Scope line:** Works offline.
- **Outcome:** The app installs on a phone, keeps every published entry on the
  device, and searches with no signal.
- **Checks:** with the network cut, search still answers from the device; after a
  new entry is verified, the device has it on its next visit online.

## 8. Colleague access

- **Scope line:** Colleague access.
- **Outcome:** Colleagues sign in with an email link she sends, and see verified
  entries only.
- **Checks:** an invited colleague signs in and sees verified entries; a "to check"
  entry never reaches them, online or on the device (pgTAP and end-to-end).

## 9. Her editor

- **Scope line:** Her editor.
- **Outcome:** She adds, corrects and verifies entries from her phone or a laptop.
- **Checks:** a new entry, a correction and a verification each show at once and
  survive a reload; a translation that clashes with an existing one warns her
  before saving; colleagues cannot edit (pgTAP).

## 10. Missing-word requests

- **Scope line:** Missing-word requests.
- **Outcome:** When a search finds nothing, one tap sends the word to her list.
- **Checks:** the word reaches her list; nothing else about the search is stored
  (pgTAP: the table holds the word, the sector filter and the day, nothing more).
