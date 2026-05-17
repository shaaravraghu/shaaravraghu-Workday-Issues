Title
README module count and module inventory are stale relative to the root Maven build

Issue type
Documentation bug

Severity
Medium

Priority
P2

Affected modules
Repository docs

Affected files
`README.md`
`pom.xml`

Verification status
Source inspection

Problem summary
The README says the project provides 23 JPMS modules, but the root `pom.xml` declares 30 modules. The README module table also omits several published modules and support modules.

Evidence
README claims "23 JPMS modules" at line 10.
The root POM lists 30 modules at lines 92-122.
Examples omitted from the README module table include `base-graph`, `base-json`, `base-tar`, `base-template`, `base-template-processor`, `base-template-test`, and `base-version`.

Relevant references
`README.md:10`
`pom.xml:92`
`pom.xml:122`

Why this matters
The README is the first-stop entry point for contributors and consumers.
An outdated module inventory makes the project look smaller than it is and hides important artifacts.

Reproduction steps
1. Open `README.md`.
2. Open the `<modules>` section of `pom.xml`.
3. Compare the count and the listed artifacts.

Expected result
The README should reflect the actual module count and describe all current modules that matter to contributors and consumers.

Actual result
The README understates the module count and omits multiple modules.

Suggested fix direction
Regenerate or manually refresh the module summary in the README from the root POM and current architecture docs.

Acceptance criteria
The README count matches the root build.
The module table includes the currently maintained modules or clearly states that it is a curated subset.

Suggested labels
`documentation`
`readme`
