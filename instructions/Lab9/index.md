**APIC Workshop - Lab 9 -- Creating GraphQL API with StepZen**

In this lab, you will explore how you can quickly expose a REST backend as a GraphQL API. 

Using StepZen's CLI you can generate your GraphQL schema and resolvers for any backend data source (REST, Databases, GraphQL, Web3) with a few commands.

In this tutorial, you will do the following activities:

-   Sign-up for a free account in StepZen

-   Create GraphQL API for a REST backend

-   Deploy GraphQL API in StepZen

-   Test the GraphQL API

APIC Workshop Series
=======================================================================================================================================================================================================================================================================================================

The APIC Workshop AP Series is a hands-on workshop with lab exercises that
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

Prerequisites: Node.js and npm interface on your local machine. [Click here](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) for instructions.

 Create a GraphQL API with StepZen
=================================================================================

1.  Go to https://stepzen.com/developers and click on 'Start for Free' button in top right corner.

    ![](images/lab9-pic1.png)

2.  You can sign-up with your GitHub account or with your email address.

    ![](images/lab9-pic2.png)
    
    Make sure to verify the account by clicking on the link received in email.

3.  After you successfully sign-up, you will by default have subscription to free plan that allows you to host two endpoints and 300k calls/month. Click on the 'key' icon in left hand side menu bar to look at your account information.

    ![](images/lab9-pic51.png)
    
    The 'Admin Key' displayed here is used to authenticate to perform the administrative operations, like deployment of APIs in the account; while the 'API Key' is used to autneticate API calls at runtime.

4.  Click on the 'flag' icon in left hand side menu bar to go to getting-started page.

    ![](images/lab9-pic4.png)

5.  Click on the 'REST API' under 'All Connectors'. You will see the steps required to setup your CLI for StepZen and connect to your StepZen account.
     ![](images/lab9-pic52.png)
    
    Create a directory on your local machine and navigate to it using CLI:
    ![](images/lab9-pic6.png)
     
     Install the StepZen CLI
     
     `npm install -g stepzen`
     
     ![](images/lab9-pic7.png)
     
     Login with your StepZen account
     
     `stepzen login -a <Your account name>`
     
     Enter the admin key when prompted.
      ![](images/lab9-pic81.png)

6.  We have hosted a REST backend that returns a list of user details. Instructor will provide the url of the service
    
    <http://hostname/user/v1/showAll>
    
    Let us import this REST endpoint from the terminal using StepZen CLI.
    
    `stepzen import curl http://hostname/user/v1/showAll`
    
    Supply the api endpoint name as `api/getUsers` and enter.
    
    ![](images/lab9-pic9.png)
    
    Now type `stepzen start` in your terminal. This deploys the GraphQL API in StepZen and you can explore it from StepZen dashboard.
    
    ![](images/lab9-pic10.png)


7.  Now go to StepZen dashboard <https://dashboard.stepzen.com/explorer>. You should see the GraphQL API endpoint there.

    ![](images/lab9-pic11.png)

8.  From this playground you can test the hosted GraphQL API

   ![](images/lab9-pic12.png)


Summary
=================================================================================================================

Congratulations! You have successfully created a GraphQL API for a REST backend.

To learn more about StepZen, visit <https://stepzen.com/docs>

To learn more about Cloud Pak for Integration and API Life Cycle
Management, visit <https://www.ibm.com/cloud/cloud-pak-for-integration>


