# gha-needs-probe

Scratch repo. It proves, on real GitHub Actions, how a skipped job in a `needs` chain reaches a job
downstream of it, for aryze-io/money-os PR #471 (MON-660). `.github/workflows/probe.yml` copies
that PR's job graph and `if:` expressions with `echo` steps only: no secrets, GitHub-hosted runners.

Run it by hand on `dev` with a `plan` (all-reuse, all-build, mixed) and a `fail` (none,
build-scan, reuse-scan, check). `deploy (old condition)` is the condition #471 first had;
`deploy (new condition)` is the fix.
