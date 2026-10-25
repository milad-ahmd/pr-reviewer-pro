<div align="center">

# 🔎 pr-reviewer-pro

**An Agent Skill that reviews your pull requests like a senior engineer: few comments, high signal, with fixes included.**

[![License: MIT](https://img.shields.io/github/license/milad-ahmd/pr-reviewer-pro)](LICENSE)
[![Stars](https://img.shields.io/github/stars/milad-ahmd/pr-reviewer-pro?style=social)](https://github.com/milad-ahmd/pr-reviewer-pro)
![Works with](https://img.shields.io/badge/works%20with-Claude%20Code%20%7C%20Cline%20%7C%20Cursor%20%7C%20Codex-8A2BE2)

[Install](#-install) · [What it checks](#-what-it-checks) · [Usage](#-usage) · [Other skills](#-more-skills)

</div>

## 😩 The problem

AI reviews are often 40 nitpicks about formatting while the SQL injection on line 12 slips through. This skill makes your agent behave like the reviewer you actually want.

## 🎯 What it checks

| Severity | Examples |
|---|---|
| 🔴 Blocker | Bugs, data loss, race conditions, injection, authz bypass, leaked secrets, breaking API changes |
| 🟠 Major | N+1 queries, unbounded memory, missing validation, **missing tests** |
| 🟡 Minor | Naming, duplication, dead code, unclear errors |
| 💡 Nit / Praise | Only what your linter doesn't already catch, plus credit where it's due |

**Rules it follows:** every comment cites `file:line`, explains why it matters, suggests a fix, follows *your* repo's conventions, and stays at roughly 10 comments or fewer.

## 📦 Install

**Claude Code** (personal skills):

```bash
git clone https://github.com/milad-ahmd/pr-reviewer-pro /tmp/pr-reviewer-pro
mkdir -p ~/.claude/skills && cp -r /tmp/pr-reviewer-pro/skills/pr-reviewer-pro ~/.claude/skills/
```

**Per project** (Claude Code / Cline / any tool that reads `SKILL.md`): copy `skills/pr-reviewer-pro` into your project's `.claude/skills/` folder.

**Any other agent**: paste [`SKILL.md`](skills/pr-reviewer-pro/SKILL.md) into your rules or system prompt.

Optional: the [GitHub CLI](https://cli.github.com) (`gh`) is needed for reviewing PRs by number and for posting reviews.

## 💬 Usage

```text
Review my changes before I push
Review PR #123
Review PR #123 and post it to GitHub
```

The helper script [`collect_diff.sh`](skills/pr-reviewer-pro/scripts/collect_diff.sh) gathers the diff, either your branch vs the default branch or a GitHub PR. The agent always shows you the review before posting anything.

## 🧩 More skills

🧰 **[See all 31 skills and the one-line installer → milad-ahmd/agent-skills](https://github.com/milad-ahmd/agent-skills)**

- ✨ [readme-glow-up](https://github.com/milad-ahmd/readme-glow-up): turn any README into a star magnet
- 📚 [awesome-agent-skills](https://github.com/milad-ahmd/awesome-agent-skills): a curated list of Agent Skills

## 🤝 Contributing

PRs that add language-specific checklists (Go, Rust, Python, React...) are very welcome.

## 📄 License

[MIT](LICENSE) © Milad Ahmadi

<div align="center">

**If this caught a bug for you, a ⭐ helps others find it.**

</div>
