# Contributing to EnginEx

Thank you for helping improve EnginEx. Focused changes, reproducible tests, security review, and accurate documentation keep the renderer dependable.

## Development workflow

1. Fork the repository or create a branch from the maintained default branch.
2. Use a currently patched Node.js 22, 24, or 26 runtime.
3. Make a focused change and add or update regression tests.
4. Run the relevant test, then npm test, npm run check, and npm run evals as applicable.
5. Run git diff --check and inspect the full diff.
6. Update documentation, grammar, schemas, release metadata, and changelog when behavior changes.
7. Open a pull request describing the problem, implementation, validation results, security impact, and limitations.

~~~bash
npm test
npm run check
npm run evals
npm run bench:compare
npm audit
git diff --check
~~~

## Code and security expectations

- Preserve the restricted template-expression grammar; never add arbitrary JavaScript execution from template source.
- Add negative-path regression tests for parser, compiler, escaping, path, cache, data, schema, provider, MCP, and transport changes.
- Do not silently accept unsupported syntax or JSON Schema keywords.
- Keep optional AI, provider, MCP, accelerator, and transport integrations optional.
- Treat model output, precompiled manifests, and external templates as untrusted until validated.
- Keep host helpers capability-limited and never log secrets or private inputs.
- Do not add model-controlled direct file-write or publication tools.
- Performance claims must include reproducible commands and output-equivalence evidence.

## Pull request checklist

- [ ] The change has a clear, focused purpose.
- [ ] Relevant tests pass and skipped checks are identified.
- [ ] Security boundaries and negative paths have been reviewed.
- [ ] Documentation, grammar, schemas, and changelog are updated as appropriate.
- [ ] No credentials, private data, or unrelated generated artifacts are staged.
- [ ] License and third-party notices are preserved.

## Attribution and licensing

By submitting a contribution, you confirm that you have the right to submit it and agree that it may be distributed under GPL-2.0-or-later unless the maintainers agree to another arrangement in writing. Preserve third-party notices. This policy does not create a copyright assignment or a separate contributor license agreement.

See LICENSE, COPYRIGHT, NOTICE.md, and TRADEMARKS.md.