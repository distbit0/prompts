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
  - If "$ARGUMENTS" is empty, write the plan to its own file under `plan/` (create the directory if needed), using a concise descriptive filename for that todo.
    - Make sure each plan file is completely self-contained and doesn't require the original todos nor my answers to your questions as context in order to be understood and executed. Ensure all relevant context is provided.
    - Do not include the original text of the todo in the plan file.
  - If "$ARGUMENTS" is a file name, append the plan as indented text directly below that todo in the same file, so the plan is visually nested under the todo item.
- Do not ask questions for later todos until the current todo is accepted and planned.
- After planning the last todo, check whether any new todos have been added.
- Do not skip any todos unless I ask you to.

Once finished phase 1, ask if I'd like to continue to phase 2 or if I have any other requests/comments/critiques before implementing. Also ask me whether to run a critique sub-agent on the plan. If so, please have a sub-agent critique the plans in the context of the relevant code and my implicit + stated goals.
When moving to phase 2, use the current worktree only for coordination and bookkeeping; use per-todo worktrees for implementation.
Phase 2: implement (driven by the recorded plan):
- Only start implementing once Phase 1 is complete for all todos (except those I asked to skip).
- Treat the current worktree as the coordinator worktree. It owns the todo file and all `plan/` files.
- Only the coordinator worktree may modify the todo file, mark plan steps complete, archive plan files, or mark a todo as complete.
- For each todo, create a dedicated git branch and git worktree before spawning its implementation sub-agent.
- Run that todo's implementation sub-agent only inside its dedicated worktree.
- The implementation sub-agent may read the recorded plan and todo file, but must not modify `plan/` files or the todo file. It should only implement the todo's code or document changes in its own worktree.
- Make one commit in the todo's dedicated worktree after implementing that todo.
- Use a separate worktree for each todo you implement. Only run > 1 implementation sub-agent in parallel when their planned file edits will not conflict.
- If I tell you to start implementing the todos covered so far and skip the rest, do that even if there are remaining todos.
- After a todo's implementation sub-agent finishes, integrate its commit back into the coordinator worktree by cherry-picking that todo commit unless I instruct otherwise.
- For each todo you implement, refer to the recorded plan (inline under the todo when "$ARGUMENTS" is a file name, or that todo's file under `plan/` when "$ARGUMENTS" is empty) to determine what to do.
- After the implementation commit is integrated into the coordinator worktree, update the recorded plan to mark its steps complete, then modify the todo file to mark that todo as complete.
- Once implementation of a per-todo plan file is complete, copy it to `plan/archived/` using the same filename, then remove it from `plan/`.
- After the todo is integrated and its bookkeeping is complete, remove its dedicated worktree and delete its temporary branch if it is no longer needed.
