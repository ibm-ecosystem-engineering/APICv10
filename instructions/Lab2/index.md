**APIC Workshop Lab 2 - The Developer Portal Experience**

In this lab, we will take the API created in Lab 1 and publish it to a
Developer Portal, ready for consumption by app developers. We will begin
by creating a new catalog and configuring the developer portal for our
HotelReview product. We will then define a new plan in the product and
publish to our new developer portal.

In this tutorial, you will explore the following key capabilities:

-   Configure the Developer Portal and publish the APIs.

-   Create a Portal Account.

-   Create App and Subscribe to Plan.

-   Test API in the Developer Portal

 APIC Workshop Series
==================================================================================================================================================================================================================

The APIC Workshop Series is a hands-on workshop with lab exercises that
walk you through designing, publishing, and securing APIs. This workshop
is for API developers, architects, and line of business people who want
to create a successful API strategy. There are 9 labs and each is 30
minutes long. Make sure you choose enough time in your reservation to
get through all the labs! 

[NOTE: ]**[This demo environment contains a
full API Connect installation in Cloud Pak for Integration. The login
information to the APIC cluster will be sent in a separate email when
you reserve the instance. Use Google Chrome, Firefox or Microsoft Edge
to access the cluster using the credentials supplied. Make sure you
login using Common Services registry.]**

[Lab 0 : Get Started](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab0)

[Lab 1 : Create and Secure an API to Proxy an Existing REST Web
service](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab1)

[Lab 2 : The Developer Portal
Experience](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab2)

[Lab 3 : Add OAuth Security to your
API](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab3)

[Lab 4 : Use Lifecycle Controls to Version Your
API](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab4)

[Lab 5: Advanced API
Assembly](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab5)

[Lab 6: Working with API
Products](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab6)

[Lab 7: The Consumer
Experience](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab7)

[Lab 8: Create and test GraphQL Proxy
API](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab8)

[Lab 9: Creating GraphQL API with API Connect Essentials](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab9)

Prerequisites: Lab 1

 Generate the developer portal
====================================================================================

In this section, we will configure developer portal 
for the sandbox catalog, sign up and login to Developer Portal.

**Create API Connect Developer Portal site**

1. Login to the API Manager.

2. Click **Manage** in the vertical left navigation menu or click "Manage catalogs".

    ![](images/lab_2_01.png)

3. Select the **Sandbox** Catalog and click on the **Catalog Settings** tab.

    ![](images/lab_2_02.png)

4. Click on **Portal** in the left navigation menu, you should see as shown in below image.

	![](images/noportalservice.png)

5. Click **Create** and select the portal_service to use as shown in below image.	
  
	![](images/create_portal_service.png)
	
6. Click **Save** and you should see a confirmation screen as in image below.

	![](images/create_portal_confirm.png)

7.  After a few minutes when Developer portal is ready, 
	Go to the **Portal URL** (shown in confirmation screen) in the new browser window.

8.  API Connect Developer Portal provides consumers access to API
    Catalog information to explore and test APIs, register Applications
    and subscribe to Plans. Portal Administrator can customize the looks
    and feel to their organizational specifications. The default
    Developer Portal looks like below:

    ![](images/tutorial_html_df45d2edf6f25ba8.png)
	
**Sign up for API Connect Developer Portal**

1. Sign Out from the admin account and click **Create account** in the top navigation of the Developer Portal site.

    ![](images/lab_2_03.png)

2. Fill up the form and click **Sign up**. You **must** use another email address. You cannot use the same email address as the admin account.

    ![](images/dev_portal_signup.png)

3. Click the account activation link in the confirmation email to activate your account.

**Login to API Connect Developer Portal**

1.  Some products are visible to all users without an account depending
    on the Product visibility setting. Additional options are available
    when you login to the Portal Server.

    Click **Sign in** to login to the portal

    ![](images/tutorial_html_279e27e5ac9b71cb.png)

2.  Login to portal user using the username and password supplied during Sign up.

    ![](images/tutorial_html_d0807a5f400162a.png)

