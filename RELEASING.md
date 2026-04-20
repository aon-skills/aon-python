# Releasing

## Canonical Artifacts

- The Python runtime artifact is the PyPI package `aon-demo-skill-python`.
- This GitHub repository is the public wrapper for skill instructions, governance files, and install documentation.

## When to Cut a GitHub Release

Create or update a GitHub release when one of the following is true:

- the published Python skill version changes
- the install flow changes in a user-visible way
- the packaged `SKILL.md` semantics change for end users

Pure governance-only or template-only changes do not require a release.

## GitHub Actions

- `Validate Wrapper Repo` runs on pushes and pull requests to `main` and checks the required public wrapper files.
- `Publish GitHub Release` is a manual Actions workflow. Run it with a tag that matches the published PyPI version when the wrapper repo needs a release snapshot.

## Sync Source

The source of truth lives in the AON monorepo. Sync this repository from the monorepo with:

```bash
PUBLISH_MSG="docs(aon-python): sync from monorepo" bash sdk/publish_skills.sh aon-skills aon-python
```

## Versioning Guidance

- Use the PyPI package version as the GitHub release tag version.
- Keep `CHANGELOG.md` aligned with the public package surface.
- Treat GitHub Releases as documentation snapshots, not as the primary binary distribution channel.