# The problem with vague prompts

**Prompt:** *"Write a Python endpoint that returns user profile data."*

AI produces working code. Passes basic SAST. But:
- Missing authorization check — any authenticated user can retrieve any profile by ID
- Nothing in the code explains why the check is absent

**Vibe coding** can lead to insecure or inconsistent implementations across the codebase.

**The spec-driven idea in one sentence:**
Write a short specification first — what the code must do, what it must **not** do, which security constraints apply, then iterate with the AI on that spec until it is solid. Only **then** ask the AI to write code based on the refined spec.

> "When a developer writes 'this endpoint must never return data belonging to another user', three things happen: the AI follows the constraint, the reviewer can verify it, and the auditor has evidence it was considered."

*We'll come back to this in about an hour — and I think it will change how you think about prompting entirely.*
