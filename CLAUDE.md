# Sanskrit vibhakti flashcards

Single self-contained page: `index.html` (HTML, CSS and JS inline, no build step).

## Data (top of the <script>)
- `TPL`: declension templates. Endings are appended to an a-final base (देव, मुन, पित).
  `|` separates accepted alternate forms; `_` means an empty ending.
- `natva()` applies the n→ṇ rule; `decline(base, tpl)` generates the 8×3 table.
- `TYPES`: stem types and their words, as rows of [id, stem, base, template, English, Hindi].
  Types marked `hidden: true` are left out of the case decks but their words stay in vocabulary.
- Pronouns are hand-written with `P(...)`.
- `SENTS`: gap-fill sentences; the first option is the correct one; `c` is the case index (0–7).
- `VOCAB`: [word, grammar note, English, Hindi]. Case-deck nouns are appended to it automatically.

## Rules
- Progress is stored by card id. Vocabulary ids use the array index, so only APPEND to
  `VOCAB` and `SENTS`; never reorder or delete entries. Keep existing paradigm ids
  (deva, muni, pitr…) unchanged.
- After changing declension data, print a few generated tables and check them by eye,
  especially words with र, ष or ऋ (णत्व).
- The `window.claude` sync code is inactive outside claude.ai and falls back to localStorage;
  it can be removed.
