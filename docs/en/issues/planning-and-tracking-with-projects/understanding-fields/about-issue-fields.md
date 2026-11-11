---
source_path: "/en/issues/planning-and-tracking-with-projects/understanding-fields/about-issue-fields"
title: "About issue fields in projects"
intro: "Learn how to use issue fields in your projects to track structured metadata like priority, effort, and dates."
product: "GitHub Issues"
document_type: "article"
breadcrumbs:
  - title: "GitHub Issues"
    href: "/en/issues"
  - title: "Projects"
    href: "/en/issues/planning-and-tracking-with-projects"
  - title: "Understanding fields"
    href: "/en/issues/planning-and-tracking-with-projects/understanding-fields"
  - title: "About issue fields"
    href: "/en/issues/planning-and-tracking-with-projects/understanding-fields/about-issue-fields"
---

# About issue fields in projects

Learn how to use issue fields in your projects to track structured metadata like priority, effort, and dates.

Issue fields are organization-level or user-level fields that provide consistent, typed metadata across repositories owned by that organization or user. Unlike project custom fields, issue fields are defined once at the organization or user level and are available on issues owned by that organization or user and in projects owned by that organization or user. For more information on creating and managing issue fields, see [Managing issue fields](/en/issues/tracking-your-work-with-issues/using-issues/managing-issue-fields).

## Issue fields in public and internal projects

Only fields with **Public** visibility appear in public and internal projects. Restricted fields are hidden. For details on configuring field visibility and how visibility changes affect projects, see [Managing issue fields](/en/issues/tracking-your-work-with-issues/using-issues/managing-issue-fields#setting-field-visibility).

## Adding an issue field to a project

To display issue field values in a project:

1. Open a project and select a view using the table layout.
2. Click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-plus" aria-label="Add field" role="img"><path d="M7.75 2a.75.75 0 0 1 .75.75V7h4.25a.75.75 0 0 1 0 1.5H8.5v4.25a.75.75 0 0 1-1.5 0V8.5H2.75a.75.75 0 0 1 0-1.5H7V2.75A.75.75 0 0 1 7.75 2Z"></path></svg> in the table header.
3. Click **Add field**.
4. Select one or more issue fields from the list of available fields.
5. Click **Add**.

The issue field appears as a column in the table view.

## Removing an issue field from a project

To remove an issue field from a project:

1. Click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-kebab-horizontal" aria-label="open field options" role="img"><path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path></svg> in the top right corner of the project page.
2. Click **Settings**.
3. In the left sidebar, select the issue field you want to remove.
4. Click **Remove field**.

Removing an issue field from a project does not delete the field or its values. The field can be re-added at any time.

## Editing issue field values in a project

You can edit issue field values directly in the project table view without opening the issue. Click on a cell in the issue field column to set or change the value. Changes are synced back to the issue automatically.

## Grouping, filtering, and sorting

You can group, filter, and sort project views by issue field values, just like any other project field. This works in both table and board layouts.

You can also use issue fields to group by column on the board layout.

## Charts and insights

Issue fields are available as data sources in project charts. You can create charts that group or segment by issue field values to visualize trends.

## Limits

Projects support up to 50 fields in total. Issue fields and system fields count toward this limit. If a project is already at the field limit, you need to remove existing fields before issue fields can be added.

> [!NOTE]
> Issue fields only apply to issues owned by the same organization or user. If a project contains pull requests, draft issues, or issues from another organization or user, issue field columns show empty cells for those items.
