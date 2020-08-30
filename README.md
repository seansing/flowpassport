# FlowPassport Cadence Smart Contract

FlowPassport Cadence Smart Contract for Flow OWB Program 

This smart contract was derived from the idea that every governmental body in the world will come together and form an association dedicated to uniting passports and any cross crountry travel documentation like Visas.   
Each participating governmental body will serve as a member who will be responsible for validating nodes to maintain the Flow blockchain and ensuring the necessary steps to maintain operability and implementation of the digital passport system are carried out coherently. 

The FlowPassport smart contract shall operate as a standardized global digital passport smart contract on the Flow blockchain. It will be maintained by the FlowPassport Association to help create a passport for new applicants, issues it to the applicant, and update their travel logs as they depart and enter countries around the world.

This proof of concept (PoC) does not cover the details of setting up adminitrative rights for each participating member or processing Visa applications between countries for example. 
It will showcase how the Flow resource can be used by an authorised member to create a passport resource, send the resource to a citizen and update its travel logs with signatures from the admin and citizen.

Visit the contract's Flow Playground here: https://play.onflow.org/3ad97f1c-87af-4da6-a561-0bbbfa3f22b4

Deployment (flowpassport.cdc):

1. The FlowPassport Association admin first deploys the smart contract, which contains two resources: Passport and Admin. 
    - Passport resource contains the informations for a citizens passport and will be issues to a citizen once created.
        For this PoC, a passport contains the following information of a citizen: 
        -Name : String
        -Date of Birth : String
        -Gender : String
        -Citizenship : String
        -Visa : { String : bool } 
        -Travel Log : [ String ] 
    - Admin resource allows for authorized admins to utilize its Admin resource to create passports (eg. each govermental body)  

Transactions (respective number_cdc files):

1. The FlowPassport Admin issues the new passport to the respective citizen using the 1_create_and_issue_passport.cdc transaction.

2. For the first travel, a citizen departs and tries to enter a country without a Visa via the 2_citizen_travels.cdc transaction
    This transaction is expected to fail to demonstrate what happens to a citizen who does not have a valid Visa in his passport.

3. The Admin updates the Visa status for the citizen's passport via 3_update_visa.cdc transaction.

3a. The citizen tries transaction 2_citizen_travels again and gets a successful entry to the country. 

4. An external admin can utilize the created capability to call the createPassport function using the 4_use_admin_capability.cdc transaction.

Future additional features to add to the passport: 
-Visa expiry date (automatic updates to visa status)