3.  After successful login, you will see a Get Started page. Proceed to
    create a new Test application.

 Register a test app
==========================================================================

API Connect enforces entitlement rules to ensure that consumers are
allowed to access the APIs that are being requested. The instructions
below will guide you through registering your consumer application and
subscribing it to an API Product.

 Create A New Consumer Application
----------------------------------------------------------------------------------------------------------------------------------------------------

1.  Click [[Apps]] in the top navigation menu
    and then click *Create new App* button.

    ![](images/tutorial_html_114ebdd6ef4988c.png)

2.  Give your application the title **[IBM Consumer ]** and then
    click [[Save]].

    ![](images/tutorial_html_c4d9babec32568f9.png)

 Save the Consumer Application Credentials
-------------------------------------------------------------------------------------------------------------------------------------------------------------

When your consumer application is registered in the IBM API Connect
system, it is assigned a unique set of client credentials. These
credentials must be provided on each API request in order for the system
to validate your subscription entitlements.

1.  Click the [[Show]] box
    in both Key and Secret to reveal it. Copy the Key and Secret. Save
    it to a text editor. Then
    click [[Ok. ]]You
    can always come back to view the Key. However, if you lose the
    Secret, you will need to generate a new one in the app settings.

    ![](images/tutorial_html_aba0b5683b88b7d6.png)

2.  Now you\'ve entered the App Dashboard. Here you\'re able to see the
    analytics of your APIs.

 Subscribe to the API Product
------------------------------------------------------------------------------------------------------------------------------------------------

At this point, your registered consumer application has no entitlements.
In order to grant it access to an API resource, you must subscribe to a
Product and Plan.

1.  Click [[API Products]] at
    the top of the screen.

2.  Click the [[hotelreview 1.0.0]] product.

    ![](images/tutorial_html_38168de09ddc40f.png)

3.  Click the [[Select]] button
    for the default plan that is listed.

4.  Follow the steps to **Select your application**, **Confirm
    Subscription**, and **View Summary**. Then click **Done**.

    ![](images/tutorial_html_cfeb4fb8846dee41.png)

    ![](images/tutorial_html_95cbfb50e3695ef5.png)

 Test the API
===================================================================

The API Connect Developer Portal allows consumers to test the APIs
directly from the website. This feature may be enabled or disabled
per-API.

1.  Open the **hotelreview 1.0.0** API to browse the API definition.

    ![](images/tutorial_html_9830850c1b13f9c1.png)

2.  Click the [[GET /reviews]] operation
    on the left palette.

3.  In the right column, you will find information about the request
    parameters and links to the response schemas.

4.  Click the [[Try it]] tab.
	Specify the values for **page** and **size** parameters as shown below.

    ![](images/tutorial_html_a16511906f41b73.png)

5.  If you only have one application registered, it will be
    automatically selected in the **[Client ID]** drop-down menu. If you have more
    than one, select the application which is subscribed to this API
    Product.

6.  Paste your **[Client Secret]** into the
    provided field.

7.  Click the [[**Send**]] button
    to invoke the API.

8.  Scroll down to see the call results.

**[Note: If running for the first time, you may see Code: 0 No response
received. Causes include a lack of CORS support on the target server,
the server being unavailable, or an untrusted certificate being
encountered. Clicking the link below will open the server in a new tab.
If the browser displays a certificate issue, you may choose to accept it
and return here to test again.]**

![](images/tutorial_html_1b2581520ef305f.png)

 Summary
==============================================================

You completed the APIC Workshop Lab 2 - The Developer Portal Experience.
Throughout the tutorial, you explored the key takeaways: 

-   Configure Developer Portal and publish the APIs.

-   Create a Portal Account. 

-   Create App and Subscribe to Plan

-   Test API in Developer Portal. 

Continue the APIC Workshop Series! Go to [APIC Workshop Lab 3 - Add OAuth
Security to your
API](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab3) to
learn about configuring an OAuth provider service. 
