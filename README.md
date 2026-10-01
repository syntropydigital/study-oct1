# study-oct1

A locked, static copy of my Oct 1 study app, for reading on a machine where the
Cloudflare URL is blocked.

Every page is encrypted (AES-256-GCM, PBKDF2-SHA256, 400,000 iterations) and
decrypted in the browser. Without the passphrase there is nothing readable here.

**What's inside:** the Bolos (Reason and Revelation) and Hutton (King David)
exam guides, a drill sheet for each course (every fair-game question argued with
citations, plus ten points on each person, term and author), a walkthrough of
every assigned reading, the Craig cross-reference, the Tuesday readings, the
flashcards, the quiz bank, the essay outlines and the diagrams.

Virtue ethics is held back from the cards and quiz bank: Bolos took it off
Exam 1 on 29 September and moved it to Exam 2.

**How it differs from the live app**

- No narration audio, so the Listen controls are hidden.
- No server: no device lock, no syncing between machines. Progress is kept in
  each browser's own storage.
- Reynolds's Crime and Punishment guide is not in this copy.

## Rebuilding

    python3 build/export_static.py  ~/.local/share/study/static-export /study-oct1/
    python3 build/encrypt_site.py   ~/.local/share/study/static-export /study-oct1/ "$(head -1 ~/.local/share/study/PASSPHRASE.txt)"

Both scripts live in the app source at `~/.local/share/study/app/build`.
