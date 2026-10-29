# The engineering standard

Every writer builds to it and the reviewer holds the work against it (galt ADR 0049 D4). A repo extends it in `.galt/crew/standards.md`.

Read before you write: the code around the change, and how this codebase already does the same thing.
Match the codebase's conventions: names, layout, error handling, docs.
One source of truth: reuse what exists (helper, component, store, config); never copy-paste.
Use the codebase's own mechanisms: its store for state, its design system for styling; no ad-hoc state or inline styles where it has them.
Do not build what already exists; search for it first.
Handle errors where the codebase handles them; never swallow one silently.
Every change is proved by a test or a check that fails without it.
The smallest change that does the job: no unrelated edits, no restyling of working code.
Say in your done note what you ran and what it showed.
