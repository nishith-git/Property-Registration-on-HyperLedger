# Property-Registration-on-HyperLedger
Property registration and data mentioned using hyperledger fabric
Introduction
Welcome to the course project on ‘Hyperledger Fabric’. As part of this project, you will build a solution for a ‘Property Registration System’ using Hyperledger Fabric.

 

Origin of Property Registration
Property registration is the process through which you register the documents related to a property of yours with legal entities. For instance, when you purchase a flat directly from a builder, property registration gives you the right to legally own, use or dispose of that property. When you have a legal ownership title over a property, there is a low likelihood of fraud or misappropriation. 
 

Need for Property Registration
Property registration is required for maintaining ownership of land/property deeds. There are many reasons why you should get your property registered:

To avoid conflicts: Proper property registration helps you avoid conflicts arising from land disputes.
To maintain ownership: Property registration also helps with identifying the rightful owner of a property.
To comply with legal processes: Many legal processes require individuals to furnish proper land deeds and documentation.
 

These requirements make the property registration process an essential part of the legal and financial worlds. A traditional property registration process already exists, but it has major challenges. Through this case study, you will assess and tackle the challenges of the traditional property registration process. But first, we will look at what the challenges are.

 

Problems/Challenges of Property Registration
Property registration is a mere record of a sales transaction.
There could be multiple parties claiming ownership of the same property.
Although property ownership can be challenged in court, the verification process is cumbersome and time consuming.
Ownership documents could be tampered with.
Tampering of land deeds can lead to the wrong individuals acquiring ownership of properties for personal gain. This is a major issue in developing countries and also creates a huge backlog of civil cases in courts.
Benami registrations: This is a transaction in which a property is transferred to one person for the consideration paid by another. This also leads to corruption and tax evasion.
Solution Using Blockchain
Blockchain is an immutable distributed ledger that is shared with everyone present on a network. Each participant interacts with the blockchain using a public–private cryptographic key combination. Moreover, the records stored on the blockchain are immutable, making them very hard to tamper with. This provides better security. A solution such as Hyperledger Fabric also offers the features to maintain users and roles, which additionally help secure and identify owners. 

 

The government can utilise the feature set of a blockchain to reduce the difficulties faced in the traditional property registration process. A distributed ledger can be set up among the buyer, seller, bank, registration authority and notary. Property details can be stored in the blockchain and accessed from it, and these details are immutable, meaning they cannot be altered by anybody.

 

In the upcoming segments, you will see the blueprint of the solution. But before proceeding, we recommend that you go through some of the additional reading material on the ‘Property Registration System’. This reading material will help you understand the problem statement better. 

 

Additional Reading
To understand more about the land registry process and the issues with the current system, please go through the following resources. 

Resource 1

Resource 2

Resource 3

Solution Blueprint
In the previous segment, you understood the motivation behind building a blockchain solution for the ‘Property Registration System’. Now, in this segment, we will discuss the blueprint of the solution. We will discuss the blueprint in this order:

Stakeholders of the network
Logical flow 
Assets on the ledger
 

1. Stakeholders of the Network
This case study involves two stakeholders: Users and registrar. 

 

1.1. Users are the people who wish to sell/buy the properties registered on this network. They need to be explicitly registered on the network in order to be able to buy/sell the properties registered on it.

 

1.2. Let’s take a look at Registrar now. In the traditional Property Registration System, a registrar is the record keeper who facilitates, monitors and validates all the property or land transactions. In this problem statement, the registrar has multiple roles. For example, if a user wishes to register themselves on the system, then the registrar must validate the identity of the user before adding them to the system. Talking of another use case; suppose a user wishes to register their property on the network. They would first raise a request to the registrar who, in turn, would register the property on the ledger after validation.

 

2. Logical Flow
The entire flow of this case study can be divided into three parts:
2.1. User registration
2.2. Property registration
2.3. Property transfer 

 

Let’s take a look at each of these subparts individually.

 

2.1. User registration: This process comprises the following steps:

 

2.1.1. A user with permission to access the network raises a request to the registrar to store their data/credentials on the ledger.

2.1.2. The request gets stored on the ledger. 

2.1.3. The registrar reads the request and stores the user’s data/credentials on the ledger after validating their identity manually.  

2.1.4. There is a digital currency called ‘upgradCoins’ associated with each user’s account. All the transactions on this network can be carried out with this currency only. When a user joins the network, they have 0 ‘upgradCoins’.

 

2.2. Property registration: This process comprises the following steps: 

 

