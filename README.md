# FlowPassport Smart Contract

## Introduction

FlowPassport is a smart contract written in Cadence for the Flow blockchain.

It stemmed from an idea that every governmental body in the world will come together and form an association dedicated to uniting passports and cross crountry travel documentation like Visas.   

The FlowPassport smart contract shall operate as a global digital passport smart contract on the Flow blockchain and used to creating and issueing passports to new applicants and update Visa statuses and travel logs as citizens depart and enter countries around the world.

This a proof of concept (PoC) showcases how the Flow resource can be used by an authorised member. to create a passport resource, send the resource to a citizen and update its travel logs with signatures from the admin and citizen.

## Presentations

- YouTube video on product presentation:

- YouTube video on FlowPassport Demo on the Playground:

- Google Slides presentation: 

## Testing FlowPassport

Visit the contract's Flow Playground here: https://play.onflow.org/3ad97f1c-87af-4da6-a561-0bbbfa3f22b4

or

1. Deploy the smart contract in using the flowpassport.cdc file.
2. Run transactions 1_ through 4_ based on the workflow below: 

## Workflow 

*Deploy `flowpassport.cdc` on Flow Playground:* 

1. The FlowPassport Admin first deploys the smart contract, which contains two resources: Passport and Admin. 
    - Passport resource contains the informations for a citizens passport and will be issues to a citizen once created.
        For this PoC, a passport contains the following information of a citizen: 
        -Name : String
        -Date of Birth : String
        -Gender : String
        -Citizenship : String
        -Visa : { String : bool } 
        -Travel Log : [ String ] 
    - Admin resource allows for authorized admins to utilize its Admin resource to create passports.

*Transactions:*

1. The FlowPassport Admin issues the new passport to the respective citizen using the `1_create_and_issue_passport.cdc` transaction.

2. For the first travel, a citizen departs and tries to enter a country without a Visa via the `2_citizen_travels.cdc` transaction
    This transaction is expected to fail to demonstrate what happens to a citizen who does not have a valid Visa in his passport.

3. The Admin updates the Visa status for the citizen's passport via `3_update_visa.cdc` transaction.

3a. The citizen tries transaction `2_citizen_travels.cdc` again and gets a successful entry to the country. 

4. An external admin can utilize the created capability to call the createPassport function using the `4_use_admin_capability.cdc` transaction.


