If `$ARGUMENTS` is non-empty, treat it as a filename, read the contents from that file, and critique it.

If `$ARGUMENTS` is empty, read the contents from the clipboard via `xclip`, critique it, and copy the critique to the clipboard via `xclip -selection clipboard`.

Critique and find as many material logical, mathematical, conceptual, or internal-consistency problems as you can in the following: `$ARGUMENTS`.

Focus on abstract and conceptual issues, incl. the underlying explicit/implicit assumptions, not nitty-gritty code issues. Put substantial effort into inferring the likely goal of each part before evaluating it, so you can judge each part against its intended purpose.

Very thoroughly review all ideas, solutions, assumptions, and conclusions, and identify logical or conceptual errors, inconsistencies, contradictions, ambiguity, confusion, redundancy, superfluous logic, unresolved problems, or architectural issues.

Prioritize critiques that are non-obvious, interesting, decisive or significant, and novel.

Make sure to explain for each, why it is actually problematic.

Use sub agents to parallelize critique generation for different sections and or using different approaches per agent.