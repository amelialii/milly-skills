---
name: note-linking
description: Add Obsidian [[wikilinks]] between notes in my vault (millynotes) without changing any wording. Use when new notes are added, or when I ask to "look through notes and add links".
---

# Note Linking

Inputs: one or more notes to link (paths under `milynotes vault/`). If none are given, ask which notes.

Work in two directions for each input note:
1. **Outbound**: in the input note, link terms to other notes that cover them.
2. **Inbound**: in other notes, link mentions of the input note's main topic(s) to the input note.

Only edit to add links. Change nothing else.

## Relevance bar

Link only when it is really relevant. "Remotely relevant" is not enough.
- The target note, or a heading in it, must be mainly *about* that term. Clicking the link should teach the reader what the term means.
- The term must be used in the same sense. `transaction` in a DB note → yes. "transaction" meaning a payment → no.
- Cross-course links are good when it's the same concept (e.g. Transactions in CSE 444 and in INFO 330/CSE414).
- If unsure, don't link. Fewer links that are all good beat many links.

## Never change wording

Every visible character must stay exactly the same. Only wrap existing text in a link.
- Always use the alias form so the display text stays exactly the original, including case and plural: `heap` → `[[Structs, Heap#Heap-allocated Memory|heap]]`.
- Formatting stays outside the link: `**linker**` → `**[[Linking, File I／O|linker]]**`.
- Link a whole word or phrase, never part of a word.
- Don't add, remove, or reword text, punctuation, whitespace, or line breaks anywhere.

## Link format

- Target = the note's file name without `.md`, copied exactly (some names use special characters like `／`).
- If two notes share a file name (e.g. `Intro`), use the path from the vault root instead: `[[CSE 333/week 1-2/Intro|intro]]`.
- When a specific heading in the target matches the term better than the whole note, add it: `[[Pointers#Output Parameters|output parameter]]`. Copy the heading text exactly.
- Inside a table, escape the alias pipe: `[[Structs, Heap\|struct]]`.

## Where links go

- Link only the **first** mention of a term in a note. Skip it entirely if the note already links to that target (anywhere, any alias).
- Never link inside: frontmatter, headings (`#` lines), fenced or inline code, existing `[[links]]` or `![[embeds]]`, markdown links or URLs, math.
- No self-links (a note linking to itself or its own headings).
- Leave image embeds like `![[file-123.png|448]]` untouched.

## Finish

List every link added as `note: "term" → [[target]]`, grouped by note, so I can review quickly. If nothing met the bar, say so and change nothing.
