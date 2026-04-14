# GitHub MCP Guidance

## Purpose
Support optional repository publishing, review, or collaboration workflows for the runtime-generated application without polluting the blueprint repository.

## Use Cases
- publishing the generated application to a separate repository
- opening review PRs for generated code
- capturing issue feedback on the produced app

## Rules
- do not publish generated application code back into this blueprint repository
- keep blueprint and generated app lifecycle separate
- preserve traceability by linking commits or pull requests to the run identifier and build manifest

## Recommended Metadata
- run ID
- blueprint version
- generated app repository URL
- validation status
- reviewer sign-off summary
