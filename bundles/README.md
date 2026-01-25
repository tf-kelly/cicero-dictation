# Replication bundles

Each `cicero_modes_bundle_*.tar.gz` is a self-contained offline replication package.

## Verify (macOS)
`shasum -a 256 -c <bundle>.tar.gz.sha256`

## Unpack
`tar -xzf <bundle>.tar.gz`

## Rebuild offline
`cd cicero_modes_bundle_*`
`bash scripts/00_RUN_ALL_OFFLINE.sh`
