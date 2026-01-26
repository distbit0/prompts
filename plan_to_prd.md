Your job is to translate the plan document ($ARGUMENTS) into a series of tasks to add to `plan/prd.json`.

Do NOT treat `plan/prd.json` as a requirements input. New requirements come only from $ARGUMENTS

1) Generate or update `plan/prd.json` as a JSON array of objects, where each object has exactly:
   - feature_description: string
   - details: string
   - test_steps: array of strings (step-by-step)
   - passes: boolean (initialize to false for new/changed items)

PRD generation rules:
- Decompose the plan document into relatively self-contained/manageable features that can be implemented and verified independently.
- `plan/prd.json needs to make sense completely independently of the plan document. Provide all required context in each prd item.
- Write test_steps that can validate correctness (i.e. explain how to test if the feature is working as intended).
- passes starts false; do not set it to true.
- leave unaffected existing entries in `plan/prd.json` unchanged, but ensure there are no duplicate entries

2) Make a git commit for the PRD update (e.g. "Update PRD backlog").

Stop after the PRD commit. Do not implement anything.