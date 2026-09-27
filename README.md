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

Open the Plugins Directory, choose **BYU–Idaho Pre-Health**, and enable **BYU–Idaho Pre-Health Mentor**. Start a new conversation when testing changed skill instructions.

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

## Google Drive resources — version 0.1.5

Source collection: [Pre-Health planning](https://drive.google.com/drive/folders/1CUu_3WfcNFyoZwGii1TvIm0jUOymflx7).

The earlier test includes dated Markdown reference summaries of three selected documents:

- GRADUATION PLAN.docx
- Course Cheat Sheet
- Application Timeline Tips from AAMC official website

Find them through [the resource index](plugins/byui-prehealth-mentor/skills/byui-prehealth-mentor/references/mentor-knowledge-index.md). Each summary records its source link, source-read date, and limits. Collected advice is separate from Hyrum's firsthand recommendations. This resource import does not finalize the mentoring workflow being designed.

The earlier summaries are included in the plugin; their originals remain at the linked locations.

Version 0.1.2 also copies all six documents from **Applications, Writing & Interviews**: AMCAS, AACOMAS, personal statement guidance, interview preparation, common interview questions, and the Spring 2026 strategy presentation. [Open the collection](plugins/byui-prehealth-mentor/skills/byui-prehealth-mentor/references/applications-writing-interviews/README.md) for readable text, five Google Docs exports in Word format, and the original PDF. Source links, modification times, and file checksums are recorded in its manifest. That update imported only the Applications, Writing & Interviews subfolder.

Version 0.1.3 copies both original Word documents from **Courses & Planning**, with full readable source text and links to the existing course and graduation summaries. [Open Courses & Planning](plugins/byui-prehealth-mentor/skills/byui-prehealth-mentor/references/courses-planning/README.md). Its BYU-I subfolder was empty and is represented by a note. The two existing summaries and their new original copies cover the same two documents.

Version 0.1.4 copies all five **Experiences** resources: community service, patient exposure, research, shadowing, and archived local volunteering leads. [Open Experiences](plugins/byui-prehealth-mentor/skills/byui-prehealth-mentor/references/experiences/README.md) for four Word exports, the original PDF, readable source text, and verification notes. Linked external resources were not recursively imported.

Version 0.1.5 copies the single **Testing & MCAT** Google Doc as a Word export and readable reference, preserving its embedded external compilation link. [Open Testing & MCAT](plugins/byui-prehealth-mentor/skills/byui-prehealth-mentor/references/testing-mcat/README.md). The external website and its downloads were not imported; availability and content remain unverified.

These are collected sources, not newly verified admissions rules or automatically Hyrum’s personal advice. Students do not need a Drive connection to read the bundled copies. Source materials retain their original authorship and applicable rights; the repository MIT license does not establish rights to third-party source documents.

### Refreshing resources

Drive is the editing source; GitHub contains the published reference summaries. **Drive-to-GitHub automatic synchronization is not configured.** ChatGPT's GitHub marketplace sync is a separate step and only picks up changes already committed to this repository.

For now, update a selected Drive document, re-read it, revise its matching reference summary and source-read date, validate the package, and commit the update. Adding a new Drive file alone does not add it to the plugin. Future automation can use the stable file links in the index while retaining source labels and review of changing claims.

### First test

After importing or refreshing the GitHub plugin, start a new conversation and ask:

> Use BYU–Idaho Pre-Health Mentor. What does the collected course cheat sheet suggest for balancing a semester? Distinguish source advice from verified requirements.

Check that it reads the bundled course reference, attributes the workload pattern to the collected document, and avoids treating its difficulty labels or credits as verified current catalog facts.
