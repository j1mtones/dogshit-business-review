---
name: business-spec
description: Use when the user wants to catalogue, log, write up, or add a new business idea as an Idea Brief. Trigger on phrases like "add this to my business ideas", "write up this idea", "new idea brief", or when the user pitches a business/startup concept and wants it saved/catalogued — even if they don't name the skill directly. Also trigger if they ask to see the format of existing idea briefs before adding a new one.
---

# Business Spec (Idea Brief)

Turn a business idea the user gives you into a formatted Idea Brief, saved as a markdown file in the local repo (not Drive — Drive docs created via the API can't be edited afterward by this skill or `grill-business-spec`, and the brief needs to stay editable after the grilling interview).

## Before writing

1. If you haven't seen the format before, check the "Business Ideas" Google Drive folder (ID `1S2Ikyh3rPT7_ETTJlq1zbwEBwdo0QCJJ`) for 1-2 existing briefs (`search_files` scoped to the folder, then `read_file_content`) to match section order, tone, and table style already in use there. That folder is a format reference only — the new brief itself is not written there.
2. Ask the user to fill in details for each category of the brief up front, listing the categories out for them: Header, Problem, Solution, Target Customer, Market & Competition, Business Model, Distribution, Why Us, Risks & Open Questions. (Omit Next Steps from this list — that section is generated later, not filled in by the user now.)
3. Research real competitors — web search, don't invent names or claim numbers you didn't find. If you can't verify a fact (market size, competitor pricing), say so ("unverified") rather than fabricate it. Only research to support categories the user actually gave you content for — don't invent content for a category the user left out.

Any category the user doesn't give you content for stays blank in the doc — do not fill it in with assumed or invented context.

## Writing style

Terse. Cut filler words, hedges, articles where meaning survives without them. Fragments over full sentences where clarity holds. This is a working doc, not prose — a founder should skim it in 90 seconds. Still needs to read as professional, not sloppy.

## Doc structure

Title: `[Idea Name] — Idea Brief`

- **Header** — one-liner, status (Idea/Exploring/Validating), owner, date
- **Problem**
- **Solution**
- **Target Customer**
- **Market & Competition** — real comp research (names, pricing, positioning), not guesses
- **Business Model** — table, columns: `Stream | When (launch vs. later) | Pros | Cons`. Separate self-serve/no-sales-team revenue from partnership-dependent revenue as distinct rows. Explicitly call out (a line below the table is fine) which stream actually funds the core value prop at launch.
- **Distribution** — how *this* idea specifically gets its first users/customers, not generic "SEO + social" advice. Tie it to where this customer already is.
- **Why Us**
- **Risks & Open Questions**
- **Next Steps**

Use real markdown: `#`/`##` headings, `-` bullets, and a `|` pipe table for Business Model — so it imports as a formatted Doc, not a wall of plain text.

Next Steps is not filled in at this stage — leave it as an empty section heading; it gets generated later (after grilling). Any other category the user didn't provide content for is also left as an empty heading, not filled with guesses.

## Creating the file

Write the markdown to `business-ideas/[idea-name-slugified].md` in the current repo (create the `business-ideas/` directory if it doesn't exist). Slugify the idea name for the filename (lowercase, hyphens), but keep the human-readable `[Idea Name] — Idea Brief` as the `#` title inside the file.

## When done

Reply with the file path. Then immediately continue in the same chat by invoking the `grill-business-spec` skill on the brief you just wrote — don't wait for the user to ask. That skill interviews the user to pressure-test the assumptions in the doc, and since the file is local, the resulting edits can go straight back into it.
