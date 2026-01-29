Read the input spec or todos then implement items from it by first optionally running a structured, non-obvious, in-depth interview and optionally producing `plan/plan.md` after the interview, then making code changes.

Files live under `plan/`:
- Inputs: `plan/todo.md` and optionally `plan/spec.md`
- Optional communication artifacts: `plan/interview.md`, `plan/plan.md`

Todos come only from `plan/todo.md`, `plan/spec.md`, and clarified answers in `plan/interview.md`.

Ensure `plan/*` is tracked in git and not ignored.

Workflow:

1) Parse `plan/todo.md` and extract each distinct feature/change request.

2) Present the extracted requests as a numbered list, then ask the user for a single reply containing:
   - Which items to implement now (numbers like `1, 3, 4`), OR whether instead to use `plan/spec.md` as the source for what to implement, OR a free-form description of what to do. (default: move all TODO items)
   - Whether to run an interview first (yes/no). (default: no)
   - Whether to write `plan/plan.md` before implementing (yes/no). (default: no)

Do not proceed until the user replies. Use defaults for anything not addressed.

3) Review the codebase and conduct web searches as needed to devise implementation approach, interview questions (if requested) & plan contents (if requested). Do not implement or modify any code yet.

4) If interview was requested:
   - Write `plan/interview.md` first, before asking any questions in the terminal.
   - Only include questions relevant to the selected todos / or `plan/spec.md`.
   - Questions must be specific and non-obvious, grounded in the codebase where helpful.
   - If `plan/interview.md` contains unrelated content, delete it first.
   - Format:
     - Each question is a markdown block quote line starting with `> `
     - Append to each question "Default answer: " and then specify the default answer (how you will resolve the question if the user doesn't answer it)
     - After each question, add two blank non-block-quote lines for answers
     - Group questions by selected TODO item with headings
   - After writing the questions, ask them in the terminal one at a time, in the same order as `plan/interview.md`.
   - After each user answer, immediately write the answer into `plan/interview.md` under that question (replacing the blank space), then move to the next question.
   - Accept explicit “use default” as an answer and record it as such in `plan/interview.md`.

5) After the user is finished (or if no interview):
   - re-execute step 3) as/if needed
   - Ask follow-up questions only if gaps block correct implementation.
   - If follow-ups are needed, append the questions to `plan/interview.md` first (same format), then ask them in the terminal one at a time and write answers back into `plan/interview.md` before continuing.

6) Make a git commit capturing:
   - the current state of `plan/todo.md` (and `plan/spec.md` if used)
   - `plan/interview.md` answers if any
   This commit is a rollback point.

7) If `plan/plan.md` was requested:
   - Present the plan section by section in the terminal, explicitly asking for approval of each section before moving on.
   - Before presenting any section in the terminal, write it to `plan/plan.md` first (so the file stays coherent with what is shown).
   - Workflow:
     - Start `plan/plan.md` with the section outline/headings.
     - For each section:
       - Write/update `plan/plan.md` so it contains the full plan with the current section filled in (and previously approved sections unchanged).
       - Present only that section in the terminal.
       - Ask for approval or edits for that section, then iterate until approved.
   - After all sections are approved, STOP and ask:
     "proceed to implement now? (yes/no)"

8) Implementation
* Only start after all plan sections are approved (if a plan was requested) and I explicitly approve starting.
* If I request plan changes: update `plan/plan.md` and re-present only the affected sections for approval before continuing.

9) When implementation is finished:

* Summarize changes and map them to each selected TODO item (or `plan/spec.md` if used).
* Remove completed items from `plan/todo.md` without disturbing unrelated items.
