# Contributing to PulsePhone

Thank you for your interest in contributing to PulsePhone!  
This project is primarily a hardware project built in KiCad.  
Because hardware files do not merge as cleanly as code, we use a **hybrid workflow** designed to keep the project stable while still welcoming ideas and improvements.

---

# 🛠 Contribution Workflow

## 1. Fork the Repository
Click **Fork** at the top right of the GitHub page.

## 2. Create a Feature Branch
Name it after your change, for example:

improve-usb-c-routing
fix-power-rail
camera-module-redesign

markdown
Copy code

## 3. Make Your Changes
You may:
- modify KiCad schematic sheets
- modify PCB layout files
- add documentation
- propose design ideas

**Important:** KiCad files often conflict, so please keep changes focused and small when possible.

## 4. Open a Pull Request — to the `dev` branch
All PRs must target the `dev` branch:

base: dev
compare: your-branch

Copy code

Pull requests **will not** be accepted directly into `main`.

## 5. Review Process
The project maintainer (Pedro Porcelli) will:

✔ review your changes  
✔ merge clean PRs directly into `dev`  
✔ for conflicting KiCad edits, manually apply the changes  
✔ ask for clarification if needed  

Once stable, changes from `dev` will be merged into `main`.

---

# 📫 Communication

For major changes or design proposals, open GitHub Issues to discuss ideas before working on them.

---

# 🧭 Governance

## Project Lead
PulsePhone is led by:

**Pedro Porcelli — Founder, Designer, and Maintainer**

Pedro has final approval on:
- KiCad design decisions  
- hardware revisions  
- module architecture  
- electrical and mechanical standards  
- merges into `main`

## How Decisions Are Made
1. Community proposes ideas via Issues or PRs.  
2. Pedro reviews and gives feedback.  
3. If accepted, changes enter the `dev` branch.  
4. After testing and validation, changes are merged into `main`.

## Why This Hybrid Model?
KiCad PCB and schematic files merge poorly.  
This governance model ensures:

- stability of the official hardware files  
- freedom for contributors to experiment  
- a clear review path  
- zero risk of corrupting the main design  

---

# 🙌 Thank You
PulsePhone is an open hardware project built to inspire learning and creativity.  
Your ideas and improvements help push the project forward!
