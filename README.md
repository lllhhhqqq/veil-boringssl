# veil-boringssl

This repository is a patch orchestration layer, not a full source mirror.

## Layout

- `upstream/boringssl`: git submodule pinned to upstream BoringSSL.
- `upstream-baseline.txt`: expected upstream commit hash.
- `patches/mimic-baseline.patch`: fork delta patch applied on top of upstream baseline.
- `.github/workflows/mimic-ci.yml`: validates pin + patch and builds patched upstream.

## Update Flow

1. Move `upstream/boringssl` to a new approved upstream commit.
2. Refresh `patches/mimic-baseline.patch`.
3. Update `upstream-baseline.txt`.
4. Ensure CI is green before tagging.
