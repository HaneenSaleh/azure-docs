---
title: 'Tutorial: Azure AD SSO integration with FactSet'
description: Learn how to configure single sign-on between Azure Active Directory and FactSet.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 11/21/2022
ms.author: jeedes
---

# Tutorial: Azure AD SSO integration with FactSet

In this tutorial, you'll learn how to integrate FactSet with Azure Active Directory (Azure AD). When you integrate FactSet with Azure AD, you can:

* Control in Azure AD who has access to FactSet URLs via the Federation.
* Enable your users to be automatically signed-in to FactSet with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

## Prerequisites

To get started, you need the following items:

* An Azure AD subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* FactSet single sign-on (SSO) enabled subscription.

## Scenario description

In this tutorial, you configure and test Azure AD SSO in a test environment.

* FactSet supports **SP** initiated SSO.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add FactSet from the gallery

To configure the integration of FactSet into Azure AD, you need to add FactSet from the gallery to your list of managed SaaS apps.

1. Sign in to the Azure portal using either a work or school account, or a personal Microsoft account.
1. On the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add new application, select **New application**.
1. In the **Add from the gallery** section, type **FactSet** in the search box.
1. Select **FactSet** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, as well as walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

## Configure and test Azure AD SSO for FactSet

Configure and test Azure AD SSO with FactSet using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in FactSet.

To configure and test Azure AD SSO with FactSet, perform the following steps:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    1. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure FactSet SSO](#configure-factset-sso)** - to configure the single sign-on settings on application side.
    1. **[Create FactSet test user](#create-factset-test-user)** - to have a counterpart of B.Simon in FactSet that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the Azure portal, on the **FactSet** application integration page, find the **Manage** section and select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot shows how to edit Basic SAML Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier** text box, type the URL:
    `https://auth.factset.com`

    b. In the **Reply URL** text box, type the URL:
    `https://auth.factset.com/sp/ACS.saml2`

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the metadata file and save it on your computer.

	![Screenshot shows the Certificate download link.](common/metadataxml.png "Certificate")

1. On the **Set up FactSet** section, copy the appropriate URL(s) based on your requirement.

	![Screenshot shows to copy configuration appropriate URL.](common/copy-configuration-urls.png "Metadata")

### Create an Azure AD test user

In this section, you'll create a test user in the Azure portal called B.Simon.

1. From the left pane in the Azure portal, select **Azure Active Directory**, select **Users**, and then select **All users**.
1. Select **New user** at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Name** field, enter `B.Simon`.  
   1. In the **User name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Click **Create**.

### Assign the Azure AD test user

In this section, you'll enable B.Simon to use Azure single sign-on by granting access to FactSet.

1. In the Azure portal, select **Enterprise Applications**, and then select **All applications**.
1. In the applications list, select **FactSet**.
1. In the app's overview page, find the **Manage** section and select **Users and groups**.
1. Select **Add user**, then select **Users and groups** in the **Add Assignment** dialog.
1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
1. If you are expecting a role to be assigned to the users, you can select it from the **Select a role** dropdown. If no role has been set up for this app, you see "Default Access" role selected.
1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure FactSet SSO

To configure single sign-on on FactSet side you will need to visit FactSet's [Control Center](https://controlcenter.factset.com) and configure the **Federation Metadata XML** and appropriate copied URLs from Azure portal under **Control Center's Security > Single Sign-On (SSO)** page. If you require access to this page, please contact [FactSet Support Team](https://www.factset.com/contact-us) and request FactSet product 8514 (Control Center - Source IPs, Security + Authentication).

### Create FactSet test user

Work with your FactSet account support representatives or contact [FactSet Support Team](https://www.factset.com/contact-us) to add the users in the FactSet platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Azure AD single sign-on configuration with following option.

* FactSet only supports SP-initiated SAML. You may test SSO by visiting any authenticated FactSet URL such as [Issue Tracker](https://issuetracker.factset.com) or [FactSet-Web](https://my.factset.com), click on **Single Sign-On (SSO)** on the logon portal and supply your email address in the subsequent page. Please see supplied [documentation](https://download.factset.com/documents/web/FactSet_Single_Sign-On.pdf) for additional information and usage.  

## Next steps

Once you configure FactSet you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).