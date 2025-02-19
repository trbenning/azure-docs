---
title: 'Tutorial: Azure Active Directory single sign-on (SSO) integration with Adobe Creative Cloud | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and Adobe Creative Cloud.
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

# Tutorial: Azure Active Directory single sign-on (SSO) integration with Adobe Creative Cloud

In this tutorial, you'll learn how to integrate Adobe Creative Cloud with Azure Active Directory (Azure AD). When you integrate Adobe Creative Cloud with Azure AD, you can:

* Control in Azure AD who has access to Adobe Creative Cloud.
* Enable your users to be automatically signed-in to Adobe Creative Cloud with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

## Prerequisites

To get started, you need the following items:

* An Azure AD subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Adobe Creative Cloud single sign-on (SSO) enabled subscription.

## Scenario description

In this tutorial, you configure and test Azure AD SSO in a test environment.

* Adobe Creative Cloud supports **SP** initiated SSO

## Add Adobe Creative Cloud from the gallery

To configure the integration of Adobe Creative Cloud into Azure AD, you need to add Adobe Creative Cloud from the gallery to your list of managed SaaS apps.

1. Sign in to the Azure portal using either a work or school account, or a personal Microsoft account.
1. On the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add new application, select **New application**.
1. In the **Add from the gallery** section, type **Adobe Creative Cloud** in the search box.
1. Select **Adobe Creative Cloud** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, as well as walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

## Configure and test Azure AD SSO for Adobe Creative Cloud

Configure and test Azure AD SSO with Adobe Creative Cloud using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in Adobe Creative Cloud.

To configure and test Azure AD SSO with Adobe Creative Cloud, perform the following steps:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    1. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure Adobe Creative Cloud SSO](#configure-adobe-creative-cloud-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Adobe Creative Cloud test user](#create-adobe-creative-cloud-test-user)** - to have a counterpart of B.Simon in Adobe Creative Cloud that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the Azure portal, on the **Adobe Creative Cloud** application integration page, find the **Manage** section and select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, enter the values for the following fields:

	a. In the **Sign on URL** text box, type the URL:
    `https://adobe.com`

    b. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://www.okta.com/saml2/service-provider/<token>`

	> [!NOTE]
	> The Identifier value is not real. Follow the guidance on the step 4 of **Configure Adobe Cloud SSO** section. In that you can open the **Federation Metadata XML file** and get the Entity ID value from it and put that as a Identifier value in Azure AD configuration. You can also refer to the patterns shown in the **Basic SAML Configuration** section in the Azure portal.

1. Adobe Creative Cloud application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/edit-attribute.png)

1. In addition to above, Adobe Creative Cloud application expects few more attributes to be passed back in SAML response, which are shown below. These attributes are also pre populated but you can review them as per your requirement.

	| Name | Source Attribute|
	|----- | --------- |
	| FirstName | user.givenname |
	| LastName | user.surname |
	| Email | user.mail |

	> [!NOTE]
	> Users need to have a valid Microsoft 365 ExO license for email claim value to be populated in the SAML response.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section, find **Federation Data XML**, and then select **Download** to download the XML metadata file and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

1. On the **Set up Adobe Creative Cloud** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

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

In this section, you enable B.Simon to use Azure single sign-on by granting access to Adobe Creative Cloud.

1. In the Azure portal, select **Enterprise Applications** > **All applications**.
1. In the applications list, select **Adobe Creative Cloud**.
1. In the app's overview page, find the **Manage** section, and select **Users and groups**.
1. Select **Add user**. Then, in the **Add Assignment** dialog box, select **Users and groups**.
1. In the **Users and groups** dialog box, select **B.Simon** from the list of users. Then choose **Select** at the bottom of the screen.
1. If you are expecting a role to be assigned to the users, you can select it from the **Select a role** dropdown. If no role has been set up for this app, you see "Default Access" role selected.
1. In the **Add Assignment** dialog box, select **Assign**.

## Configure Adobe Creative Cloud SSO

1. In a different web browser window, sign in to [Adobe Admin Console](https://adminconsole.adobe.com) as a system administrator.

1. Go to **Settings** on the top navigation bar, and then choose **Identity**. The list of directories opens. Select the Federated directory you want.

1. On the **Directory Details** page, select **Configure**.

1. Copy the Entity ID and the ACS URL (Assertion Consumer Service URL or Reply URL). Enter the URLs at the appropriate fields in the Azure portal.

	![Configure single sign-on on the app side](./media/adobe-creative-cloud-tutorial/tutorial_adobe-creative-cloud_003.png)

	a. Use the Entity ID value Adobe provided you for **Identifier** in the **Configure App Settings** dialog box.

	b. Use the ACS URL (Assertion Consumer Service URL) value Adobe provided you for **Reply URL** in the **Configure App Settings** dialog box.

1. Near the bottom of the page, upload the **Federation Data XML** file that you downloaded from the Azure portal. 

	![Federation Data XML file](https://helpx.adobe.com/content/dam/help/en/enterprise/kb/configure-microsoft-azure-with-adobe-sso/jcr_content/main-pars/procedure/proc_par/step_228106403/step_par/image_copy/saml_signinig_certificate.png "IdP Metadata XML")

1. Select **Save**.

### Create Adobe Creative Cloud test user

In order to enable Azure AD users to sign into Adobe Creative Cloud, they must be provisioned into Adobe Creative Cloud. In the case of Adobe Creative Cloud, provisioning is a manual task.

### To provision a user accounts, perform the following steps:

1. Sign in to [Adobe Admin Console](https://adminconsole.adobe.com) site as an administrator.

2. Add the user within Adobe’s console as Federated ID and assign them to a Product Profile. For detailed information on adding users, see [Add users in Adobe Admin Console](https://helpx.adobe.com/enterprise/using/users.html#Addusers).

3. At this point, type your email address/UPN into the Adobe sign in form, press tab, and you should be federated back to Azure AD:
   * Web access: www\.adobe.com > sign-in
   * Within the desktop app utility > sign-in
   * Within the application > help > sign-in

## Test SSO

In this section, you test your Azure AD single sign-on configuration with following options. 

* Click on **Test this application** in Azure portal. This will redirect to Adobe Creative Cloud Sign-on URL where you can initiate the login flow. 

* Go to Adobe Creative Cloud Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you click the Adobe Creative Cloud tile in the My Apps, this will redirect to Adobe Creative Cloud Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Next steps

Once you configure Adobe Creative Cloud you can enforce session control, which protect exfiltration and infiltration of your organization’s sensitive data in real-time. Session control extend from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).
