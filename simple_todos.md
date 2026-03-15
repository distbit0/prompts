Todo source and scope: "$ARGUMENTS" is either empty or a file name.
If it is a file name, todos to be completed are listed at the bottom of the file. Only modify that file, though you can read other files if helpful. If "$ARGUMENTS" is empty, use the repo-wide todo or spec file and repo-wide editing scope.

Default workflow: plan first, then implement.

Phase 1: clarify and plan (no implementation yet):
- Work through the todo list one todo at a time. If it is a spec, treat it as a series of sub-parts of each you can ask questions about. 
- For the current todo, first find the code, documents, or sections it requires modification of, then propose an approach that addresses it.
    - Ask only non-obvious questions that resolve material ambiguity about my intent.
        - Use questions to support planning and implementation, and ask me to confirm the approach for the TODO.
        - Do not ask obvious or confirmatory questions.
        - Ask many questions, ideally which are generative, surface significant/important trade-offs, help me clarify intent, and highlight/help resolve potential contradictions and help me provide necessary info for you to implement the todos/spec. make sure questions reflect deep thought about the task and the available approaches and potential objectives I might have in mind.
    - If a todo ends with ##, this indicates it is complex so you should think about it/investigate even more thoroughly and ask a large number of questions
    - Append to each question "Default answer: " and then specify the default answer (how you will resolve the question if the user doesn't answer it)
        - If I do not address a question in my next msg, it means I agree with your default answer. Do not follow up or ask me the same question again!
    - let my answers to earlier todos inform what questions you ask for subsequent todos/spec sub-parts.
- Keep updating that todo's approach based on my clarifications until I accept it, or I implicitly accept it.
- After the current todo's approach is accepted, record a concrete plan for it based on my comments, elaborations, and responses:
  - If "$ARGUMENTS" is empty, write the plan to its own file under `plan/` (create the directory if needed), using a concise descriptive filename for that todo and adding a numeric prefix only when needed to keep filenames unique and ordered.
    - Make sure each plan file is completely self-contained and doesn't require the original todos nor my answers to your questions as context in order to be understood and executed. Ensure all relevant context is provided.
    - Do not include the original text of the todo in the plan file.
  - If "$ARGUMENTS" is a file name, append the plan as indented text directly below that todo in the same file, so the plan is visually nested under the todo item.
- Do not ask questions for later todos until the current todo is accepted and planned.
- After planning the last todo, check whether any new todos have been added.
- Do not skip any todos unless I ask you to.

Once finished phase 1, ask if I'd like to continue to phase 2 or if I have any other requests/comments/critiques before implementing. Also ask me whether to run a critique sub-agent on the plan. If so, please have a sub-agent critique the plan in the context of the relevant code and my implicit + stated goals.
Phase 2: implement (driven by the recorded plan):
- Only start implementing once Phase 1 is complete for all todos (except those I asked to skip).
- Make one commit after implementing each todo.
- Use a sub agent to implement each todo, but only run > 1 in parallel where this will not result in conflicts.
- If I tell you to start implementing the todos covered so far and skip the rest, do that even if there are remaining todos.
- For each todo you implement, refer to the recorded plan (inline under the todo when "$ARGUMENTS" is a file name, or that todo's file under `plan/` when "$ARGUMENTS" is empty) to determine what to do. Mark each todo as complete in its plan as you complete them.
- Implement each todo's plan, then modify the plan file and todo file to mark that todo as complete, then move onto the next todo's plan file.
- Once implementation of a per-todo plan file is complete, copy it to `plan/archived/` using the same filename, then remove it from `plan/`.
