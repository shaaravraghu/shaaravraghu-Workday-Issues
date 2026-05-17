Type: Bug Report
Title: [Bug]: README documents `/api/data/graphql` but the implementation uses `/api/v1/data/graphql`
Labels: bug

What happened?
The README says `GraphQLResolver` sends requests to `/api/data/graphql`, but both the resolver and the dev-server proxy are wired to `/api/v1/data/graphql`.

Steps to Reproduce
1. Open the GraphQL section of `README.md`.
2. Compare the documented endpoint path with the implementation in `src/data/GraphQLResolver.ts` and `cli/src/commands/everywhere/view.ts`.

What did you expect to happen?
I expected the README to describe the same endpoint path the SDK actually uses.

What actually happened?
The docs reference a different path than the runtime implementation.

Screenshots or Logs
Relevant lines:
- `README.md:151-153`
- `src/data/GraphQLResolver.ts:39-40`
- `cli/src/commands/everywhere/view.ts:57-69`

Environment Information
- Node.js version: not executed during this review
- SDK version: `0.2.2`
- Operating System: macOS
- Package manager: npm

Additional Context
This is easy to miss because the same README section also mentions `--no-mock-data`, so users may debug the wrong proxy path if they are trying to trace requests manually.

How often does this happen?
Every time