2.2.1. A user added to the Property Registration System raises a request to the registrar to register their property on the network.

2.2.2. The request gets stored on the ledger.

2.2.3. The registrar reads the request and stores the property on the ledger after validating the data present in the request. Let’s take an example to understand this. Suppose Mr Garg registers himself on the network and raises a request to register his farmhouse in Lonavla. Now, before registering the property on the ledger, the registrar needs to verify whether it is real and whether it actually belongs to Mr Garg.

 

Note: In this process, the property gets only registered on the system. It can be purchased by other registered users only if its owner explicitly wishes to list it for sale. You will understand this better as you move ahead with the problem statement. 

 

2.3 Property transfer: This process comprises the following steps:

 

2.3.1. The owner of the property must put the property on sale.

2.3.2. The buyer of the property must ensure that the amount of ‘upgradCoins’ they have is greater than or equal to the price of the property. If not, then the user must recharge their account.

2.3.3. If the two criteria above are satisfied, then the ownership of the property changes from the seller to the buyer and ‘upgradCoins’ equal to the price of the property are transferred from the buyer’s account to the seller’s.

 

3. Assets on the Ledger
3.1. Users: Each user’s data/credentials, such as name, email ID and Aadhar number, need to be captured before they can be allowed to buy/sell properties on the network. The credentials of every user are stored as states on the ledger.
3.2. Requests: Recall that users need to raise a request to the registrar in order to register themselves on the network or buy property on the ledger. These requests get stored on the ledger.
3.3. Property: The properties owned by the users registered on the network are stored as assets on the ledger.


You need to define several functions inside your chaincode in order to implement these functionalities. We will discuss each of these functions separately in the problem statement.

 

The entire case study can be split into two distinct sections: ‘Fabric Network Setup’ and ‘Chaincode Development’. We will look at each of these sections individually in the upcoming segments. 

Fabric Network Setup
There are two organisations in the network: ‘Users’ and ‘Registrar’. There are two peers defined for the organisation ‘Registrar’ and three peers defined for the organisation ‘Users’. The buyers/sellers registered on the network would use the peers of the organisation ‘Users’ to invoke functions to perform tasks such as user/property registration. Similarly, the registrars registered on the network would use the peers of the organisation ‘Registrar’ to perform functions such as approval of requests for user/property registration.

 

As part of this assignment, you need not write the configuration files for setting up the network. All the configuration files, along with the script files to automate the process of network set-up and chaincode installation, are provided to you and are attached at the end of this segment. You may start developing the chaincode for this case study right away. 

 

The script files provided inside the network folder of the ‘property-registration’ folder are configured for this case study. Hence, the commands to start the network and install the chaincode using these script files (which you saw in the ‘Chaincode Development’ module for the ‘certification-network’) would remain the same.

 

Property-Registration Project 
Chaincode Development
As part of developing the smart contract for the ‘property-registration-network’, you need to implement the logic for the transactions given below.

 

Transactions
 

requestNewUser

Initiator: It will be the user. 
Output: A ‘Request’ asset on the ledger will be the output. 
Use case: This transaction is called by the user to request the registrar to register them on the property-registration-network. 


Flow

A user registered on the network initiates a transaction to request the registrar to store their details/credentials on the ledger.
The details include:
Name,
Email ID,
Phone number
Aadhar Number and
CreatedAt.
All these details will be stored as a Request state on the ledger in the form of key–value pairs. The name and Aadhar Number of the user, along with appropriate namespace, should be used in order to create a composite key for this Request asset on the ledger.
The transaction will return the Request object.
 

approveNewUser

 

Initiator: It will be the registrar. 
Output: A ‘User’ asset on the ledger will be the output. 
Use case: The registrar initiates a transaction to register a new user on the ledger based on the request received. 

 

Flow 

This function takes, as input parameters, the name and Aadhar Number of the user who generated the request for registration. 
The user’s Request object is fetched from the ledger. The request contains several details about the user.
These details are then used to create a new User asset on the ledger.
A new field named ‘upgradCoins’ will get added as an attribute. ‘upgradCoins’ is a kind of currency that can be used by each user to purchase property on the asset. For example, if the price of a property is stated as 500 upgradCoins, then only a user with ‘upgradCoins’ equal to or greater than 500 will be able to purchase it. The initial value of this attribute is set to 0. There is a separate function to recharge the account balance. We will look at this next.
 

rechargeAccount 

 

Initiator: It will be the user. 
Use case: This transaction is initiated by the user to recharge their account with ‘upgradCoins’.


