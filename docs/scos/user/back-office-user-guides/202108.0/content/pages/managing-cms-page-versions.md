---
title: Managing CMS page versions
description: The guide provides instructions on how to view CMS page versions, roll back to a specific version or view SEO information in the Back Office.
last_updated: Jun 18, 2021
template: back-office-user-guide-template
originalLink: https://documentation.spryker.com/2021080/docs/managing-cms-page-versions
originalArticleId: 0110b8f0-26d9-41b8-99f7-1fc55efba8be
redirect_from:
  - /2021080/docs/managing-cms-page-versions
  - /2021080/docs/en/managing-cms-page-versions
  - /docs/managing-cms-page-versions
  - /docs/en/managing-cms-page-versions
related:
  - title: CMS Page
    link: docs/scos/user/features/page.version/cms-feature-overview/cms-pages-overview.html
---


This article describes how you can manage versions of CMS pages: view general information, SEO details, compare CMS versions, and roll back to the selected version or discard changes to a page.

## Prerequisites

To start working with CMS page versions, go to **Content** > **Pages**.

## Viewing the history of CMS pages

To view version history of a CMS page:
1. On the *Overview of CMS pages* page in the _Actions_ column, select **View** > **Version History** next to the page whose version history you want to view.
2. On the *Version History: [Page Name]* page, the following information is available:
    * Information on the current version and when it was published.
    * Name of the page and the template it is using.
    * SEO information: title, keywords, and description.
    * Placeholders that display a page title and contain content.
    * Option to roll back all the changes to the specific CMS version.
    * Option to compare the current version with the selected one.

On the *Version History: [Page Name]* page, you can return to the list of CMS pages by clicking **Back to CMS** at the top of the page.

### Rolling back to a CMS page version

To roll back to the specific version:
1. On the *Version History: [Page Name]* page from the drop-down list, select the version you want to return to.
![Rolling back to the selected version](https://spryker.s3.eu-central-1.amazonaws.com/docs/User+Guides/Back+Office+User+Guides/Content+Management+System/Pages/CMS+Pages+Versioning/page-versioning.png)

2. Click **Rollback to Selected Version** in the top right corner of the page. This copies all data from the older version and publish the previous version in the online store.


### Comparing CMS Versions
To compare CMS versions to see what changes you have made to the current version:
1. On the *Version History: [Page Name]* page from the drop-down list, select the version you want to compare with the current one.
2. Click **Compare**. The information of the selected version is displayed next to the information about the current version.
