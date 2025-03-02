---
title: Order Cancellation overview
description: Allow your customer to cancel orders or cancel orders on their behalf.
last_updated: Jun 16, 2021
template: concept-topic-template
originalLink: https://documentation.spryker.com/2021080/docs/order-cancellation-overview
originalArticleId: 454fec27-cd49-4939-ba51-4a6b9c80468b
redirect_from:
  - /2021080/docs/order-cancellation-overview
  - /2021080/docs/en/order-cancellation-overview
  - /docs/order-cancellation-overview
  - /docs/en/order-cancellation-overview
---

Order cancellation makes the shopping experience of B2B and B2C shoppers more flexible by allowing them to cancel their orders within a defined time period. Also, it optimizes the workflow of sales and customer service by allowing them to cancel orders on customers’ behalf in the Back Office.

For example, a customer changes their mind about an item in an order they have placed. Instead of contacting customer service, they can cancel the order and place a new one with the desired items.

A customer can cancel orders on the *Order History* and *Order Details* pages.

<details open>
    <summary markdown='span'>Order cancellation representation - Order History Page</summary>


![order-history-page](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Order+Management/Order+Cancellation/Order+Cancellation+Feature+Overview/order-history-page.png)


</details>

<details open>
    <summary markdown='span'>Order cancellation representation - Order Details Page</summary>

![order-details-page](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Order+Management/Order+Cancellation/Order+Cancellation+Feature+Overview/order-details-page.png)


</details>


See [Order cancellation on the Storefront](#storefront) to learn how B2B and B2C shoppers can cancel orders on the Storefront.

See [Changing Order Statuses](/docs/scos/user/back-office-user-guides/{{page.version}}/sales/orders/changing-the-state-of-order-items.html) to learn how a Back Office user can cancel orders.

## Time frames and statuses

A customer can cancel an order only within a defined time period. By default, the time period is 30 minutes. After the time period has passed, the buttons to cancel the order are not available. A Back Office user can skip the cancellation time period.  

Also, they can cancel an order only if all the included items are in the states that are defined as cancellable. By default, the *payment pending* and *confirmed* states are cancellable. If at least one of the items in an order is in a different state, the buttons to cancel the order are not available.

In the [state machine](/docs/scos/dev/back-end-development/data-manipulation/datapayload-conversion/state-machine/order-process-modelling-via-state-machines.html), a developer can configure different order states to be cancellable and change the cancellation time period.

{% info_block warningBox "State machine" %}

Ensure that, in your state machine, the *refunded* state always goes before the *cancelled* state. Otherwise, you can't refund the money for a canceled order. You can check the order of the states in the Back Office > **Administration** > **OMS**.

{% endinfo_block %}

See [Changing the state of order items](/docs/scos/user/back-office-user-guides/{{page.version}}/sales/orders/changing-the-state-of-order-items.html) to learn how a Back Office user can skip timeout or cancel an order by changing order statuses.

<a name="storefront"></a>

## Order cancellation on the Storefront
This is how the Order Cancellation feature works on the Spryker Demo Shop Storefront:

![image](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Order+Management/Order+Cancellation/Order+Cancellation+Feature+Overview/shop-guide-cancelling-orders.gif)

## Related Business User articles

|BACK OFFICE USER GUIDES|
|---|
| [Changing the state of order items](/docs/scos/user/back-office-user-guides/{{page.version}}/sales/orders/changing-the-state-of-order-items.html)   |

{% info_block warningBox "Developer guides" %}

Are you a developer? See [Order Management feature walkthrough](/docs/scos/dev/feature-walkthroughs/{{page.version}}/order-management-feature-walkthrough/order-management-feature-wakthrough.html) for developers.

{% endinfo_block %}
