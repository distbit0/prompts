If `$ARGUMENTS` is non-empty, treat it as a filename, read the contents from that file, and critique it.

If `$ARGUMENTS` is empty, read the contents from the clipboard via `xclip`, critique it, and copy the critique to the clipboard via `xclip -selection clipboard`.

If it is a plan/spec, make sure to also read all code related to the changes and functionality which it describes. Do not just critique the plan in isolation, always critique it in the context of the existing code which it intends to modify.

Critique and find as many material logical, mathematical, conceptual, or internal-consistency problems as you can in the following: `$ARGUMENTS`.

Focus on abstract and conceptual issues, incl. the underlying explicit/implicit assumptions, not nitty-gritty code issues. Put substantial effort into inferring the likely goal of each part before evaluating it, so you can judge each part against its intended purpose.

Very thoroughly review all ideas, solutions, assumptions, and conclusions, and identify logical or conceptual errors, inconsistencies, contradictions, ambiguity, confusion, redundancy, superfluous logic, unresolved problems, or architectural issues.

Prioritize critiques that are non-obvious, interesting, decisive or significant, and novel.

Make sure to explain for each, why it is actually problematic. Make sure to properly explain each issue so it can be understood without needing to ask more questions. 

Use sub agents to parallelize critique generation:
- For one set of sub-agents, assign each to analyse all sections using a different approach/focus per sub-agent.