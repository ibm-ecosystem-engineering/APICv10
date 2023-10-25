## Use Case driven exercise - Banking Use Case
### Problem Statement

A bank has two organizations (business units), namely 'Retail' and 'Wholesale'. They are looking to implement a multi-tenant
deployment of API Connect to cater the needs of both the organizations. An API Connect instance has been deployed on a CP4I
cluster and you have been tasked to appropriately configure the environments. Note the following requirements and steps:
      
       - API Manager needs to authenticate users from LDAP registry.
       
       - Both the organizations need isolated API management environments.
       
       - Owner of 'Retail' organization should be user 'vest1' from the LDAP registry.
       
       - Owner of 'Wholesale' organization should be user 'vest2' from the LDAP registry.
       
       - Users of the LDAP registry should be scoped to their API manager environment only 
         and should not have ability to manage/modify the API Connect cluster.
         
       - Add another user 'vest3' from Open LDAP as developer into both 'Retail' and 'Wholesale' organizations.
       
       - Both the organizations need to have their DEV and UAT environments.
       
       - Each environment needs to have their own developer portal.
       
       - Enable API lifecycle approval for 'Stage' and 'Published' states in both DEV and UAT environments 
         for both the organizations. Enable 'Take self-approval' option for simplicity of this exercise.
         
       - In organization 'Retail', enable approval for self service onboarding for both DEV and UAT developer portals.
       
       - Logout and Login as user 'vest3' into API manager and select 'Retail' organization
       
       - Use the deposit API definition (look at the link to deposit.yaml below under 'Hints') to create an API 
         in 'Retail'. Secure it with the client-id and client-secret. (You can follow the steps from Lab1 for guidance)
       
       - Use the below as backend url for deposit API
         <Instructor will provide the url for backend deposit service>
         
       - Create a product namely 'Deposit' and create two plans with the names 'Silver' and 'Gold'. Follow 
         lab6 for directions.
       
       - Test this API in Sandbox environment
       
       - Stage this product to DEV env while you are logged in as 'vest3' user. Try to publish it.
       
       - Logout and login as user 'vest1'. Now approve this product and publish.
       
       - Stage and Publish this product to UAT env.
       
       - Onboard a consumer organization, namely 'Fintech' onto DEV environment's developer portal
       
       - Create a consumer application, namely 'BestDeposits'
       
       - Subscribe to the product and test from developer portal.
       
       - Test the API from Postman
       




### Hints

1) [deposit.yaml](https://github.com/ibm-ecosystem-lab/APICv10/blob/main/Misc/Exercises/deposit.yaml) can be downloaded from here.

2) Use below information for configuring Open LDAP registry:

Create a new Open LDAP user registry in cloud manager. Open LDAP credentials will be provided by lab instructor. 

##### LDAP Server and port: 
        Will be shared by the instructor
      
#### Authentication method: 
        Compose DN
      
#### Admin DN: 
        cn=admin,dc=gsilab,dc=ibm,dc=com
      
#### Password: 
        Will be shared by the instructor
      
#### Prefix: 
        uid=
      
#### Suffix: 
        ,ou=People,dc=gsilab,dc=ibm,dc=com

#### Credentials for users vest1, vest2 and vest3
        Will be shared by the instructor
      
      

![](images/open_ldap_config.png)

