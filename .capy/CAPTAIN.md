# Captain context — mod-autobalance-chronicle (fork)

> Voir aussi [.capy/CAPY-PLATFORM.md](./CAPY-PLATFORM.md).

## What this is

Fork of `azerothcore/mod-autobalance` — the dynamic creature/instance scaling module for AzerothCore. It tunes encounter difficulty for the small-group (10-50 friends) Chronicle WoW 3.3.5a narrative private server.

This fork is an **AzerothCore module**: it is compiled into the server build (built and hosted elsewhere). Do not attempt to build the server here.

Keep divergence minimal. Chronicle-specific patches belong here only when they cannot be expressed through module config (`conf/`) or accepted upstream.

## Branches

| Branch | Role |
|---|---|
| `master` | Default branch; upstream-sync baseline mirroring `azerothcore/mod-autobalance@master` |
| Feature branches | Chronicle-specific patches or process/docs changes isolated from upstream sync commits |

## Consumed by

- The Chronicle AzerothCore server stack (built/hosted elsewhere) loads this module via the standard module mechanism.
- Ultimate consumer: [`NomenAK/Chronicle`](https://github.com/NomenAK/Chronicle).

## Upstream sync strategy

- Prefer expressing Chronicle tuning through `conf/` (`.conf.dist`) overrides rather than code patches.
- Pull opportunistically: needed features, build/runtime fixes, or explicit human request; no blind fixed-schedule sync.
- Keep upstream merge/cherry-pick commits separate from Chronicle-specific patch commits.

## Hard rules

1. **DO NOT modify upstream code** unless the patch is Chronicle-specific and impossible via config. Prefer `conf/` overrides, then upstream contribution or cherry-pick.
2. **Commit messages** follow upstream convention; inspect `setup_git_commit_template.sh` for the project template.
3. **Secrets** follow [.capy/CAPY-PLATFORM.md §1](./CAPY-PLATFORM.md#1-vm-capy--secrets). Never persist tokens or private config in this repo.
4. **Do not build the server here** — server build/runtime validation happens downstream in the Chronicle stack.

## CI

- Server build/integration validation happens downstream through the Chronicle stack, not in this fork.
- For docs/process-only changes, verify changed files and skip expensive C++ builds unless requested.

## Linear / coordination

Team/project context: `Omega · Chronicle`. Keep generic Linear CLI/auth guidance in [.capy/CAPY-PLATFORM.md §4](./CAPY-PLATFORM.md#4-linear-coordination).

## Local agent note

`.capy/` is fork-local agent context. It intentionally avoids root-level agent instruction files so upstream syncs have fewer predictable conflicts. No `.capy/BUILD.md` for this fork.

## Related repos

- Ultimate consumer: https://github.com/NomenAK/Chronicle
- AzerothCore core fork: https://github.com/NomenAK/azerothcore-wotlk-chronicle
- Sibling module forks: https://github.com/NomenAK/mod-playerbots-chronicle, https://github.com/NomenAK/mod-ale-chronicle
- Upstream: https://github.com/azerothcore/mod-autobalance
