# Patch Pipeline

`veil-boringssl` is the canonical native TLS fork used as the patch-pipeline
template for the Veil stack.

## Baseline

- Upstream submodule: `upstream/boringssl`
- Upstream commit: `673e61fc215b178a90c0e67858bbf162c8158993`
- Baseline record: `upstream-baseline.txt`

## Patch Set

- `patches/boringssl-baseline.patch`

The patch file is the audit trail for fingerprint-related native behavior.
Native behavior changes must be reproducible from the upstream baseline plus
patch files; do not leave behavior changes only in checked-in source edits.

## Verification Contract

1. Verify the upstream submodule matches `upstream-baseline.txt`.
2. Apply `patches/*.patch` to a clean upstream checkout.
3. Confirm exported symbols used by wrappers are present before publishing a
   Veil tag.
4. Keep capability review separate from Rust wrapper review. This repo answers
   "does the native symbol/behavior exist?"

