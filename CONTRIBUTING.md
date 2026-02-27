# Contributing to PulsePhone

PulsePhone is an open hardware project built in KiCad. Hardware files don't merge cleanly like code, so we use a hybrid workflow to keep things stable while staying open to contributions.

---

## Workflow

**1. Fork the repository** and create a branch named after your change — e.g. `fix-power-rail`, `improve-usb-c-routing`, `camera-module-redesign`.

**2. Make your changes.** You can modify KiCad schematics, PCB layouts, or documentation, or propose design ideas. Keep changes focused and minimal where possible — KiCad files conflict easily.

**3. Open a Pull Request targeting `dev`.** PRs directly into `main` will not be accepted.

**4. Review.** Pedro will review your changes, merge clean PRs into `dev`, manually apply conflicting KiCad edits, or ask for clarification if needed. Once stable, `dev` gets merged into `main`.

For major changes or design proposals, open a GitHub Issue before you start working — it saves everyone time.

---

## Governance

PulsePhone is led by **Pedro Porcelli — Founder, Designer, and Maintainer**.

Pedro has final say on KiCad design decisions, hardware revisions, module architecture, electrical and mechanical standards, and all merges into `main`. This isn't bureaucracy — it's just the reality of hardware: one bad merge can corrupt the design files for everyone.

The process is simple: propose via Issues or PRs, get feedback, land in `dev`, ship to `main` after validation.

---

PulsePhone is built to inspire learning and creativity. Contributions of any size are welcome and appreciated.
