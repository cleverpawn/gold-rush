# Releasing — Dungeon Match · Muse Edition

## Versioning rules

Dungeon Match — Muse Edition uses Semantic Versioning: MAJOR.MINOR.PATCH.

- **MAJOR** — major releases, or incompatible changes to the completed
  game's public behavior.
- **MINOR** — new gameplay features, systems, or significant functionality.
- **PATCH** — bug fixes, performance improvements, layout corrections, and
  minor polish that does not introduce new gameplay systems.

While the game remains in development, versions stay in the 0.x.y range.

Rules:

- A version number is assigned only to an approved, published release.
  Completing a development milestone does not by itself increment the
  version.
- Development milestone IDs (1A, 1F.3, 1H.1, …) and release version numbers
  are separate systems; a milestone is not a version.
- The Muse Edition and Codex Edition keep separate version histories,
  even though they share the same game design specification.
- The single authoritative version definition lives in the game page
  itself; the visible version label on the character-selection screen is
  rendered from it. Do not maintain conflicting hardcoded version strings.

## Release checklist

1. Complete and verify the development milestone.
2. Confirm the intended release scope.
3. Select the next approved version number.
4. Update the version definition, the visible version label, and
   CHANGELOG.md.
5. Run the regression tests.
6. Build and publish to GitHub Pages.
7. Verify the served deployment after a cold load and a reload.
8. Tag the exact release commit with an annotated tag (e.g. `v0.1.0`)
   and verify the remote tag points to that commit.
9. Create the GitHub Release from the tag, using the changelog entry as
   the release notes; mark it as a prerelease while the game is in
   development.
10. Preserve the rollback information: version, release commit, tag,
    release date, published URL, and the location of the known-good
    rollback copy of the build.

## Rollback references

Known-good build copies are preserved outside the repository at
`~/workspace/dungeon-match-reference/` (one file per milestone/release,
named with its commit). A rollback is performed by republishing the
preserved file for the target version — never by guessing at an earlier
state.
