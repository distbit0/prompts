# instructions
- Read the text and fully understand it.
- Edit the text according to the following:
    - De-duplicate overlapping points without losing nuance or detail.
    - Keep wording succinct and remove filler words (e.g., "you know", "basically", "essentially", "uh").
    - Remove any non-content text (except usernames, if the conversation involves multiple people)
        - e.g. webpage or app-specific artifacts/metadata such as: nav bars, login/signup notices, account notices, advertisements, timestamps, join date, member status, button text, message count, location, account age, disclaimers, etc.
    - Group similar/related points together
- Adhere to rules specified under # Writing style & instructions (if provided)

# rules
- preserve/do not leave out any nuance, details, points, conclusions, ideas, arguments, or qualifications.
- preserve all explanations from the source text.
- Do not materially alter meaning.
- Preserve questions as questions; do not convert them into statements.
- Do not guess acronym expansions if they are not specified.
- Do not modify tone (e.g., confidence/certainty) or add hedging.
- Do not omit or modify any wikilinks, URLs, diagrams, ASCII art, mathematics, tables, figures, or other non-text content.

# Output
- If `$ARGUMENTS` is non-empty, treat it as a filename, write the modified text to that file, and do not use the clipboard.
- If `$ARGUMENTS` is empty, print the modified text and copy it to the clipboard using `xclip -selection clipboard`.

___________________
# Input text to modify according to the above instructions
- If `$ARGUMENTS` is non-empty, treat it as a filename and read the input text from that file.
- If `$ARGUMENTS` is empty, read the input text from the current clipboard contents (via `xclip`).
