Todo source and scope: "$ARGUMENTS" is either empty or a file name.
If it is a file name, todos to be completed are listed at the bottom of the file. Only modify that file, though you can read other files if helpful. If "$ARGUMENTS" is empty, use the repo-wide todo file and repo-wide editing scope.

Default workflow: plan first, then implement.

Phase 1: clarify and plan (no implementation yet):
- Work through the todo list one todo at a time.
- For the current todo, first find the code, documents, or sections it requires modification of, then propose an approach that addresses it.
- Then ask me only non-obvious questions to remove actual & material ambiguity/uncertainty regarding my intent, to facilitate planning+implementation and to ask me to confirm the approach for that todo. Pls do not waste my time with obvious/confirmatory questions. But ideally ask me quite a few questions, esp. if they are generative/divergent/useful and reflect. deep thought about the task at hand and potential approaches or potential goals I might have.
    - If a todo ends with !, this indicates it is complex so you should think about it/investigate even more thoroughly and ask a large number of questions
    - Append to each question "Default answer: " and then specify the default answer (how you will resolve the question if the user doesn't answer it)
        - If I do not answer a question, it means I selected the default answer. 
- Keep updating that todo's approach based on my clarifications until I accept it, or I implicitly accept it.
- After the current todo's approach is accepted, record a concrete plan for it based on my comments, elaborations, and responses:
  - If "$ARGUMENTS" is empty, append the plan to `plan/PLAN.md` (create it, and the `plan/` directory, if needed).
    - Make sure the plan you append to PLAN.md is completely self-contained and doesn't require the original todo as context in order to be understood & executed
  - If "$ARGUMENTS" is a file name, append the plan as indented text directly below that todo in the same file, so the plan is visually nested under the todo item.
- Do not ask questions for later todos until the current todo is accepted and planned.
- After planning the last todo, check whether any new todos have been added.
- Do not skip any todos unless I ask you to.

Once finished phase 1, ask if I'd like to continue to phase 2 or if I have any other requests/comments/critiques before implementing.
Phase 2: implement (driven by the recorded plan):
- Only start implementing once Phase 1 is complete for all todos (except those I asked to skip).
- If I tell you to start implementing the todos covered so far and skip the rest, do that even if there are remaining todos.
- For each todo you implement, refer to the recorded plan (inline under the todo when "$ARGUMENTS" is a file name, or `plan/PLAN.md` when "$ARGUMENTS" is empty) to determine what to do. Mark each todo as complete in the plan as you complete them.
- Implement the plan for each todo, then modify the PLAN and todo file to mark that todo as complete, then move onto the next todo int he PLAN file.