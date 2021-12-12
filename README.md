# Yearn V2 Affiliate Tracker

This contract is an accounting contract for tracking yearn deposits from affilaites. It is non-custodial and only works with vaults endorsed by v2.registry.ychad.eth

To work out how much traffic an affiliate has generated we compare the balance stored in the accounting contract with the yvault tokens in their wallet.

Example:
A user deposits 10,000 DAI to the yvDAI vault through this contract specifying affiliate A. They get 9,000 yvdai tokens back. At this point affilate A's balance from the user is 9,000 yvDAI. The minimum of the 9,000 in the accounting and the 9,000 in their balance.

If the user now withdraws 5,000 yvDAI the balance they have left is 4,000 yvDAI. 
At this point affilate A's balance from the user is 4,000 yvDAI. The minimum of the 9,000 in the accounting and the 4,000 in their balance.

A second user deposits 10,000 DAI to the yvDAI vault through this contract specifying affiliate A. They get 9,000 yvdai tokens back but have already got 10,000 yvDAI from a previous, non-affiliated deposit.  At this point affilate A's balance from the user is 9,000 yvDAI. The minimum of the 9,000 in the accounting and the 19,000 in their balance.