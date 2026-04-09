# Veil BoringSSL Maintenance Contract

Last updated: 2026-04-09

## Scope

This repository is the maintained fork for `veil-boringssl`.

## Frozen Invariants

1. Upstream source of truth is `upstream/boringssl` submodule.
2. Upstream pin must match `upstream-baseline.txt` (`673e61fc215b178a90c0e67858bbf162c8158993`).
3. Fork delta must be carried as explicit patch files under `patches/`.
4. `mimic-v*` tags are releasable rollback anchors.
5. No silent semantic drift against documented baseline.

## Operating Model

1. Move `upstream/boringssl` submodule to approved upstream commit.
2. Update `patches/*.patch` for fork-specific changes.
3. Apply/verify patch set on top of upstream in CI.
4. Run CI (`mimic-ci`) before tagging.
5. Update `mimic-v*` tag only after CI is green.

## Forbidden Shortcuts

1. Do not move upstream submodule pointer without updating baseline file.
2. Do not change source behavior without corresponding patch update.
3. Do not bundle unrelated patch sets in one commit.
4. Do not tag release from unverified commit.

## Rollback Anchor

Rollback target is the previous `mimic-v*` tag.
