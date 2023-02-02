Simple Marketplace Sample Application for Azure Blockchain Workbench
====================================================================

Overview 
---------

The Simple Marketplace application expresses a workflow for a simple transaction
between an owner and a buyer in a marketplace.  The state transition diagram
below shows the interactions among the states in this workflow. 

Application Roles 
------------------
| Name                   | Description                                       |
|------------------------|---------------------------------------------------|
|Owner |A person who wants to sell on the marketplace. |
|Buyer |A person who wants to buy from the marketplace. |

States 
-------

| Name                   | Description                                       |
|------------------------|---------------------------------------------------|
|ItemAvailable |Indicates that an owner has made the item they want to sell available in the marketplace. 
|OfferPlaced |Indicates that a seller has made an offer to buy the item listed by an owner. 
|Accepted |Indicates that the owner has accepted the buyer's offer for the item. 

Workflow Details
----------------

![workflow details for application](media/a98d6da0441c39cf0e2d82b2f4faaff3.png)

An instance of the Simple Marketplace application's workflow starts in the
ItemAvailable state when an Owner makes an item available for sale by specifying
its description and price.  A buyer can then make an offer by specifying their
price for the item.  This action causes the state to change from ItemAvailable
to OfferPlaced.  Now, if the owner agrees to the buyer's offer, then owner calls
the function to accept an offer, and the workflow reaches a successful
conclusion state denoted by the Accepted state.  If the owner, however, is not
satisfied with the offer, then the owner can call the function to reject the
offer.  On rejection, the state changes to ItemAvailable indicating that the
item is still up for sale.  The transitions between the ItemAvailable and the
OfferPlaced states can continue until the owner is satisfied with the offer
made. 

A happy path shown in the transition diagram traces an owner making an item
available, a buyer making an offer, and the owner accepting the offer. 

 
 
Application Files
-----------------

[SimpleMarketplace.json](./ethereum/SimpleMarketplace.json)

[SimpleMarketplace.sol](./ethereum/SimpleMarketplace.sol)
