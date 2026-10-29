# mako-rust — lane outcome: no_gain (no port)

Training-loop lane `rs-port-mako` (2026-10-29) measured the tier-1
pure-Python fix first and recomputed the rewrite ceiling against it:

- tier-1 (kwargs-plan memo + list-backed buffer): **1.015x** on the frozen
  40000-render server-side workload, upstream suite 562 passed + 53
  skipped on both arms;
- realizable-port ceiling over tier-1: **1.17x at zero FFI toll**
  (machinery-deletion probe), below the 2x kill bar; the FFI toll on
  ~220 per-pair buffer writes inverts the rest (expected ≤1.0x).

Disposition: **no_gain with numbers** — no Rust port; this repo intentionally
contains no port code. Evidence: rustsmith ADR-064 + lane record
`/home/john/firstmate/data/rs-port-mako/` (WORKLOAD.md, bench arms,
upstream patch note `upstream-patch-note.md`, tier-1 diff
`tier1-runtime.patch`).

Upstream: [sqlalchemy/mako](https://github.com/sqlalchemy/mako) (MIT).
See NOTICE.
