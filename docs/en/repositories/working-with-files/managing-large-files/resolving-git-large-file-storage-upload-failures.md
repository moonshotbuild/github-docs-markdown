---
source_path: "/en/repositories/working-with-files/managing-large-files/resolving-git-large-file-storage-upload-failures"
title: "Resolving Git Large File Storage upload failures"
intro: "If your Git LFS files didn't upload properly, you can take several steps to troubleshoot the upload error."
product: "Repositories"
document_type: "article"
breadcrumbs:
  - title: "Repositories"
    href: "/en/repositories"
  - title: "Work with files"
    href: "/en/repositories/working-with-files"
  - title: "Managing large files"
    href: "/en/repositories/working-with-files/managing-large-files"
  - title: "Resolve upload failures"
    href: "/en/repositories/working-with-files/managing-large-files/resolving-git-large-file-storage-upload-failures"
---

# Resolving Git Large File Storage upload failures

If your Git LFS files didn't upload properly, you can take several steps to troubleshoot the upload error.

The Git LFS integrity check ensures that all referenced Git LFS files in a push have been uploaded properly. If the check detects referenced files that have not been uploaded, you will receive an error message and your push will be blocked.

To resolve the error message, you must reinstall your local Git LFS client to ensure that the referenced Git LFS files can be properly uploaded in the future.

1. Open Terminal.
1. Reinstall Git LFS.

   ```shell
   git lfs install
   ```

1. Push all referenced Git LFS files.

   ```shell
   git lfs push --all origin
   ```
