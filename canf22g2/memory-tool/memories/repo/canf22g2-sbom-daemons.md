- Scope: this file captures scanner visibility, cataloger behavior, and SBOM-generation traps; daemon library modeling rules belong in `canf22g2-daemon-library-metadata.md`.
- Syft v1.42.4 does not catalog pkg-config `.pc` files as packages in directory scans.
- To surface custom daemon metadata in Syft output, provide a CycloneDX file and enable the sbom cataloger, for example via `.syft.yaml` with `select-catalogers: [+sbom-cataloger]`.
- Put daemon CycloneDX metadata inside the scan scope, for example under `tmp/lib/pkgconfig/getac-daemons.cdx.json`.
- Trivy can read that CycloneDX directly via `trivy sbom <file>`; CycloneDX output preserves daemon components.
- In `5_build_getac_daemon.sh`, do not call metadata registration helpers via command substitution when they mutate associative arrays; bash runs `$(...)` in a subshell and loses CycloneDX component registration side effects.
- Existing `getac_appSrc/getac_daemon_release/lib/pkgconfig` artifacts may be root-owned from prior runs; metadata regeneration can fail with permission denied unless the directory is recreated by the build flow or validated in a writable temp copy.

