---
layout: article-toc
---
# Welcome 
Use the files in this book to single-source content for reuse in multiple hdocbooks.

**To add the reusable content found in this library:**
1. Add an INCLUDE directive as in the example that follows. 

    This example single-sources "What is Hornbill?" content for use in both the Platform Fundamentals Guide and the Platform User Guide:

    `[[INCLUDE https://raw.githubusercontent.com/Hornbill-Docs/hdoc-library/main/hdoc-library/guides/what-is-hornbill.md]]`
1. For each hdocbook in which you want to use the content, open the relevant .md file and locate the place you want the content to appear.
1. Place the INCLUDE directive, changing the end bits of the path to match the location of the reusable content's file.

For more information, see [the Hornbill Docs Contributor Guide](/hdoc-guide/hdocbook/reusable-content).

**To create new reusable content in this library:**
1. Create an .md file for each body of text or snippet.
1. For good housekeeping, update the hdocbook.json so that your new content appears in the navigation.
1. Aim to place the new .md file into an existing folder, if applicable. If there is no applicable folder, create a new one.
