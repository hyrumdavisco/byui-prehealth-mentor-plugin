# BYU–Idaho Pre-Health Mentor Plugin

A skills-only ChatGPT and Codex plugin that helps BYU–Idaho students build realistic pre-health timelines. The first workflow plans backward from the intended professional-school entry year and, for pre-med students, the MCAT window.

## Repository structure

- `.agents/plugins/marketplace.json` — Git-backed marketplace catalog
- `plugins/byui-prehealth-mentor/` — plugin package
- `plugins/byui-prehealth-mentor/skills/byui-prehealth-mentor/` — mentoring skill and knowledge files

No MCP server is required. The plugin provides guidance and planning but does not need to access an external account or database.

## Import into ChatGPT with automatic sync (recommended)

Requires access to workspace **Admin > Plugins**.

1. Open **Admin > Plugins > Add > Import marketplace**.
2. Set **Source** to `https://github.com/hyrumdavisco/byui-prehealth-mentor-plugin`.
3. Leave **Path** blank: the catalog is at the repository root in `.agents/plugins/marketplace.json`.
4. Leave **Branch, tag, or commit** blank to follow the default branch, `main`.
5. Select **Import marketplace** and authorize GitHub access if prompted.
6. Review the import results and make **BYU–Idaho Pre-Health Mentor** available or installed for your intended role.

New imported marketplaces have automatic daily sync enabled. For an immediate update, open **Admin > Plugins > Marketplaces**, select this marketplace, and choose **Sync now**. No MCP server, Notion connection, or CLI is required for this route. Importing here does not publish the plugin to the universal public directory.

Official guidance: https://learn.chatgpt.com/docs/enterprise/plugin-management

## Optional local Codex installation

```bash
codex plugin marketplace add hyrumdavisco/byui-prehealth-mentor-plugin --ref main
codex plugin add byui-prehealth-mentor@byui-prehealth
```

Restart the ChatGPT desktop app, open the Plugins Directory, choose **BYU–Idaho Pre-Health**, and enable **BYU–Idaho Pre-Health Mentor**. Start a new conversation when testing changed skill instructions.

## Update workflow

1. Edit or add files under `plugins/byui-prehealth-mentor/skills/byui-prehealth-mentor/`.
2. Add each new knowledge file to `references/mentor-knowledge-index.md`.
3. Commit and push the changes to `main`.
4. For the ChatGPT Admin import, wait for daily sync or select **Sync now**, then review the sync report. An invalid update leaves the last working version active.
5. Start a new chat to test the changed mentoring instructions.

Only for the optional local CLI installation, refresh with:

```bash
codex plugin marketplace upgrade byui-prehealth
codex plugin add byui-prehealth-mentor@byui-prehealth
```

Workspace-imported marketplaces sync automatically; the CLI installation is a separate update mechanism. Public-directory publication is also separate from workspace import.

## Add mentor knowledge

Keep mentor notes focused by topic. Label advice as **Official**, **Firsthand**, or **Reported**, and date-check changing requirements. Do not present one student's experience with a course or instructor as universal fact.
