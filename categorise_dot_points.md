# Input and output
- If `$ARGUMENTS` is non-empty, treat it as a filename, read the input text from that file, and write the updated text back to the same file.
- If `$ARGUMENTS` is empty, read the input text from the clipboard via `xclip`, and print the updated text and copy it to the clipboard via `xclip -selection clipboard`.

Make sure that points in $ARGUMENTS are properly categorised by markdown headings. Create new markdown headings if necessary. Make sure no points are in incorrect categories and if any categories stand out as obviously missing, pls add them.

# instructions
- Read the text and fully understand it.
- Edit the text according to the following:
    - Make minor grammar edits as needed so ideas read cleanly as bullet points.
    - De-duplicate overlapping points without losing any nuance or detail.
    - Keep wording succinct and remove filler words (e.g., "you know", "basically", "essentially", "uh").
    - Group similar/related points together

# rules
- PRESERVE/DO NOT LEAVE OUT ANY NUANCE, DETAILS, POINTS etc.
- Do not materially alter meaning.
- Preserve questions as questions; do not convert them into statements.
- Do not guess acronym expansions if they are not specified.
- Do not modify tone (e.g., confidence/certainty) or add hedging.
- Do not omit or modify any wikilinks, URLs, diagrams, ASCII art, mathematics, tables, figures, or other non-text content.
