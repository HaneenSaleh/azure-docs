---
title: Export APIs from Azure API Management to Microsoft Power Platform | Microsoft Docs
description: Learn how to export an API from API Management as a custom connector to Power Apps and Power Automate in the Microsoft Power Platform.
services: api-management
author: dlepow

ms.service: api-management
ms.topic: how-to
ms.date: 08/12/2022
ms.author: danlep

---
# Export APIs from Azure API Management to the Power Platform 

Citizen developers using the Microsoft [Power Platform](https://powerplatform.microsoft.com) often need to reach the business capabilities that are developed by professional developers and deployed in Azure. [Azure API Management](https://aka.ms/apimrocks) enables professional developers to publish their backend service as APIs, and easily export these APIs to the Power Platform ([Power Apps](/powerapps/powerapps-overview) and [Power Automate](/power-automate/getting-started)) as custom connectors for discovery and consumption by citizen developers. 

This article walks through the steps in the Azure portal to create a custom Power Platform connector to an API in API Management. With this capability, citizen developers can use the Power Platform to create and distribute apps that are based on internal and external APIs managed by API Management.

## Prerequisites

+ Complete the following quickstart: [Create an Azure API Management instance](get-started-create-service-instance.md)
+ Make sure there is an API in your API Management instance that you'd like to export to the Power Platform
+ Make sure you have a Power Apps or Power Automate [environment](/powerapps/powerapps-overview#power-apps-for-admins) 

## Create a custom connector to an API

1. Navigate to your API Management service in the Azure portal.
1. In the menu, under **APIs**, select **Power Platform**.
1. Select **Create a connector**.
1. In the **Create a connector** window, do the following:
    1. Select an API to publish to the Power Platform.
    1. Select a Power Platform environment to publish the API to. 
    1. Enter a display name, which will be used as the name of the custom connector.  
    1. Optionally, if the API doesn't already require a subscription, select **Create subscription key connection parameter**.
    1. Optionally, if the API is [protected by an OAuth 2.0 server](api-management-howto-protect-backend-with-aad.md), provide details including **Client ID**, **Client secret**, **Authorization URL**, **Token URL**, and **Refresh URL**.  
1. Select **Create**. 

    :::image type="content" source="media/export-api-power-platform/create-custom-connector.png" alt-text="Create custom connector to API in API Management":::

Once the connector is created, navigate to your [Power Apps](https://make.powerapps.com) or [Power Automate](https://make.powerautomate.com) environment. You will see the API listed under **Data > Custom Connectors**.

:::image type="content" source="media/export-api-power-platform/custom-connector-power-app.png" alt-text="Custom connector in Power Platform":::

## Manage a custom connector

You can manage your custom connector in your Power Apps or Power Platform environment. For details about settings, see [Create a custom connector from scratch](/connectors/custom-connectors/define-blank).

1. Select your connector from the list of custom connectors.
1. Select the pencil (Edit) icon to edit and test the custom connector. 

> [!NOTE]
> To call the API from the Power Apps test console, you need to add the `https://make.powerautomate.com` URL as an origin to the [CORS policy](cors-policy.md) in your API Management instance.
> 
> Depending on how the custom connector gets used when running Power Apps, you might need to configure additional origins in the CORS policy. You can use developer tools in your browser, tracing in API Management, or Application Insights to investigate CORS issues when running Power Apps.

## Update a custom connector

From API Management, you can update a connector to target a different API or Power Apps environment, or to update authorization settings.

1. Navigate to your API Management service in the Azure portal.
1. In the menu, under **APIs**, select **Power Platform**.
1. Select **Update a connector**.
1. Select the API you want to update the connector for, update settings as needed, and select **Update**.


## Next steps

* [Learn more about the Power Platform](https://powerplatform.microsoft.com/)
* [Learn more about creating and using custom connectors](/connectors/custom-connectors/)
* [Learn common tasks in API Management by following the tutorials](./import-and-publish.md)
