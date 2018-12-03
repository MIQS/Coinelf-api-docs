# Pending Approvals

* [Get Pending Approval Transfer Requests](#pendingApprovals)
* [Approve Pending Approval Transfer Request](#approve)
* [Reject Pending Approval Transfer Request](#reject)

<a name="pendingApprovals" id="pendingApprovals"> </a>

## Get Pending Approval Transfer Requests

    GET /pendingApprovals
    
Returns all the transfer requests that are subject for approval by the user.

### Transfer Request Object fields

Please refer to [Transfer Request](wallets.md#transferRequest) Object


<a name="approve" id="approve"> </a>

## Approve Pending Approval

    POST /pendingApprovals/:transferRequestId/approve

### Transfer Request Object Response with Updated Transfer State

Please refer to [Transfer Request](wallets.md#transferRequest) Object

<a name="reject" id="reject"> </a>

## Reject Pending Approval Transfer Request

    POST /pendingApprovals/:transferRequestId/reject

### Transfer Request Object Response with Updated Transfer State

Please refer to [Transfer Request](wallets.md#transferRequest) Object



