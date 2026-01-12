# Input and output
- If `$ARGUMENTS` is non-empty, treat it as a filename, read the text from that file, and when implementing accepted changes, write the updated text back to the same file.
- If `$ARGUMENTS` is empty, read the text from the clipboard via `xclip`, and when implementing accepted changes, print the updated text and copy it to the clipboard via `xclip -selection clipboard`.

# Goal
- Review `$ARGUMENTS` and find instances where adding an example could very clearly improve clarity.

# Workflow
- Propose instances where examples could be added.
  - For each instance, propose what you will use as an example.
- Allow me to reject or accept each proposed example.
  - Allow me to provide an explanation of how I would like you to revise them before implementing them.
- If I do not ask you to revise them, implement them.
- If I ask you to revise them, revise them and come back to me with the same prompt.
  - Repeat until I accept without revisions.
  - Then implement.