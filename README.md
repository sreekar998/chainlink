# Chainlink

Add chainlink to your testnet. 
Get some faucet.
Connect the account to remix
Deploy your contract
Transfer some link to the contract.
Check your functionalities


Oracle Contract


Oracle contracts are owned by oracle node operators, which run alongside off-chain oracle nodes.

Request
The client contract that initiates this cycle must create a request with:

the oracle address
the job ID, so the oracle know what tasks to perform
the callback function, which the oracle will send the response to.
To learn about how to find oracles to suit your needs, see Find Existing Jobs.

Oracle contracts are responsible for handling on-chain requests made through the LINK token, by implementing onTokenTransfer as a LinkTokenReceiver. Upon execution of this function, the oracle contract emits an OracleRequest event containing information about the request. This event is crucial, as it is monitored by the off-chain oracle node which acts upon it.

Fulfillment
For fulfillment, the oracle contract has a fulfillOracleRequest function which is used by the node to fulfill a request once it has the result of the job. This function returns the result to the ChainlinkClient using the callback function defined in the original request.
