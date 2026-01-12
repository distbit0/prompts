# Instructions
- If `$ARGUMENTS` is non-empty, treat it as a filename, read the input text from that file, modify it according to the instructions provided under # Writing style & instructions, and write the output back to the same file.
- If `$ARGUMENTS` is empty, read the input text from the current clipboard contents (via `xclip`), and copy the output to the clipboard as well (via `xclip -selection clipboard`).
