# `esp-csi-rs-core` — deprecated, folded back into `esp-csi-rs`

[![crates.io](https://img.shields.io/crates/v/esp-csi-rs-core.svg)](https://crates.io/crates/esp-csi-rs-core)

> **Use [`esp-csi-rs`](https://github.com/csi-rs/esp-csi-rs) instead.**
>
> ```toml
> esp-csi-rs = "0.10"
> ```

This crate was a short-lived extraction of the CSI engine out of `esp-csi-rs`, published as
`0.1.0` and `0.1.1` in July 2026. The split turned `esp-csi-rs` — the crate the project is known
by — into a fifteen-line re-export whose documentation landed here instead, which was the wrong
trade. **`esp-csi-rs 0.10.0` absorbed the engine back**, so there is once again a single crate
that holds the code, the documentation and the examples:
<https://docs.rs/esp-csi-rs>.

Nothing was lost in the move. Every path is the same modulo the crate name, so migrating is a
rename:

```diff
-esp-csi-rs-core = "0.1"
+esp-csi-rs = "0.10"
```

```diff
-use esp_csi_rs_core::{NodeRole, CollectorMode, RadioProfile};
+use esp_csi_rs::{NodeRole, CollectorMode, RadioProfile};
```

`esp-csi-rs 0.10.0` also carries engine work that never reached a `esp-csi-rs-core` release —
CSI source attribution filters, per-run statistics that survive to the end of the run, and a
log path that no longer caps a collector's sample rate.

## This crate is not yanked, and will not be

`esp-csi-rs 0.9.0` is published and depends on `esp-csi-rs-core ^0.1`. Yanking would
retroactively break a release people are using, so `0.1.0` and `0.1.1` stay available
indefinitely. They will simply receive no further versions.

## Repository status

Archived, and kept public so existing links and cross-references keep resolving. The engine's
full history lives on in `esp-csi-rs`, which absorbed it with history joined rather than copied —
`git log` there reaches back through these commits.
