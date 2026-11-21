# OffCode Security Audit Playbook for AI Coding Agents (modular edition)

A phased, evidence-based security and privacy audit for your own code, with copy-paste prompts for Cursor, Claude Code, or any coding agent. This edition splits the original single-file playbook (about 80 KB) into one module per session, so the agent reads only a few kilobytes per conversation instead of the whole playbook.

The single-file playbook, [OffCode Security Audit for ai agents.md](OffCode%20Security%20Audit%20for%20ai%20agents.md), is still included. It is identical to `docs/security-audit/SECURITY_AUDIT_FULL.md`: the same audit text with a quick start at the top and the classic copy-paste prompts (the single-file route), which refer to `docs/security-audit/SECURITY_AUDIT_FULL.md`. The modular route below is recommended for agents.

## Structure

This folder mirrors a project root: copy its contents straight into your repository.

```
<repository root>/
├── OffCode Security Audit for ai agents.md   single-file playbook (identical to SECURITY_AUDIT_FULL.md)
├── README_MODULAR.md          this file
├── AGENTS.md                  agent instructions (Cursor and Claude Code read it from the root)
├── CLAUDE.md                  one line, @AGENTS.md, for Claude Code
├── .cursor/rules/
│   └── security-audit.mdc     optional Cursor project rule pointing to AGENTS.md
└── docs/
    └── security-audit/
        ├── SECURITY_AUDIT.md          master: how to use, session plan, core rules, status vocabulary, links
        ├── SECURITY_AUDIT_FULL.md     single-file playbook (only the single-file route reads it)
        ├── sessions/                  one module per session = header + original stage text, verbatim
        │   ├── session-01-kickoff.md … session-12-final-report.md
        │   └── remediation.md         stage 13: fixing one finding, severity classes, finding fields
        ├── prompts/                   one short prompt per session + remediation, reverify, continue
        ├── reference/                 operating rules (section 3), honesty and evidence (18),
        │                              appendix A checklist, start now (19), single-file intro, attribution
        └── templates/                 AUDIT_PROGRESS.md and FINDINGS.md starters
```

Audit outputs are written to **`docs/security/`** (created during session 01).

Each session module starts with a short header (purpose, original sections, files to read, outputs, condensed core rules) followed by the **full original text** of its stages. Cross-references between stages (for example 6b → 10c, 6c → 11) are relative links to the right module.

## Install into a project

1. Copy **everything in this folder** (including the hidden `.cursor` folder) into the repository root. The playbook lands in `docs/security-audit/`, and `AGENTS.md` and `CLAUDE.md` are already at the root.
2. If the project already has an `AGENTS.md` or `CLAUDE.md`, do not overwrite it: append this `AGENTS.md` content as a section, and add the line `@AGENTS.md` to the existing `CLAUDE.md`.
3. `.cursor/rules/security-audit.mdc` is optional; Cursor also reads `AGENTS.md` from the root on its own. Delete the rule if you do not want it.
4. Optional: if you do not want the single-file playbook and this README in the repository root, delete the root copy of the playbook (the same text stays in `docs/security-audit/SECURITY_AUDIT_FULL.md`) and move this README to `docs/security-audit/` or delete it. Agents do not need either.

All prompts and `AGENTS.md` use the paths `docs/security-audit/` and `docs/security/`. If you choose other paths, search and replace them in `AGENTS.md`, `.cursor/rules/`, and `docs/security-audit/`.

## Run the audit

1. Open a new conversation and paste `docs/security-audit/prompts/session-01.md` (kickoff and scoping).
2. Open a new conversation for each next session: `prompts/session-02.md` … `prompts/session-12.md` (session 12 is the final report). Commit and review after each session.
3. After the audit, run `prompts/remediation.md` once per finding (most severe first), then `prompts/reverify.md` in a separate session, then run session 12 again if needed.
4. If the context runs out mid-session, use `prompts/continue.md`.

Stages the project does not have are marked NOT APPLICABLE with a reason; what cannot be checked is NOT VERIFIED.

**Single-file route (alternative):** the classic prompts in `docs/security-audit/SECURITY_AUDIT_FULL.md` (Prompt 0, stage audit template, remediation, re-verification, final report, continue) tell the agent to read that file. They write the same outputs to `docs/security/` with the same `phase-NN-<name>.md` names, but use much more context per session.

## Editing the playbook

`docs/security-audit/SECURITY_AUDIT_FULL.md` (and its identical root copy) is the single-file version of the modules. If you edit a session module, update the full file and the root copy too, or just edit the modules (on the modular route agents only read the modules). The `<!-- BEGIN ORIGINAL … -->` / `<!-- END ORIGINAL … -->` comments in the modules mark where the original playbook text starts and ends. They are harmless and can stay.

---

This playbook is free to use. Bookmark it if you want it at hand for the next audit, and share it with anyone who is reviewing the security of their own code with an AI agent.

OffCode

https://www.dev-offcode.com
