If `$ARGUMENTS` is non-empty, treat it as a filename, refactor the contents of that file in place, and write the updated code back to the same file.

Refactor $ARGUMENTS to **minimize LOC and cognitive load** without changing externally observable behavior.

Treat this as a “delete-first” cleanup: remove dead code, merge duplicated logic, eliminate unnecessary abstraction, and make control/data flow obvious at a glance.

**Concrete cleanup tactics to apply aggressively**

* **Flatten**. Avoid deep call chains and pass-through wrappers. Prefer a few well-named intermediate locals over values threaded through 3–6 functions.
* Don’t add pass-through parameters unless they represent legitimate context for that layer
* Keep orchestration thin; keep computation in a small number of semantically clear functions.
* Keep functions mostly pure; avoid module-level mutable state and “hidden” caching.
* Remove all redundant, silent or overly risk averse/code-bloat fallbacks.
* **Delete with prejudice:** remove unused variables, unused dict keys, unreachable branches, obsolete code paths, commented-out chunks, and “future-proof” scaffolding that isn’t used.
* **Inline trivial helpers:** if a helper is both trivial and only called once and isn’t conceptually reusable, inline it and delete it.
* **Collapse duplication into a single source of truth:** if two branches differ only by small parameter tweaks, unify them by computing the differing pieces once (via locals) and reusing one shared block.
* **Unify near-duplicate functions with a parameterized core:** if you have `compute_x_for_mode_a` and `compute_x_for_mode_b` that share 80–95% logic, create `compute_x(mode, ...)` (or two thin front-doors calling one core) so the shared logic lives once.
* **Normalize data early:** if the module repeatedly transforms/validates the same inputs, do it once near the boundary, then operate on a consistent internal representation.
* **Prefer explicit locals over cleverness:** avoid “action at a distance” (mutating dicts passed around, implicit globals). Make dependencies explicit via function inputs and clear return values.
* **Shrink complex conditionals:** pull repeated sub-conditions into a single well-named boolean local (e.g. `is_using_oracle_price`) so logic reads like prose.
* **Unify error handling:** if the same error checks/log messages appear in multiple places, centralize them once (but don’t add new validation everywhere).
* **Prefer one “core computation” function per concept:** if multiple functions each compute the same “thing” in slightly different formats, pick one canonical internal form, compute it once, and convert at the edges.
* Do not make any already large functions even bigger.
