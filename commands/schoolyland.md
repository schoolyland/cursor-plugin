---
name: schoolyland
description: Work on your Schoolyland WordPress site — content, store, courses, email marketing, forms and SEO — through the Schoolyland MCP tools.
---

# /schoolyland

Natural-language entry point for your Schoolyland site. Interpret the request, keep the user's constraints, and treat the current Schoolyland MCP tool descriptions as the source of truth.

## Usage

```
/schoolyland <natural language request>
```

## Examples

```
/schoolyland Give me a weekly summary of my site
/schoolyland Show this month's sales and the top-selling products
/schoolyland Check the SEO of my home page and tell me what to improve
/schoolyland Draft an email campaign announcing my new course
/schoolyland Add an FAQ section to the pricing page
/schoolyland Which students enrolled in my course this week?
```

## Routing

- **Not sure what the site has** → call `get_site_overview` first (plugins, content, store and CRM at a glance).
- **A weekly review or site health check** → `start_weekly_review`.
- **The tool you need is not in the visible list** → many more tools exist behind `run_advanced_tool`. Call `describe_advanced_tool` to see the catalog and a tool's parameters, then run it through `run_advanced_tool`.
- **Missing an ID (page, product, course, contact)** → look it up with the matching list or search tool. Don't guess IDs.

## Before changing anything

- Confirm write actions with the user first — publishing, sending an email campaign, deleting content, or changing settings.
- Page and post edits are backed up automatically before they are written. If a change needs to be undone, use `restore_content_backup` (or `restore_elementor_backup` for Elementor pages).
- The connection is tied to the site the user approved when signing in. To work on a different site, the user connects that site from their Schoolyland account.
