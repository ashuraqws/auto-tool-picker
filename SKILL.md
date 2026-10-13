---
name: auto-tool-picker
description: Use this skill whenever a task could be done better with an installed tool the user did not name — an MCP server, another skill, a plugin, or a hook that is already connected in this Claude Code session. Trigger on any multi-step or specialized request (reading or searching files, querying a database, browsing a website, checking GitHub issues or PRs, looking up library docs, working with Google Drive, Gmail or Calendar, previewing a web app, designing UI, making a document) even when the user never mentions a tool. Only choose among tools that are already installed and enabled; never install, enable or configure anything new.
---

# Auto Tool Picker

Pick the best already-installed tool for the job, then use it. The user should not have to name the tool.

## Step 1: Inventory what is available

Look at the tools and skills already visible in this session: the deferred tool list, the available skills list, and any MCP servers that are connected. Do not search for or propose tools that are not installed. If a server is listed as failed or needing authentication, treat it as unavailable and say so only if the user's request depends on it.

## Step 2: Match the task to a tool

Pick the most specific tool that fully covers the task:
- A dedicated tool for the app beats a general one. A Google Drive connector beats a browser for Drive files.
- A specialized skill beats doing the work from scratch when the skill's description matches the request.
- A built-in tool (Read, Grep, Bash) beats an MCP server when it does the same job.
- If two options fit equally, prefer the one that needs no login or network.

If nothing fits, do the task directly with the built-in tools. Do not force a tool.

## Step 3: Act with an approval rule

- **Read-only work runs without asking:** search, read, list, fetch, look up docs, inspect status.
- **Changes ask first:** sending messages or emails, creating or editing files outside the project, updating external records, publishing, deleting, paying, or changing settings. Show what will change and wait for a clear yes.
- **Irreversible actions always ask**, even if the user seemed to approve something similar earlier.

Never use a tool to get around a permission prompt or to read credentials, tokens, or license keys.

## Step 4: Say what you used

In one short line before the result, name the tool and why, for example: "Drive MCP ile dosyayı arıyorum." Keep it to one line. Do not list every tool you considered.

## Step 5: Fall back safely

If the chosen tool fails, try one other installed option that fits. If that also fails, stop and report the error exactly as returned, with the tool name. Do not retry the same failing call in a loop.
