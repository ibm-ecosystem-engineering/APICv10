**APIC Workshop - Lab 8 -- Creating GraphQL Proxy API**

In this lab, you will explore the how to define GraphQL APIs that proxy
to a backend GraphQL server. GraphQL is a query language for APIs that
gives an application client greater control over what data it retrieves
in an API request when compared with a REST API request.

API Connect GraphQL support also allows rate limiting and other controls
using API Gateway.

In this tutorial, you will explore the following key capabilities:

-   Create a GraphQL Proxy API

-   Learn about GraphQL introspection and Schema Editor

-   Test APIs by using the built-in GraphQL editor

-   Review API Assembly Policies for the cost end point

APIC Workshop Series
=======================================================================================================================================================================================================================================================================================================

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
login Common Services registry.]**

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

Prerequisites: None

 Create a GraphQL Proxy API
=================================================================================

1.  Select Develop API and click Add-\>API

    ![](images/tutorial_html_c0c5acec16e566bb.png)

2.  To create a GraphQL proxy definition, select From Existing GraphQL service. When you
    point to an existing GraphQL server, API Connect introspects the
    service and automatically creates a GraphQL proxy service.

    ![](images/tutorial_html_797b2f887d77017c.png)

3.  We will use SWAPI (The Star Wars API).
	Enter the following values and click Next. You can use default
    values for the rest.

    Title: `swapi`

    GraphQL server URL: `https://swapi-graphql.netlify.app/.netlify/functions/index`

    ![](images/tutorial_html_f83e60ae96763438.png)

    ![](images/tutorial_html_90e0cbad29eca5a.png)

4.  The schema validator reports warning and errors if found. There are 88
    warnings in the swapi schema imported from the server. You can
    review the schema warning details and also select the end points
    interested for this proxy. Select all the available end points.

    ![](images/tutorial_html_3cc23a786c4f73c2.png)

5.  A review of the schema shows that no limit is set on the size of the
    list. You will fix this warning in later steps. Click Next to
    continue.

    ![](images/tutorial_html_8104c10fce21e609.png)

6.  Keep both Secure Client ID and CORS checked and click Next

    ![](images/tutorial_html_464f81f24c7d47dd.png)

7.  API Connect successfully created a GraphQL proxy API. You can edit
    the API to view more details on the proxy API just created. Click
    EDIT API to continue.

    ![](images/tutorial_html_e70bb58508f9b662.png)

8.  GraphQL APIs are structured the same as REST APIs with some
    additional options. Just like REST APIs, you will be able to add
    security definitions, properties and Activity logs from the left
    menu bar. You can also view the Source and Policies tabs similar to
    REST APIs. You will notice a new tab for GraphQL APIs. Click on
    GraphQL Schema tab to view the schema.

    ![](images/tutorial_html_b27d147e1a49276b.png)

9.  GraphQL Schema editor displays Type and Weight information. The
    weighting factor is used when calculating the type cost for a
    request to the GraphQL API. For example, a field that requires
    extensive CPU or memory use on the server to retrieve its value
    would be given a higher cost.

    ![](images/tutorial_html_ab0c11b157a7cd4b.png)

10. Click View in the warnings to review the warning details. In
    addition to the warning details, the Warning window gives an option
    to fix the warnings by apply the limits. Click Apply All to continue.

    ![](images/tutorial_html_ed0f88002c9eb816.png)

11. After applyting the recommendation the wanrning message is removed.
    Click Save to save the API definition .

    ![](images/tutorial_html_63ce76efdb0032d7.png)

12. Select Policies in Gateway tab to view the API in Assembly view. The flow is
    automatically created as part of the initial API creation. You may
    apply addition logic by dragging and dropping items from the pallet
    to the canvas. In this tutorial, you are not adding additional
    logic.

    ![](images/tutorial_html_a2cd4daada4f2ca5.png)

13. Swapi GraphQL backend API doesn't support compression, hence we need to 
    disable the compression. Click the Source button next to Pencil icon at the top 
	and search for **compression** and set the value to `false`, as shown below.
	
	![](images/compression_flag.png)		

14. Save the changes. To publish the API toggle the button from offline to online.

    ![](images/tutorial_html_965b91d211caf432.png)

15. After successfully publishing the API to API Gateway, additional
    tabs appear on the screen. Select Test tab to test the API.

    ![](images/tutorial_html_ccb982e24326f44f.png)

16. To test the API select the end point for POST method. The URL should look like this (your
    value may be different):

    <https://apic-gw-gateway-apic.apps.ocp-060001q8qm-ada2.cloud.techzone.ibm.com/joy-vad/sandbox/swapi/graphql>
      

17. API Connect Test feature also includes GraphQL Editor called **GraphiQL**. Enter the
    following in GraphiQL Editor window. You may use Prettify option
    to view formatting string.

