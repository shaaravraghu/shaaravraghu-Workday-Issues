Type: Bug Report
Title: [Bug]: README data-hook example references `Text` without importing or defining it
Labels: bug

What happened?
The README example for rendering GraphQL hook errors uses `<Text color="cinnamon500">`, but the snippet only imports `useWorkEvents` and does not define or import `Text`.

Steps to Reproduce
1. Open the "Use data hooks in your pages" section of `README.md`.
2. Copy the code example into a plugin page.
3. Try to compile it as shown.

What did you expect to happen?
I expected the example snippet to compile or at least be self-contained enough that the missing dependency is obvious.

What actually happened?
The snippet references `Text` with no import or explanation, so the example is incomplete.

Screenshots or Logs
Relevant lines:
- `README.md:163-175`

Environment Information
- Node.js version: not executed during this review
- SDK version: `0.2.2`
- Operating System: macOS
- Package manager: npm

Additional Context
This is especially confusing because the surrounding examples otherwise use only React primitives and SDK exports.

How often does this happen?
Every time

