**APIC Workshop - Lab 7 - The Consumer Experience**

In this lab, you will explore the consumer experience for APIs that have
been exposed to your Sandbox catalog. Using the Developer Portal, you
will log in and subscribe to the latest Accessories Product and test the
APIs from the portal, before testing it in a live Web Application.

In this tutorial, you will explore the following key capabilities:

-   Subscribe to a plan in order to consume an API.

-   Test an API from the developer portal.

-   Consume an API from a sample test application.

 APIC Workshop Series
======================================================================================================================================================================================================================================================================================

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

Prerequisites: Labs 1-6

 Subscribe to the Think Accessories Product
==========================================================================================

In this section, you will subscribe to a plan for the
Accessories Product using the IBM Consumer application.

1.  Launch the Developer Portal in a browser using the link provided.

2.  If you are logged in to the portal, log out to clear your session.

3.  Click the [[API
    Products]] link.  ![](images/tutorial_html_444fff2d8e0d46b7.png)

4.  Notice that Accessories product is not listed, even though you
    just published the Accessories product. Recall that you assigned the
    Accessories product to be visible only by developers who are logged
    in to the portal.

5.  Enter Login page using Sign in option at the top right corner of the
    page.

    ![](images/tutorial_html_db604e248301f829.png)

6.  Login using the username \<portaluser\> and password
    \<portaluser-password\>

    ![](images/tutorial_html_492593c5f2350159.png)

7.  Click the [[API
    Products]] link
    after logging in.

8.  Select the [[ Think Accessories
    1.0.0]] product. 

    ![](images/tutorial_html_6efccbf2582a30c0.png)  

9.  You will be directed to the Product page which lists the available
    plans for subscription.
    Click [[Select]] under
    the [[Silver]] plan.  ![](images/tutorial_html_fd5ece1fe8b66fa5.png)

10. **Note:** The Gold plan requires approval by the API provider for
    any subscription requests and allows unlimited requests for a given
    time period. The Silver plan is limited to 100 requests per hour and
    does not require approval by the API provider for subscription
    requests.

11. A subscription wizard is initiated. All the applications available
    are displayed (in this case we only have the IBM Consumer
    application). Click [[IBM Consumer]].  
    ![](images/tutorial_html_fe0fc338b5ae9fd3.png)

12. A window with the subscription details is displayed to confirm the
    information provided.
    Click [[Next]] once
    you have reviewed the
    information.  
    ![](images/tutorial_html_ea31c68f8a08a741.png)

13. The last step is displayed with the summary of the subscription.
    Click [[Done]] to
    finalize the
    wizard.  
    ![](images/tutorial_html_359b7068e5f3a808.png)

 Test APIs from the Developer Portal
============================================================================================================================

In this section, you will use the Developer Portal to test one of the
Accessories APIs. This is useful for application developers to try the
APIs before their application is fully developed or to simply see the
expected response based on inputs they provide the API.

1.  Click the [[logistics
    2.0.0]] API
    link on the Accessories product
    page.  
    ![](images/tutorial_html_8ec6b1024d5a2f9a.png)

2.  Click the [[GET
    /shipping]] path
    on the left navigation menu. 

3.  Click the \`Try it\` link to access the test
    area.  
    ![](images/tutorial_html_6326764a039cba2b.png)

4.  Scroll down to the Parameters section, enter any **United State Zip
    Code** (e.g., \`90210\`) and
    click [[Send]] to
    invoke the API.  
    ![](images/tutorial_html_74d26a44eab03d67.png)

5.  You should see a [[200
    OK ]]and
    a response body as shown
    below.  
    ![](images/tutorial_html_f9b90c1492df91e8.png)

6.  Go ahead and try out the [[Logistics GET
    /stores]] and
    the [[Financing GET
    /calculate ]]APIs
    as well.

 Summary
================================================================================================

Congratulations! You have created multiple plans, tested APIs in the
developer portal, and used the APIs in a consumer application. 

Continue with the APIC Workshop Series! Go
to [Lab 8: Create and test GraphQL Proxy
API](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab8) to
explore working with GraphQL APIs in API Connect.