Flow 

This transaction is used by a registered user to recharge their account with ‘upgradCoins’. Before initiating the transaction, the user needs to pay the price of the ‘upgradCoins’ that they wish to purchase. They need to pay this to the network admin. In return, the user would receive a Bank Transaction ID, which they need to pass as a parameter at the time of initiating the transaction.
This function takes the Name, Aadhar Number and bank transaction ID of the user as input. 
If the bank transaction ID passed as input to the function is valid, then the data corresponding to the user ID is fetched from the ledger and the ‘upgradCoins’ attribute is updated.
Each bank transaction ID has some associated transaction amount. In an ideal case, this information about a transaction will be provided by the bank involved in the transaction. However, for this case study, we will validate the input bank transaction ID against a predefined list of transaction IDs.
Bank Transaction ID	Number of upgradCoins
upg100	100
upg500	500
upg1000	1,000
 

For example, if ‘upg500’ is passed as an input parameter by Mr. Garg, then his account gets recharged with 500 upgradCoins. If a transaction ID other than that mentioned above is passed, then the transaction is declined with the message ‘Invalid Bank Transaction ID’.
 

viewUser

 

Initiator: It will be either the user or the registrar. 
Use case: This function should be defined to view the current state of any user.

 

propertyRegistrationRequest

Initiator: It will be the user. 
Output: A ‘Request’ asset on the ledger will be the output. 
Use case: This function should be initiated by the user to register the details of their property on the property-registration-network.


Flow 

A user registered on the property-registration-network raises a request to the registrar to store their property details on the ledger.
The details include the following:
Property ID: Ideally, it should be a string comprising the geo-coordinates of the property to identify it. However, in this case study, we will be using simple strings, such as “001”, to identify a property.
Owner: This is the owner of the property. 
Price: This is the price of the property.
Status: Status can take only two values: ‘registered’ and ‘onSale’. When the status of the property is set to ‘registered’, it is not listed for sale. However, when the status of the property is set to ‘onSale’, then it is put on sale by its owner.
In addition to the details above, the name and Aadhar Number of the user should also be passed as input parameters. The ‘Owner’ attribute should store the composite key of the owner of this property. 
The request gets registered on the ledger only after validating whether the details of the property’s owner are registered on the property-registration-network.
The transaction will return the Request object.
 

approvePropertyRegistration

 

Initiator: It will be the registrar.
Output: A ‘Property’ asset on the ledger will be the output. 
Use case: This function is used by the registrar to create a new ‘Property’ asset on the network after performing certain manual checks on the request received for property registration.


Flow 

As input, this transaction takes the property ID of the property for which the request was raised.
The Request asset corresponding to the property ID is fetched from the ledger. The request contains several details about the property.
These details are then used to create a new property asset on the ledger. This property is then stored on the ledger in the form of key–value pairs. The property ID along with appropriate namespace is used to create the composite key for this asset.
 

viewProperty

 

Initiator: It will be either the user or registrar.
Use case: This function should be defined in order to view the current state of any property registered on the ledger.


updateProperty

 

Initiator: A registered user who has their property registered on the ledger will be the initiator. 
Use case: This function is invoked in order to change the status of a property. 

 

Flow 

This function takes property ID, Name, Aadhar Number and status as input parameters.
First, it is ensured that the user invoking the function is the owner of the property.
The status of the property is then updated.
The updated property is then stored back on the ledger.
 

purchaseProperty

 

Initiator: A user registered on the network will be the initiator. 
Use case: In this transaction, the properties listed for sale can be purchased by a user registered on the network.


Flow

As input, the function takes the property ID of the property listed for sale, along with the name and Aadhar Number of the buyer.
It checks the status of the property to verify whether it is listed for sale or not.
It checks whether the initiator of the transaction has a sufficient account balance.
After all the validations, the owner of the property is updated.
An amount equal to the cost of the property gets deducted from the buyer’s account and gets added to its seller’s account.
The status and owner of the Property are then updated.  The owner becomes the buyer of the property and the status of the property is changed to ‘registered’.
Important Note
The ‘regnet’ chaincode should contain two separate smart contracts: One for Users and the other for Registrar. 
All the functions that can be initiated by the registrar, for example, ‘approvePropertyRegistration’, have to be included in the smart contract defined for the registrar.
Similarly, all the functions that can be initiated by the users have to be included in the smart contract defined for the users.
The functions that can be initiated by both the registrar and the users, for example, ‘viewProperty’, have to be included in both the smart contracts.
