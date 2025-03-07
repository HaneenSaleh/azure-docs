---
title: Self-service trade-in for Azure savings plans
titleSuffix: Microsoft Cost Management
description: Learn how you can trade in your reservations for an Azure saving plan.
author: bandersmsft
ms.reviewer: onwokolo
ms.service: cost-management-billing
ms.subservice: savings-plan
ms.custom: ignite-2022
ms.topic: how-to
ms.date: 03/07/2023
ms.author: banders
---

# Self-service trade-in for Azure savings plans

If you find that your [Azure Virtual Machines](https://azure.microsoft.com/pricing/details/virtual-machines/windows/), [Dedicated Hosts](https://azure.microsoft.com/pricing/details/virtual-machines/dedicated-host/), or [Azure App Service](https://azure.microsoft.com/pricing/details/app-service/windows/) reservations, don't provide the necessary flexibility you require, you can trade these reservations for a savings plan. When you trade-in a reservation and purchase a savings plan, you can select a savings plan term of either one-year to three-year.

Although you can return the above offerings for a savings plan, you can't exchange a savings plan for them or for another savings plan.

The following reservations aren't eligible to be traded in for savings plans:

- Azure Databricks reserved capacity
- Synapse Analytics Pre-purchase plan
- Azure VMware solution by CloudSimple
- Azure Red Hat Open Shift
- Red Hat plans
- SUSE Linux plans

> [!NOTE]
> Exchanges will be unavailable for all compute reservations - Azure Reserved Virtual Machine Instances, Azure Dedicated Host reservations, and Azure App Services reservations - purchased on or after **January 1, 2024**. Compute reservations purchased **prior to January 1, 2024** will reserve the right to **exchange one more time** after the policy change goes into effect. Azure savings plan for compute is designed to help you save broadly on predictable compute usage. The savings plan provides more flexibility needed to accommodate changes such as virtual machine series and regions. With savings plan providing the flexibility automatically, we’re adjusting our reservations exchange policy. You can continue to exchange VM sizes (with instance size flexibility) but we'll no longer support exchanging instance series or regions for Azure Reserved Virtual Machine Instances, Azure Dedicated Host reservations, and Azure App Services reservations. For a limited time you may trade-in your Azure compute reservations for a savings plan. Or, you may continue to use and purchase reservations for those predictable, stable workloads where you know the specific configuration you’ll need and want additional savings. For more information, see [Self-service exchanges and refunds for Azure Reservations](../reservations/exchange-and-refund-azure-reservations.md).

There are no plans to restrict reservation to saving plan trade-ins.

- You must have owner access on the Reservation Order to trade in an existing reservation. You can [Add or change users who can manage a savings plan](manage-savings-plan.md#who-can-manage-a-savings-plan).
- Microsoft isn't currently charging early termination fees for reservation trade ins. We might charge the fees made in the future. We currently don't have a date for enabling the fee.

## How to trade in an existing reservation

You can trade in your reservation from [Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_Reservations/ReservationsBrowseBlade). When you trade in VM reservations for a savings plan, we cancel your reservation, issue you a pro-rated refund for them, and cancel any future payments (for reservations that were billed monthly).

1. Select the reservations that you want to trade in and select **Exchange**.  
  :::image type="content" source="./media/reservation-trade-in/exchange-refund-return.png" alt-text="Screenshot showing the Exchange window." lightbox="./media/reservation-trade-in/exchange-refund-return.png" :::
1. For each reservation order selected, enter the quantity of reservation instances you want to return. The bottom of the window shows the amount that will be refunded. It also shows the value of future payments that will be canceled, if applicable.
1. Select **Compute Savings Plan** as the product that you want to purchase.
1. Enter the necessary information to complete the purchase. For more information, see [Buy a savings plan](buy-savings-plan.md#buy-a-savings-plan-in-the-azure-portal).

## Determine savings plan commitment needed to replace your reservation

During a reservation trade-in, the default hourly commitment for the savings plan is calculated using the remaining monetary value of the reservations that are being traded in. The resulting hourly commitment may not be a large enough benefit commitment to cover the virtual machines that were previously covered by the returned reservations. You can calculate the necessary savings plan hourly commitment to cover the reservations as follows:

1. Follow the first six steps in [Estimate costs with the Azure pricing calculator](../manage/ea-pricing.md#estimate-costs-with-the-azure-pricing-calculator).
2. Search for the product that you want to return.
3. Select a savings plan term and operating system, if necessary.
4. Select **Upfront** as the payment option. You're using the annual cost only because it's easier to work with in this calculation example.
5. To determine the hourly commitment for the product, divide the upfront compute charge by:
    - 8,760 for a one-year savings plan
    - 26,280 for a three-year savings plan  
        :::image type="content" source="./media/reservation-trade-in/pricing-calculator-upfront-example.png" alt-text="Example screenshot showing the Azure pricing calculator upfront compute charge value example." lightbox="./media/reservation-trade-in/pricing-calculator-upfront-example.png" :::
1. Multiply the product’s hourly commitment by the number of instances you're trading-in.
1. Repeat steps 2-6 for all reservation products you're trading-in.
1. Enter the total of the above steps as the hourly commitment, then **Add** to your cart.
1. Review and complete the transaction.

The preceding image's price is an example.

The preceding process assumes 100% utilization of the savings plan.

## Determine savings difference from reservations to a savings plan

To determine the cost savings difference when switching from reservations to a savings plan, use the following steps.

1. In the [Azure portal](https://portal.azure.com), navigate to **Reservations** to view your list of reservations.
1. Select the reservation that you want to trade in and select **Exchange**.
1. Under the Essentials section, select the **Reservation order ID**.
1. In the left menu, select **Payments**.
1. Depending on the payment schedule for the reservation, you're presented with either the monthly or full cost of the reservation. You need the monthly cost. If necessary, divide the value by either 12 or 36, depending on the reservation term.
1. Multiply the monthly cost of the reservation by the number of instances you want to return. For example, the total monthly reservation cost.
1. To determine the monthly cost of an equivalent-capable savings plan, follow the first six steps in [Estimate costs with the Azure pricing calculator](../manage/ea-pricing.md#estimate-costs-with-the-azure-pricing-calculator).
1. Search for the compute product associated with the reservation that you want to return.
1. Select savings plan term and operating system, if necessary.
1. Select **Monthly** as the payment option. It's the monthly cost of a savings plan providing equivalent coverage to a resource that was previously covered by the reservation.  
    :::image type="content" source="./media/reservation-trade-in/pricing-calculator-monthly-example.png" alt-text="Example screenshot showing the Azure pricing calculator monthly compute charge value example." lightbox="./media/reservation-trade-in/pricing-calculator-monthly-example.png" :::
1.	Multiply the cost by the number of instances that are currently covered by the reservations to be returned.

The preceding image's price is an example.

The result is the total monthly savings plan cost. The difference between the total monthly savings plan cost minus the total monthly reservation cost is the extra cost incurred by moving resources covered by reservations to a savings plan.

The preceding process assumes 100% utilization of both the reservation(s) and savings plan.

## How transactions are processed

The new savings plan is purchased and then the traded-in reservations are canceled. If the reservations were paid for upfront, we refund a pro-rated amount for the reservations. If the reservations were paid monthly, we refund a pro-rated amount for the current month and cancel any future payments. Microsoft processes refunds using one of the following methods, depending on your account type and payment method.

### Enterprise agreement customers

Money is added to the Azure Prepayment (previously called monetary commitment) for refunds if the original purchase was made using one. If the Azure Prepayment used to purchase the reservation is no longer active, then credit is added to your current enterprise agreement Azure Prepayment term. The credit is valid for 90 days from the date of refund. Unused credit expires at the end of 90 days.

If the original purchase was made as an overage, the original invoice on which the reservation was purchased and all later invoices are reopened and readjusted. Microsoft issues a credit memo for the refunds.

### Microsoft Customer Agreement customers (credit card)

The original invoice is canceled, and a new invoice is created. The money is refunded to the credit card that was used for the original purchase. If you've changed your card, [contact support](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest).

## Cancel, exchange, and refund policies

You can't cancel, exchange or refund a savings plan.

## Need help? Contact us.

If you have Azure savings plan for compute questions, contact your  account team, or [create a support request](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest). Temporarily, Microsoft will only provide Azure savings plan for compute expert support requests in English.

## Next steps

- To learn how to manage a savings plan, see [Manage Azure savings plan](manage-savings-plan.md).
- To learn more about Azure saving plan, see the following articles:
  - [What are Azure savings plans?](savings-plan-compute-overview.md)
  - [How a savings plan discount is applied](discount-application.md)
  - [View Azure savings plan cost and usage details](utilization-cost-reports.md)
  - [Software costs not included in savings plan](software-costs-not-included.md)
