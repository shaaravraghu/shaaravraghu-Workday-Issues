Title
README incorrectly says `base-transport-json` uses Jackson Core

Issue type
Documentation bug

Severity
Low

Priority
P3

Affected modules
Repository docs
`base-transport-json`

Affected files
`README.md`
`base-transport-json/src/main/java/build/base/transport/json/JsonTransport.java`

Verification status
Source inspection

Problem summary
The README describes `base-transport-json` as "JSON transport via Jackson Core", but the implementation imports and uses the in-repo `build.base.json` model and parser instead.

Evidence
README says "JSON transport via Jackson Core" at line 25.
`JsonTransport` imports `build.base.json.Json`, `JsonObject`, `JsonString`, and `JsonValue` at lines 24-29.

Relevant references
`README.md:25`
`base-transport-json/src/main/java/build/base/transport/json/JsonTransport.java:24`

Why this matters
This gives consumers the wrong mental model about dependencies, compatibility, and extension points.
It also obscures the role of the `base-json` module.

Reproduction steps
1. Read the `base-transport-json` entry in the README.
2. Inspect `JsonTransport` imports and constructor code.

Expected result
The README should describe `base-transport-json` as being built on the repository's own JSON value model unless Jackson is actually introduced.

Actual result
The README references a backend that is not present in the implementation.

Suggested fix direction
Update the README to describe `base-transport-json` as JSON transport built on `base-json` and the marshalling stack.

Acceptance criteria
The README module description matches the actual implementation and dependency shape.

Suggested labels
`documentation`
`readme`
`transport`
