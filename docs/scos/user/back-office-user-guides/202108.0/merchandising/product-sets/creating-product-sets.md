---
title: Creating product sets
description: Learn how to create product sets in the Back Office.
last_updated: Jul 30, 2021
template: back-office-user-guide-template
originalLink: https://documentation.spryker.com/2021080/docs/creating-product-sets
originalArticleId: 20263bb8-2952-4db2-bde6-1a17a8e76017
redirect_from:
  - /2021080/docs/creating-product-sets
  - /2021080/docs/en/creating-product-sets
  - /docs/creating-product-sets
  - /docs/en/creating-product-sets
related:
  - title: Product Sets feature overview
    link: docs/scos/user/features/page.version/product-sets-feature-overview.html
---

This article describes how to create a product set.

You create a product set to improve the customer's shopping experience. You collect similar products into a logical chunk that can be bought with a single click. Let's say you have a pen. The logically connected items to this product can be a pencil, notebook, and sticky notes. You can collect these products under a set named _Basic office supplies_. Instead of searching for each item, your customer will add this set to cart.

## Prerequisites

To start working with product sets, go to **Merchandising** > **Product Sets**.

Review the reference information before you start, or look up the necessary information as you go through the process.

## Creating product sets

To create a product set:
1. In the top-right corner of the *Product Sets* page, click **Create Product Set**.
    On the *Create Product Set* tab, you see four tabs: *General*, *Products*, *SEO*, and *Images*.
2. In the *General* tab that is used to provide the general information about your product set, like name, URL, and description, do the following:
    1. Fill in the desired name of your new Product Set.
    2. Give your product set a URL slug. Do not leave spaces in this tag; instead, any multi-word URL fill in the spaces with a dash or underscore.
    3. **Optional:** Enter a description for your product set. This can be anything you want that identifies the _what_ or _why_ of your product set.
    If you have multiple languages, you will be required to fill in the same information in all languages.
    4. At the bottom of the **General** tab, you will find Product Set Key, Weight and a checkbox for Active. Enter the values for the attributes.
3. Select **Next** to proceed to the *Products* tab, or just click on it.
    The *Product* tab is where you select products to include in your product set.
4. To add products, simply select the checkbox next to your desired products in the **Selected** column. You can use the available search tool on the top right of the *Select Products to assign* tab on this page. You can select as many products as needed—there is no limit.

{% info_block errorBox "Important" %}

Any product set requires a minimum of two products.

{% endinfo_block %}

5. Select **Next** to proceed to the *SEO* tab, or just click on it.
    This tab is used to add a piece of friendly SEO information for your product set to improve the search.
6. On the *SEO* tab, enter the SEO information for your product set.
7. Select the **Next** to proceed to the *Images* tab, or just click on it.
8. In the *Images* tab, click **Add image set**.
9. Enter the name of your image set and add the URLs to the images.
You can select as many images as you would like in your image set by selecting **Add Image**.
Following the same procedure, choose images particular to your different online stores.

{% info_block infoBox "Info" %}

If you do not specify different images for your different stores, the system will use the photos displayed in the **Default** drop-down

{% endinfo_block %}

10. Once you are satisfied with the setup, click **Submit**.

{% info_block infoBox "Activating a product set" %}

If you did not select the **Active** checkbox in the *General* tab, your product set is inactive.
To activate it, click **Activate** on the *View Product Set* page, or select **Activate** in the _Actions_ column of the *Product Sets* page.

{% endinfo_block %}

### Reference information: Creating product sets
<a name="reference-information-creating-product-sets"></a>

This section describes the attributes you see and enter when creating and managing product sets.

#### Product Sets page

On the *Product Sets* page, you see a table with all product sets available in the system.
For each product set, the following information is presented:
* The autogenerated product set ID.
* Product set name.
* The number of products included in the product set.
* The weight of the product set.
* Product set status (either *Active* or *Inactive*).
* The actions that you can do on a product set (View, Edit, Deactivate, Delete).

#### Create/Edit Product Set page

The following tables describe the attributes that you enter and select while creating or managing a product set.

**General tab**

| ATTRIBUTE |DESCRIPTION  |
| --- | --- |
| Name | Name of your product set. |
| Url | URL slug for your product set. Do not leave spaces in this tag. Instead, for any multi-word URL, fill in the spaces with a dash or underscore.|
| Description | Eye-catching description for your product set. |
| Product Set Key |This attribute is needed when you want to define a specific page to display the product set. It is important to note when creating your product set key to not include spaces. Please use an underscore or dash instead of spaces; otherwise, the content widget cannot read it. |
| WeighT | Number that represents the importance of your product set. Product sets with a higher weight will be shown first or on top.|
| Active | Checkbox that defines if the product set is displayed anywhere in the online store. |

**SEO tab**

| ATTRIBUTE | DESCRIPTION|
| --- | --- |
| Title | SEO-friendly title for the product set. |
| Keywords| Any SEO relevant keywords for an added boost in search ranking. |
| Description | SEO-friendly product set description.  |

**Images tab**

| ATTRIBUTE | DESCRIPTION|
| --- | --- |
| Image Set Name | Name of your image set. No spaces are allowed, please use an underscore or dash. |
| Small Image URL<br>Large Image URL | Allows adding images via a URL. Make sure the image you are adding is available from a public URL. This means any images in a private Dropbox or Google folder will not work. |
| Sort OrderIf you add several images to an active image set, specify the order in which they are to be shown in the front end and back end using Sort Order fields. The order of images is defined by order of entered numbers where the image set with the sort order "0" is the first to be shown. |  

#### Product set example

This is how the product set looks like in the online store:
![Product set example](https://spryker.s3.eu-central-1.amazonaws.com/docs/User+Guides/Back+Office+User+Guides/Products/Products/Product+Sets/Product+Sets%3A+Reference+Information/product-set-example.png)

The Back Office set up for this product set looks the following way:
![Product set in the Back Office](https://spryker.s3.eu-central-1.amazonaws.com/docs/User+Guides/Back+Office+User+Guides/Products/Products/Product+Sets/Product+Sets%3A+Reference+Information/product-set-in-back-office.png)

![Product set in the Back Office](https://spryker.s3.eu-central-1.amazonaws.com/docs/User+Guides/Back+Office+User+Guides/Products/Products/Product+Sets/Product+Sets%3A+Reference+Information/product-set-example-in-back-office.png)

**What's next?**
<br>To know how the product sets are managed, see [Managing product sets](/docs/scos/user/back-office-user-guides/{{page.version}}/merchandising/product-sets/managing-product-sets.html).
