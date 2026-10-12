# Sanskrit vibhakti flashcards

`index.html` (HTML, CSS and JS inline, no build step) plus `examples.js`, loaded with a plain
`<script src>` so the page still works when opened from disk.

## Data (top of the <script>)
- `TPL`: declension templates. Endings are appended to an a-final base (देव, मुन, पित).
  `|` separates accepted alternate forms; `_` means an empty ending.
- `natva()` applies the n→ṇ rule; `decline(base, tpl)` generates the 8×3 table.
- `TYPES`: stem types and their words, as rows of [id, stem, base, template, English, Hindi].
  Types marked `hidden: true` are left out of the case decks but their words stay in vocabulary.
- Pronouns are hand-written with `P(...)`.
- `SENTS`: gap-fill sentences; the first option is the correct one; `c` is the case index (0–7).
- `VOCAB`: [word, grammar note, English, Hindi]. Case-deck nouns are appended to it automatically.
- `EX` (in `examples.js`): example sentence for each vocabulary word, keyed by the VOCAB headword:
  [sentence, English, note]. `{braces}` mark the word; the note names the case and why.
  Every VOCAB word, including the auto-appended nouns, should have an entry.

## Rules
- Progress is stored by card id. Vocabulary ids use the array index, so only APPEND to
  `VOCAB` and `SENTS`; never reorder or delete entries. Keep existing paradigm ids
  (deva, muni, pitr…) unchanged.
- After changing declension data, print a few generated tables and check them by eye,
  especially words with र, ष or ऋ (णत्व).
- The `window.claude` sync code is inactive outside claude.ai and falls back to localStorage;
  it can be removed.
