# instructions
- Read the text and fully understand it.
- Edit the text according to the following:
    - Break content into relatively atomic bullet points; each bullet should express one idea.
    - use dot point nesting where one point is naturally a sub-point of another
    - Make minor grammar edits as needed so ideas read cleanly as bullet points.
    - De-duplicate overlapping points without losing any nuance or detail.
    - Keep wording succinct and remove filler words (e.g., "you know", "basically", "essentially", "uh").
    - Add new headings, sub-headings, or parent bullet points for new items, and reuse existing ones where appropriate.
    - Remove any non-content text (except usernames, if the conversation involves multiple people)
        - e.g. webpage or app-specific artifacts/metadata such as: nav bars, login/signup notices, account notices, advertisements, timestamps, join date, member status, button text, message count, location, account age, disclaimers, etc.
    - Group similar/related points together

# rules
- PRESERVE/DO NOT LEAVE OUT ANY NUANCE, DETAILS, POINTS, CONCLUSIONS, IDEAS, ARGUMENTS, OR QUALIFICATIONS from the notes.
- preserve any obviously-intentional, clear and regular sub-headings/heading structure, if applicable
- PRESERVE ALL EXPLANATIONS FROM THE NOTES.
- Do not materially alter meaning.
- Preserve questions as questions; do not convert them into statements.
- Do not guess acronym expansions if they are not specified.
- Do not modify tone (e.g., confidence/certainty) or add hedging.
- Do not omit or modify any wikilinks, URLs, diagrams, ASCII art, mathematics, tables, figures, or other non-text content.

# formatting
- use markdown headings # for headings
- use "- " as the prefix for the bullet points under headings, not "* ", "-   " or anything else

# verification
- before you return, carefully go through all of the original points and make sure:
    - EVERY SINGLE ONE is included in your re-grouped output
    - no points have had their meaning materially modified

# Output
- If `$ARGUMENTS` is non-empty, treat it as a filename, write the modified text to that file, and do not use the clipboard.
- If `$ARGUMENTS` is empty, print the modified text and copy it to the clipboard using `xclip -selection clipboard`.

___________________
# Input text to modify according to the above instructions
- If `$ARGUMENTS` is non-empty, treat it as a filename and read the input text from that file.
- If `$ARGUMENTS` is empty, read the input text from the current clipboard contents (via `xclip`).
