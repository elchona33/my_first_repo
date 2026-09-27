# AGENTS.md

This repository uses the following shared rule for AI coding agents. The Context7 rules apply only when a task actually depends on external software documentation.
## External documentation and Context7

When a task depends on the behavior, API, configuration, or recommended usage of an external library, framework, SDK, API, or platform:

1. Inspect the dependency/version actually used by this repository first (manifest, lockfile, config, or existing imports).
2. Use Context7 before implementing the relevant code to retrieve current documentation, preferring documentation compatible with the version used by the repository.
3. Do not assume an external API exists or behaves a certain way only from model memory.
4. Preserve the repository's current compatible patterns unless the task explicitly requires a migration or upgrade. Do not upgrade dependencies merely to match newer documentation.
5. If Context7 is unavailable or does not cover the needed library/version, prefer official documentation and make any remaining assumption explicit.
6. The repository remains the source of truth for project-specific architecture, business rules, schemas, conventions, and existing behavior. Context7 does not override local code or project documentation.
7. Skip Context7 when the task is purely internal and can be resolved from the repository itself (for example copy/content changes, research files, simple refactors, or project-specific business logic with no external API question).

Use this especially for fast-moving dependencies such as web frameworks, React ecosystems, Supabase, Vercel SDKs, auth libraries, validation libraries, testing tools, cloud SDKs, and third-party APIs.

