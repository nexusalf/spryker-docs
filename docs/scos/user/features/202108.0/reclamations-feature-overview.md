---
title: Reclamations feature overview
description: With the reclamations in place, you can do three things- create a new connected order, return money paid for the order, or close the reclamation.
last_updated: Aug 3, 2021
template: concept-topic-template
originalLink: https://documentation.spryker.com/2021080/docs/reclamations-feature-overview
originalArticleId: 9b753eb0-0fd3-476f-8f2d-da9687683900
redirect_from:
  - /2021080/docs/reclamations-feature-overview
  - /2021080/docs/en/reclamations-feature-overview
  - /docs/reclamations-feature-overview
  - /docs/en/reclamations-feature-overview
---

Handling order claims are the reality of doing business for most e-commerce sites. A customer might have bought an item and then discovered, that it does not fit, or they might have stumbled upon another item and want to order it instead of the order already placed, or an item is faulty, or additional parts are needed etc.

The _Reclamations_ feature is a simple, yet effective way for administrators to handle all the customer order claims. The shop administrators can create, view, and edit the reclamations in the dedicated section of the Administration Interface. The editing implies making a refund (depending on your state machine configuration) or closing the reclamation. Thus, the Reclamation feature makes the process of claims-handling easier, faster and more efficient for the store administrators, as well as helps to improve customer service.

Once a Back Office user has received a claim regarding an order from the customer, they can go to [Overview of Orders](/docs/scos/user/back-office-user-guides/{{page.version}}/sales/orders/creating-reclamations.html) in the Back Office and click **Claim** to register the claim for the order (for all items or separate items of the order).

After the reclamation has been created, it appears on the [Reclamations](/docs/scos/user/back-office-user-guides/{{page.version}}/sales/reclamations/viewing-reclamations.html) page under the **Sales** menu in the Back Office. Each reclamation is linked to a specific order by order ID, however, one and the same order can have more than one reclamation.

With the reclamations in place, you can find the problematic issues with orders that a shop owner has (e.g., the product is faulty or broken) and manage them.

{% info_block errorBox %}

Due to the specificity of the state machine for every project, out of the box, the “refunded” state is not reflected in OMS in any way - it is just a mark for the shop administrators signifying that the order has been refunded.

{% endinfo_block %}

The reclamations can have two states - open and closed. The closed state of a reclamation means that there is nothing to do on it anymore, therefore it can not be reopened.

## Current constraints

A Back Office user can create a Reclamation in the Back Office as an action item for a company. The rest needs to be configured according to the project needs.

In the Back Office in the order list, a Back Office user doesn't have the functionality to filter the orders by a business unit. All the orders within the shop system (for example, from multiple company accounts) are displayed here.

## Related Business User articles

|BACK OFFICE USER GUIDES|
|---|
| [Create a new order-related reclamation](/docs/scos/user/back-office-user-guides/{{page.version}}/sales/orders/creating-reclamations.html)  |
| [View reclamations](/docs/scos/user/back-office-user-guides/{{page.version}}/sales/reclamations/viewing-reclamations.html)  |
| [Changing the state of order items in reclamations](/docs/scos/user/back-office-user-guides/{{page.version}}/sales/reclamations/changing-the-state-of-order-items-in-reclamations.html)  |

{% info_block warningBox "Developer guides" %}

Are you a developer? See [Reclamations feature walkthrough](/docs/scos/dev/feature-walkthroughs/{{page.version}}/reclamations-feature-walkthrough.html) for developers.

{% endinfo_block %}
