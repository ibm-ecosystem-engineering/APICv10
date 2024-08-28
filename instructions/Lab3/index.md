**APIC Workshop Lab 3 - Add OAuth Security to your API**

In this lab, you will secure the HotelReview API to protect the resources
exposed by **API Connect**. Consumers of your API will be required to
obtain and provide a valid OAuth token before they can invoke the
HotelReview API.

In this tutorial, you will explore the following key capabilities:

-   Configure an OAuth 2.0 service, the Resource Owner Password grant
    type.

-   Clone a new version of an API.

-   Secure the new version of your API.

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

[Lab 9: Creating GraphQL API with StepZen](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab9)


Prerequisites: Labs 1-2

 Configure a New OAuth 2.0 Provider API
=============================================================================================

API Connect is a full-featured OAuth 2.0 provider. The OAuth exchange
works like any other API call, and thus we treat it as its own API. In
this section, you will create a new OAuth provider API, configure which
grant type to use, and configure how it will authenticate user
credentials.

 Create OAuth Service
----------------------------------------------------------------------------------------------------------------------------------------

1.  In the Cloud Manager from the main menu on the left,
    click [[Resources]].

2.  In the Resources menu, click  [[OAuth Providers-\> Native OAuth
    Provider]].

    ![](images/tutorial_html_f1fe85d169c1b8fc.png)

3.  Specify the following properties and
    click **[Next]** to continue.

    Title: `oauth`

    Name: `oauth`

    Gateway Type: `DataPower API Gateway`

    ![](images/tutorial_html_22f9d0d5c30f657d.png)

4.  The next configuration screen will display the default paths to the
    Authorize and Token functions. For Supported grant types,
    choose [[Resource owner
    password]].
    For Supported Client types,
    choose [[Confidential]].
    Click [[Next]] continue.

    ![](images/tutorial_html_2e278c6df90a639f.png)

5.  One scope is generated for you
    : [**[sample_scope_1]**[.]]

6.  Modify the values
    for **[sample_scope_1]**, set the
    following fields:

    Name: `hotelreview`

    Description: `Access to Hotel Review API`

    ![](images/tutorial_html_b42ee8bacaf23a4c.png)

7.  Click [[Next]].

8.  Click [[Create sample user registry]] button.

    ![](images/create_sample_user_registry.png)
	
9. Select the newly created Sample registry **SampleAuthURL** from the dropdown and Click [[Next]].

    ![](images/sample_user_registry.png)
	
10. Review your OAuth configuration and
    click [[Finish]].

    ![](images/tutorial_html_985e9dbc3a3f82c0.png)

 Add the OAuth Service to the Sandbox Catalog
----------------------------------------------------------------------------------------------------------------------------------------------------------------
1. Go to API Manager, Open Sandbox Settings follow
    Home-\>Manage Catalogs-\>Sandbox-\>Catalog Settings->API User Registries.
	From the Sandbox Catalog registry setting, select API User
    Registries and Add App Registry.

    ![](images/user_registry.png)

    Use **Edit** option and enable available API registry.

    ![](images/tutorial_html_c24f06de482a8ab5.png)

2.  From the Sandbox Catalog settings, click [[OAuth
    Providers]] in the left navigation menu.

3.  Click [[Edit]].

4.  Choose the OAuth service created above. Then
    click [[Save]].    

    ![](images/tutorial_html_6fa9961893476e8e.png)

 Create a New Version of the HotelReview API
================================================================================================

API Connect supports multiple versions of APIs. Create a new version of
the HotelReview API before making any changes that would break
functionality for existing consumers. 

 [Save as a New Version]
-----------------------------------------------------------------------------------------------------------------------------------------

1.  In the API Manager from the main menu on the left,
    click [[Develop]].

2.  Click on the menu icon to the right of [[HotelReview
    1.0.0]] API
    and select [[Save as a new
    version]].  

    ![](images/tutorial_html_4f0d083547b597a4.png)

3.  Enter the new version number
    as `2.0.0` and
    click [[Submit]].

 Add OAuth security to the HotelReview API
==============================================================================================

Modify the security policy for your new API version to tell it to use
your OAuth 2.0 provider.

1.  From the Develop home page, click \`**hotelreview 2.0.0**\`

2.  Navigate to the **[Security Scehmes]** section.

3.  Click [[Add]].

4.  On the API Security Scehmes screen, enter the following:

    -   Name: `oauth-1`

    -   Description: `API OAuth security definition`

    -   Type: `OAuth2`

    -   Flow: `Resource owner - Password`

    -   Token URL: keep
        default `https://$(catalog.url)/oauth/oauth2/token`

    -   Leave everything else to the default values and
        click **Save**.  

        ![](images/tutorial_html_9b9f57dc81561ae7.png)

5.  Navigate to the **Security** section and check the **oauth-1 (OAuth)** checkbox. 
	Make sure **hotelreview** is also selected under scope.
    
    ![](images/hotel_review_scopes.png)  

    ![](images/tutorial_html_c8a8e86664fd2a1.png)

6.  Save your changes.

 Summary
==============================================================

You completed the APIC Workshop Lab 3 - Add OAuth Security to your
API. Throughout the tutorial, you explored the key takeaways:

-   Configure an OAuth 2.0 service, the Resource Owner Password grant
    type.

-   Clone a new version of an API.

-   Secure the new version of your API.

Continue the APIC Workshop Series! Go To [APIC Workshop Lab 4 - Use
Lifecycle controls to version your
API](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab4) to
manage the lifecycle of this API and test your new OAuth secured API.
