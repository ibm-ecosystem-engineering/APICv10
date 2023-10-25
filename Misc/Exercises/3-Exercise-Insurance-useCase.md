## Use Case driven exercise - Insurance Use Case

#### Pre-requisites:
    1) Configure API Connect Developer Toolkit on your local machine
    2) Configure openldap user registry for API Manager
    
### Problem Statement

An insurance company is looking to implement API lifecycle management using IBM API Connect. You have 
been tasked to appropriately configure API Connect topology to support various environments, like DEV, 
UAT, PROD etc. You are supposed to configure two non-production environments, namely DEV and UAT on an 
API Connect instance. Note the following requirements and steps:
      
       - The organization should support 'DEV' and UAT environments in addition to the Sandbox environment.
       
       - All the environments, namely Sandbox, DEV and UAT, should have their developer portals.
       
       - Enable API lifecycle approval for 'Stage' and 'Published' states in both DEV and UAT environments. 
         Enable 'Take self-approval' option for simplicity of this exercise.
       
       - Enable approval for self service onboarding for both DEV and UAT developer portals.
       
       - API Developers will develop APIs using API Connect developer toolkit locally and should have ability
         to publish and test in Sandbox environment.
       
       - API Developers should have ability to request to 'Stage' the products onto DEV and UAT environments.
       
       - Administrators can review & approve the products to stage and publish to DEV and UAT environments.
         
       - A user with name 'developer' exists in the openldap registry. Assign this user 'Developer' role
         in the provider organization.
         
       - Start API Connect Developer Toolkit and connect to the provider organization using the provided 
         credentials for 'developer' user. Ensure that you have selected the correct provider organization
         (assigned to you) in the toolkit.
       
       - Use the term_plans API definition (look at the link to term_plans.yaml below under 'Hints') to create
         term_plans API in developer toolkit. Secure it with the client-id and client-secret. (You can follow 
         the steps from Lab1 for guidance)
       
       - Use the below as backend url for term_plans API
       <Instructor will provide backend url for term_plans service>
         
       - Enable the API and test it from the Test and Explorer options in toolkit
         
       - Create a product namely 'TermPlans' and create two plans with the names 'Silver' and 'Gold'. Follow 
         lab6 for directions.
       
       - Stage this product to DEV env.
       
       - Go to API Manager. Make sure you are logged in as Owner/Administrator (Credentials provided to you).
       
       - Approve the product and publish to DEV env.
       
       - Similarly publish the product to UAT env.
       
       - Onboard a consumer organization, namely 'Fintech' onto DEV environment's developer portal
       
       - Create a consumer application, namely 'BestPlans'
       
       - Subscribe to the product and test from developer portal.
       
       - Test the API from Postman
       




### Hints
1) Instructor will provide you the API Manager Platform api url to connect from developer toolkit.

2) Instructor will provide credentials for the 'developer' user in openldap.

3) [term_plans.yaml](https://github.com/ibm-ecosystem-lab/APICv10/blob/main/Misc/Exercises/term_plans.yaml) 
   can be downloaded from here.

