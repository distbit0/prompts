Todo source and scope: "$ARGUMENTS" is either empty or a file name. If it is a file name, use that file as the todo source, which means the todos below the line "# -- SCRATCHPAD" or "# todos" in that file. Only modify that file, though you can read other files if helpful. If there are no todos below "# -- SCRATCHPAD" or "# todos", read todos from the clipboard using `xclip -o -selection clipboard`. Append the clipboard content below "# -- SCRATCHPAD" in that file, then treat the appended lines as the todo source so they can be removed as you complete them. If "$ARGUMENTS" is empty, use the repo's todo file and normal scope.

For each todo in the source:
- Find the files, code, documents, or sections it relates to, and propose a change that addresses it.
- Ask me if this is correct or if I would like to offer a clarification.
- Keep updating your suggestion based on my clarification until I accept it, or I implicitly accept it by telling you to take an action.
- Implement your suggestion and remove the todo from the todo file.
- Move to the next todo until all are complete. Do not skip any unless I ask you to.
