Type: Bug Report
Title: [Bug]: README build instructions use `npx everywhere build` instead of the published package name
Labels: bug

What happened?
Most README examples invoke the CLI as `npx @workday/everywhere ...`, but the build section switches to `npx everywhere build`.

Steps to Reproduce
1. Open `README.md`.
2. Compare the `init`, `view`, and `bind` examples with the `build` example.
3. Notice that the build section uses a different command form.

What did you expect to happen?
I expected the README to use one consistent invocation strategy for the published package.

What actually happened?
The build section uses `npx everywhere build`, which does not match the documented package name used everywhere else in the README.

Screenshots or Logs
Relevant lines:
- `README.md:10-11`
- `README.md:26`
- `README.md:62`
- `README.md:72`
- `README.md:89`
- `README.md:108`

Environment Information
- Node.js version: not executed during this review
- SDK version: `0.2.2`
- Operating System: macOS
- Package manager: npm

Additional Context
The root package declares the binary under `package.json:35-37`, but the package users install is still `@workday/everywhere`, so the README should be especially clear about which `npx` form is supported.

How often does this happen?
Every time

