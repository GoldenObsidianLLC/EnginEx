# Versioning and Releases

EnginEx follows Semantic Versioning 2.0.0 for its public package and API.

## Version sources

- package.json is the canonical package version.
- CHANGELOG.md records user-visible changes and migration requirements.
- RELEASE-MANIFEST.json records release state, evidence classification, runtime validation, and known gaps.
- Git tags use vMAJOR.MINOR.PATCH and identify immutable release commits.
- Grammar, schemas, documentation, and examples must match the implementation.

## Version increments

| Change | Increment |
|---|---|
| Breaking public API, expression grammar, runtime contract, or compatibility change | MAJOR |
| Backward-compatible functionality or supported capability | MINOR |
| Backward-compatible defect or security fix | PATCH |

License changes, security-boundary changes, and supported-runtime changes are material even when JavaScript API compatibility is unchanged. Document them explicitly and ensure the project has the rights required for the applicable license. Do not overwrite or move published release tags.

## Release workflow

1. Classify compatibility and security impact.
2. Update package.json, CHANGELOG.md, migration notes, README, grammar/schema docs, and RELEASE-MANIFEST.json as appropriate.
3. Run the supported Node.js 22, 24, and 26 test matrix, deterministic eval fixtures, package-integrity checks, and relevant fuzz/regression tests.
4. Review resolved dependency and optional peer-dependency licenses; generate an SBOM and run security/dependency scans.
5. Review parser, compiler, escaping, path, helper, provider, MCP, transport, and publication changes.
6. Ensure hosted CI validates the exact release commit.
7. Publish a release tag and notes only after applicable release gates are complete.

## Evidence and current status

Keep raw benchmark runs, runtime fingerprints, output checksums, and methodology with the evidence. Distinguish local tests, hosted CI, exploratory measurements, external review, and production qualification. EnginEx 7.0.0 is identified by its release manifest as a security-hardening candidate with outstanding validation and independent-review gaps. It is not independently security-certified or production-approved.