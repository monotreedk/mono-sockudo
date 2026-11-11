# Monotree's build of Sockudo

Sockudo built for Ubuntu 22.04 (glibc 2.35), with only the features we use. Upstream's release binaries are
built on 24.04 and need glibc 2.39.

- **Branch `monotree`** is upstream `master` at a pinned commit, plus this file and
  `.github/workflows/monotree-build.yml`. There are no code changes. `master` is left as forked and not synced.
- **Updating:** `git fetch upstream && git merge <upstream sha>` into `monotree`, then run the workflow.
- **Building:** run "Monotree build" (Actions, workflow_dispatch) on `monotree`. It builds on ubuntu-22.04 with
  `--no-default-features --features local,mysql,redis`.
- **Releases:** tagged `mono-<12-char sha>`. Each has the raw `sockudo` binary and `sockudo.sha256`, to be
  downloaded by tag and verified against the checksum.
- **Upstream workflows** are disabled in this fork's Actions settings, so they don't run here.
