# MR Marine Group README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create the concise main GitHub organization README for MR Marine Group.

**Architecture:** Use one standalone Markdown file at the repository root. The page will combine a short company overview based on the official website with a clearly labeled statement about this organization’s software-development role.

**Tech Stack:** GitHub-flavored Markdown.

## Global Constraints

- Keep the page short and suitable as the main GitHub organization landing page.
- Use the company tagline `Your Global Beacon`.
- Link to `https://mr-marinegroup.com/`.
- Do not add badges, repository inventories, technology claims, or unverified internal product details.

---

### Task 1: Create the organization README

**Files:**
- Create: `README.md`
- Test: Markdown structure and whitespace checks via shell commands.

**Interfaces:**
- Consumes: Approved design in `docs/superpowers/specs/2026-08-12-mr-marine-group-readme-design.md`.
- Produces: The public organization landing page at the repository root.

- [ ] **Step 1: Add the approved Markdown content**

Create `README.md` with:

```md
# MR Marine Group

> Your Global Beacon

Mr. Marine is a global maritime service company committed to keeping vessels safe and compliant worldwide. Its services include marine elevators, ballast systems, and marine instruments and controls. [Learn more about Mr. Marine](https://mr-marinegroup.com/).

## Software Development

This organization is home to the software development of MR Marine Group.
```

- [ ] **Step 2: Verify the file contents and Markdown structure**

Run:

```bash
sed -n '1,120p' README.md
rg -n '^# |^> |^## |https://mr-marinegroup\\.com/' README.md
```

Expected: one level-one heading, one tagline blockquote, one `Software Development` level-two heading, and the official website link.

- [ ] **Step 3: Check for whitespace errors**

Run:

```bash
git diff --check
```

Expected: no output and exit status `0`.

- [ ] **Step 4: Commit the completed README**

Run:

```bash
git add README.md
git commit -m "docs: add MR Marine Group organization README"
```

Expected: a new commit containing only the organization README.
