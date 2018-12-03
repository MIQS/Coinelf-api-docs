# Wallets

* [List Coin Wallets](#wallets)
* [Get Wallet Details](#walletDetails)
* [List Wallet Transfers](#walletTansfers)
* [Get Wallet Transfer Details](#walletTransferDetails)
* [Create Wallet Address](#createAddress)
* [Get Wallet Address](#getAddress)
* [Create Transfer Request](#createTransferRequest)
* [Get Transfer Request](#transferRequest)
* [Get Wallet Pending Approvals](#walletPendingApprovals)


<a name="wallets" id="wallets"> </a>
---
## List Coin Wallets

    GET /:coin/wallets
    
Returns an array of Wallet objects.

### Wallet Body Fields

Please refer to [Wallet](#wallet) object


<a name="walletDetails" id="walletDetails"> </a>
---
## Get Wallet Details

    GET /:coin/wallets/:walletId
    
Returns Wallet object.

### Wallet Object Fields

<a name="wallet" id="wallet"> </a>

Name             | Type(value)                     | Mandatory   | Description
-----------------| --------------------------------|-------------|-----------------------
walletId         | String                          | M           | Wallet id
label            | String                          | M           | Wallet label
coin             | String                          | M           | Coin id
balance          | String                          | M           | Wallet balance on blockchain
availableBalance | String                          | M           | Available balance for spending

<a name="walletTransfers" id="walletTransfers"> </a>
---
## Get Wallet Transfers

    GET /:coin/wallet/:walletId/transfers
    
Returns an array of wallet Transfer objects.

### Wallet Transfer Body Fields

Please refer to [Transfer](#transfer) object

<a name="walletTransferDetails" id="walletTransferDetails"> </a>
---
## Get Wallet Transfer Details

    GET /:coin/wallet/:walletId/transfers/:transferId

Returns wallet Transfer object

<a name="transfer" id="transfer"> </a>
### Transfer Object Fields

Name             | Type(value)                     | Mandatory   | Description
-----------------| --------------------------------|-------------|-----------------------
transferId       | String                          | M           | Transfer id
coin             | String                          | M           | Coin id
walletId         | String                          | M           | Wallet id
txid             | String                          | M           | Txid on blockchain
createdTime      | Long                            | M           | Time the transfer was created
lastModifiedTime | Long                            | M           | Time the transfer was last updated
confirmations    | Integer                         | M           | Number of confirmations
transferState    | Enum                            | M           | Please refer to transferState in enums file
confirmedTime    | Long                            | M           | Time the transfer was confirmed

<a name="createAddress" id="createAddress"> </a>
---
## Create Wallet Address

    POST /:coin/wallets/:walletId/addresses
    
Returns Address object.

### Address Body Fields

Please refer to [Address](#address) object
    
<a name="getAddress" id="getAddress"> </a>
---
## Get Wallet Address

    GET /:coin/wallets/:walletId/addresses/:address

Returns Address object.
<a name="getAddress" id="getAddress"> </a>

### Address Object Fields

Name             | Type(value)                     | Mandatory   | Description
-----------------| --------------------------------|-------------|-----------------------
address          | String                          | M           | Coin address
coin             | String                          | M           | Coin id
walletId         | String                          | M           | Wallet id
createdTime      | Long                            | M           | Time the address was created

<a name="createCoinTransferRequest" id="createCoinTransferRequest"> </a>
---
## Create Transfer Request

    PUT /:coin/wallets/:walletId/transferRequests
    
### Request Parameters

Name             | Type(value)                     | Mandatory   | Description
-----------------| --------------------------------|-------------|-----------------------
walletPassPhrase | String                          | M           | Wallet pass phrase
amount           | DoubleString                    | M           | The amount to be sent
toAddress        | String                          | M           | The address to send to
comment          | String                          | O           | Notes for the transfer

### Transfer Request Body Fields

Please refer to [TransferRequest](#transferRequest) object

<a name="transferRequest" id="transferRequest"> </a>
---
## Get Transfer Request

    GET /:coin/wallets/:walletId/transferRequests/:transferRequestId

Returns Transfer Request Object

<a name="transferRequest" id="transferRequest"> </a>

### Transfer Request Fields
 
Name               | Type(value)                     | Mandatory   | Description
-------------------| --------------------------------|-------------|-----------------------
transferRequestId  | String                          | M           | Transfer request id
coin               | String                          | M           | Coin Id
walletId           | String                          | M           | Wallet Id
toAddress          | String                          | M           | Send to address
amount             | DoubleString                    | M           | The amount to be sent
comment            | String                          | O           | Notes for the transfer
transferState      | Enum                            | M           | Please refer to transferState in enums
approvalsRequired  | Integer                         | M           | Number of approvals required
createdTime        | Long                            | M           | Created time
createdBy          | String                          | M           | User id that is used to create the transfer request
apiKey             | String                          | O           | Exists if the request is sent through api
transferId         | String                          | O           | Transfer id
txid               | String                          | O           | Txid on blockchain

<a name="walletPendingApprovals" id="walletPendingApprovals"> </a>
---
## List Wallet Pending Approvals

    GET /:coin/wallets/:walletId/transferRequests?transferState=PENDING_APPROVAL
    
Returns an array of Transfer Request Objects with transfer state of PENDING_APPROVAL

### Pending Approval Transfer Request Object Fields

Please refer to [TransferRequest](#transferRequest) object




    








