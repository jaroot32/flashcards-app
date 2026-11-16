# Working notes: Flashcards lab

Starter prompt header v1 drafted with help from Claude (Claude Code) from the lab instructions. Disclose this in the README.

## Prompt header v1 (paste at the top of every Copilot prompt; do not edit this version)

```
Project: Flashcards Study App. Single-page app, vanilla HTML, CSS, and JavaScript only.
No frameworks, no build tools. Must run by opening index.html in a browser.
Files: index.html, styles.css, app.js. Only edit the files I name in the task.
Data model (AppState):
  decks: Array<{ id: string, name: string, createdAt: number }>
  cardsByDeckId: Record<string, Array<{ id: string, front: string, back: string, updatedAt: number }>>
  activeDeckId: string | null
  ui: { isModalOpen: boolean, activeCardIndex: number }
Data is saved to LocalStorage (decks, cards, last active deck).
HTML: semantic elements (header, nav, main, section, footer, button).
Class names: lowercase with hyphens (deck-list, card-front). State classes start with "is-" (is-active, is-flipped).
CSS: use CSS variables for colors and spacing. Responsive: works on mobile and desktop.
Accessibility: every input has a matching label (for/id), every button has visible text or an aria-label, visible focus styles.
Keep rendering logic in small, named functions. Explain any part of the code I might not understand.
```

## Prompt header v2 (copy v1 here and add rules as Copilot makes mistakes)

Write down WHY you added each rule. That becomes the reflection bullet "What prompt changes improved AI output."

```
(copy of v1 + your new rules)
```

## AI bug log (fill in as you go; this becomes the reflection)

| Part | What Copilot produced | What was wrong | How I found it | How I fixed it |
|---|---|---|---|---|
| 1 |  |  |  |  |

## Things to test after each Part (from the lab's "AI inconsistency watch")

These are kept OUT of the prompt on purpose so you can see whether Copilot gets them right on its own.

- [ ] Part 1: class names match between index.html and styles.css; every label's `for` matches an input `id`; buttons have accessible names
- [ ] Part 2: Tab stays inside the open modal; Esc closes it; focus returns to the button that opened it; sidebar updates without reload; no duplicate listeners after re-render (click once, does it fire twice?)
- [ ] Part 3: card is not still flipped when Next loads a new card; every card gets a unique id; editing a card updates the current view
- [ ] Part 4: no console errors with fast Next/Prev clicks; no crash at first and last card; keyboard listeners not added twice when re-entering study mode
- [ ] Part 5: refresh keeps decks and cards; last active deck restored; clearing search shows all cards again; search does not change saved data; app survives bad LocalStorage data
- [ ] Part 6: color contrast meets WCAG AA in light and dark mode; empty states ("No decks yet", "No cards found"); empty deck name rejected

## Reflection checklist (5 bullets for README.md, in your own words, no em dashes)

- [ ] Where AI saved time
- [ ] At least one AI bug I identified and how I fixed it
- [ ] A code snippet I refactored for clarity (save a before/after)
- [ ] One accessibility improvement I added
- [ ] What prompt changes improved AI output (v1 vs v2)
