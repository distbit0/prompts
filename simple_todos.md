Todo source and scope: "$ARGUMENTS" is either empty or a file name.
If it is a file name, todos to be completed are listed at the bottom of the file. Only modify that file, though you can read other files if helpful. If "$ARGUMENTS" is empty, use the repo-wide todo file and repo-wide editing scope.

Default workflow: plan first, then implement.

Phase 1: clarify and plan (no implementation yet):
- For every todo, find the code, documents, or sections it requires modification of, and propose an approach that addresses it.
- Ask me any questions needed to remove ambiguity, and ask me to confirm the approach.
- Keep updating the approach based on my clarifications until I accept it, or I implicitly accept it by telling you to take an action.
- After each todo is covered and its approach is accepted, record a concrete plan for that todo based on my comments, elaborations, and responses:
  - If "$ARGUMENTS" is empty, append the plan to `plan/PLAN.md` (create it, and the `plan/` directory, if needed).
  - If "$ARGUMENTS" is a file name, append the plan as indented text directly below that todo in the same file, so the plan is visually nested under the todo item in the Markdown list.
- Check whether any new todos have been added.
- Do not skip any todos unless I ask you to.

Start phase to immediately. Do not wait for confirmation to implement after writing the PLAN.md.
Phase 2: implement (driven by the recorded plan):
- Only start implementing once Phase 1 has asked questions for all todos (except those I asked to skip).
- If I tell you to start implementing the todos covered so far and skip the rest, do that even if there are remaining todos.
- For each todo you implement, refer to the recorded plan (inline under the todo when "$ARGUMENTS" is a file name, or `plan/PLAN.md` when "$ARGUMENTS" is empty) to determine what to do.
- Implement the plan, remove the todo from the todo file, then move to the next todo.