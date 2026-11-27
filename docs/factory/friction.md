# Friction log

What slowed an agent or the owner down, or let a mistake through, in this client
project. One line each, added in the same pull request as the work, by whoever hit
it. Lines that would help every client project go back to the template too.
Short and factual: never the client's data or names.

Format: `- YYYY-MM-DD · area · what happened · what would have prevented it (guess)`

## Open

- 2026-11-27 · guard · `npm run guard` died with a stack trace in a fresh clone, because `origin/main` had not been fetched · the guard naming the missing ref and the fetch command (done in the template; copy `scripts/guard.mjs` here)

## Done
