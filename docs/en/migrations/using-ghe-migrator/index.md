---
source_path: "/en/migrations/using-ghe-migrator"
title: "Using ghe-migrator"
intro: "You can use ghe-migrator to migrate user, organization, and repository data to your GitHub Enterprise Server instance from GitHub.com or another GitHub Enterprise Server instance."
product: "Migrations"
document_type: "category"
breadcrumbs:
  - title: "Migrations"
    href: "/en/migrations"
  - title: "ghe-migrator"
    href: "/en/migrations/using-ghe-migrator"
---

# Using ghe-migrator

You can use ghe-migrator to migrate user, organization, and repository data to your GitHub Enterprise Server instance from GitHub.com or another GitHub Enterprise Server instance.

## Links

* [About ghe-migrator](/en/migrations/using-ghe-migrator/about-ghe-migrator)

  You can use ghe-migrator to transfer data from a source location (either a GitHub.com organization or a GitHub Enterprise Server instance) to a target GitHub Enterprise Server instance.

* [Exporting migration data from GitHub Enterprise Server](/en/migrations/using-ghe-migrator/exporting-migration-data-from-github-enterprise-server)

  To change platforms or move from a trial instance to a production instance, you can export migration data from a GitHub Enterprise Server instance by preparing the instance, locking the repositories, and generating a migration archive.

* [Exporting migration data from GitHub.com](/en/migrations/using-ghe-migrator/exporting-migration-data-from-githubcom)

  You can export migration data from an organization on GitHub.com by using the API to select repositories to migrate, then generating a migration archive that you can import into a GitHub Enterprise Server instance.

* [Migrating data to GitHub Enterprise Server](/en/migrations/using-ghe-migrator/migrating-data-to-github-enterprise-server)

  After generating a migration archive, you can import the data to your target GitHub Enterprise Server instance. You'll be able to review changes for potential conflicts before permanently applying the changes to your target instance.
