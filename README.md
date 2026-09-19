# BYU–Idaho Pre-Health Mentor Plugin

A skills-only ChatGPT and Codex plugin that helps BYU–Idaho students build realistic pre-health timelines. The first workflow plans backward from the intended professional-school entry year and, for pre-med students, the MCAT window.

## Repository structure

- `.agents/plugins/marketplace.json` — Git-backed marketplace catalog
- `plugins/byui-prehealth-mentor/` — plugin package
- `plugins/byui-prehealth-mentor/skills/byui-prehealth-mentor/` — mentoring skill and knowledge files

No MCP server is required. The plugin provides guidance and planning but does not need to access an external account or database.

## Install from GitHub

```bash
codex plugin marketplace add hyrumdavisco/byui-prehealth-mentor-plugin --ref main
codex plugin add byui-prehealth-mentor@byui-prehealth
```

Restart the ChatGPT desktop app, open the Plugins Directory, choose **BYU–Idaho Pre-Health**, and enable **BYU–Idaho Pre-Health Mentor**. Start a new conversation when testing changed skill instructions.

## Update workflow

1. Edit or add files under `plugins/byui-prehealth-mentor/skills/byui-prehealth-mentor/`.
2. Add each new knowledge file to `references/mentor-knowledge-index.md`.
3. Commit and push the changes to `main`.
4. Pull the latest marketplace snapshot:

```bash
codex plugin marketplace upgrade byui-prehealth
codex plugin add byui-prehealth-mentor@byui-prehealth
```

5. Start a new ChatGPT thread to load the updated skill.

GitHub is the source of truth, but installed plugins do not silently hot-reload every commit. The upgrade/reinstall step makes the updated files active. Public-directory releases require versioning and review.

## Add mentor knowledge

Keep mentor notes focused by topic. Label advice as **Official**, **Firsthand**, or **Reported**, and date-check changing requirements. Do not present one student's experience with a course or instructor as universal fact.