```
query Query {
	allFilms(last: 10) {
		edges{node{title}}
		films {
			title
			episodeID
			vehicleConnection(last: 10) {
				vehicles {
					name
					model
				}
			}
			speciesConnection(last: 1000) {
				species {
					name
					designation
					classification
					personConnection(last: 10) {
						people {
							name
							gender
						}
					}
				}
			}
		}
	}
}
```

18. Click Run button to send the GraphQL request to the end point. An
    exception window will appear when you use test the API for the first
    time.


19. Click accept Exception to continue.

    ![](images/tutorial_html_98d8f253e9342c8b.png)

    You may see an invalid certificate issue page when you continue. This is
    because valid certificates are not applied in this test environment. If
    you are using Chrome browser you can accept the exception by typing
    "thisisunsafe" anywhere in the window. Similar workarounds are available
    for other browsers. For firefox browser, follow the steps from here -
    <https://support.mozilla.org/en-US/kb/error-codes-secure-websites>    

20. The results for GraphQL request are displayed on the right panel. 

    ![](images/tutorial_html_1d05935575c71f8e.png)

21. You can request additional queries, refer to the schema editor
    for details or go to https://github.com/graphql/swapi-graphql/tree/master/doc/example_queries for example requests).
    
```
query Query {
	allVehicles(last: 10) {
		edges{node{name}}
		vehicles {
			name
			manufacturers
      model
      vehicleClass
			
			pilotConnection(last: 10) {
				pilots {
					name
					birthYear
					eyeColor
					gender
				}
			}
		}
	}
}
```

![](images/tutorial_html_e37331678c3d02b2.png)


 Create a Product and apply GraphQL RateLimits
====================================================================================================

1.  To create a product Select Develop icon from left menu bar and click
    Add-\>Product

    ![](images/tutorial_html_4f43bda35452bd65.png)

2.  Name the product as Swapi Product and click Next

    ![](images/tutorial_html_d0c3992a4bd7bc24.png)

3.  Add swapi API to the product by selecting swapi. Click Next to
    continue to create the swapi-product.

    ![](images/tutorial_html_4ae09f5fddd82bab.png)
	
4. Select the Default Plan and Click Next.	

5.  Accept the default for Visibility and Subscribability and Click Next

    ![](images/tutorial_html_1adf1922464ea393.png)

6.  Click Edit Product to Edit the product swapi-product to review the details. 
    
	![](images/edit-product.png)

7.	The Default Plan contains traditional rate limiting options but you will notice
    another section that list GraphQL Rate Limits.

    ![](images/tutorial_html_15d9c2582155eea8.png)

8.  You will be able to adjust GraphQL cost parameters from this
    section. You can set a limit or make it unlimited. You will not be
    making any changes in this tutorial.

    ![](images/tutorial_html_3c25f5d5dab1988e.png)


9.  Publish the Product to Sandbox Catalog and Click Next.

    ![](images/tutorial_html_a1f1cf7707e31913.png)

10.  Accept the default for Visibility and Subscribability    

11.  Click Publish to complete publishing the product.

 ![](images/tutorial_html_890ebcd8219b104.png)


 Test GraphQL API from Developer Portal
=============================================================================================

1.  Sign in to API Connect Developer Portal using the Developer Portal
    URL, username and password.

    ![](images/tutorial_html_540cbe0b9202f4a7.png)

    ![](images/tutorial_html_c34973eb377015ce.png)

2.  Go to API Prpducts in top menu. Developer Portal displays all the products that are currently
    published. Locate swapi-product and select the product.

    ![](images/tutorial_html_2635d049f12d59c6.png)

3.  The selected product lists one API (swapi api) and one Plan
    (Default Plan). Click Select to subscribe to the plan.

    ![](images/tutorial_html_bd0ea34d4f40d756.png)

4.  The Plan subscription requires an Application. You can create a new
    Application or select the IBM Consumer application that is already
    created.

    ![](images/tutorial_html_2fd3cf48168675e5.png)
	
5.  Subscribe to swapi product and Click Next.

6.  Review summary and Click Done.

    ![](images/dev_portal_subscription.png)			

7.  Select swapi API to review and test the API. Click swapi to
    continue

    ![](images/tutorial_html_8a5975dd9780a924.png)

8.  Developer Portal displays the type as GrahQL API. Currently Client
    ID security is enforced. Since there is only one Plan and one
    Consumer Application, the Consumer ID filed is already populated.

    ![](images/tutorial_html_e8892b4b3da410fc.png)

9.  To continue to test the API, use the GraphQL Editor. Submit requests
    with different field names and watch how quickly the results are
    returned in the results window. If this was a REST API multiple end
    points will be needed to achieve the same result.

    ![](images/tutorial_html_9575e27d8184b8fc.png)

Summary
=================================================================================================================

Congratulations! You have successfully created a GraphQL Proxy API,
published the API as part of a Product, applied controls and rate
limits, and tested using Developer Portal.

Continue with the APIC Workshop Series! Go
to [Lab 9: Creating GraphQL API with StepZen](https://github.com/ibm-ecosystem-lab/APICv10/tree/main/instructions/Lab9) to
explore StepZen.
