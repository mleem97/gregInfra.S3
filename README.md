# gregInfra.S3

Coolify raw-compose stack: 6 MinIO S3 instances.

| Service | Purpose | Buckets |
|---|---|---|
| `s3-releases` | Published mod artifacts | `mods` |
| `s3-quarantine` | Untrusted uploads (security pipeline) | `quarantine` |
| `s3-images` | Avatars, banners, covers (public prefixes) | `avatars`, `banners`, `images` + per-user buckets |
| `s3-scans` | Security worker artifacts | `scans` |
| `s3-backups` | DB dumps, volume backups | `backups` |
| `s3-docs` | Hosted docs / CDN assets (public) | `docs` |

Credentials via Coolify app env (`S3_<PURPOSE>_USER/PASSWORD`).
Internal reachability: `http://s3-<purpose>:9000` on the `coolify` network.
