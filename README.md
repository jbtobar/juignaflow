# juignaflow

---

## CreditClub

Idea: funds pooled from member recurring deposits - members receive loan/credit from pool.

---

## CreditClub v0.0.1

Idea: funds pooled from member recurring deposits - members receive loan/credit from pool.

### Architecture

1. WebApp and/or Mobile UI for Administrator
  - to facilitate administrator actions

2. Mobile App UI on MAIA for users
 - to allow users to interact with smart contract and view transaction history

3. Smart Contract on Ethereum blockchain
 - handles all payment logic, allows users to join club, make payments, receive credit requests, make credit payouts, etc.


### Function Specs

1. [x] Any user can join the club by clicking JoinNow button
2. [x] By joining the club the user is part of the members list
3. [x] The user can make an X payment every certain amount of time by clicking makePayment button
4. [x] The payment is stored on CreditClub smart contract
5. [x] The user can view their past contributions
6. [x] If the user is in 'good standing' - meaning they have met a Z amount of payments - they can make a credit request by inputing an amount and clicking on makeRequest button
7. [x] The credit request - which contains amount, beneficiary, and whether it had been paid out - is stored in CreditClub smart contract, in a list containing all credit requests
8. [x] The admin can click on makePayout button and next credit on the credit list is paid out - meaning the amount of the credit is sent to the beneficiary and that credit is marked as 'paidOut'. The next time the admin clicks on makePayout, the next credit request will be paid out

### Smart Contract Interface

1. `function join() public` - adds the caller to list of members
2. `function makePayment( _paymentValue )` - user calls this function to make payment of amount `_paymentValue`
3. `function requestCredit(_creditRequested)`- user calls this function to add a credit request to list of requests
4. `function payOut()` - admin calls this function to transfer the amount of the pending credit request to beneficiary and mark it as paidOut


---

### Video Demo

* [Video Demo](https://vimeo.com/317587073)


What to look for in the video:

 - user connects their bank account to be able to make ACH transfers
 - user requests a 1000 transfer and you can see the balance go from 0 to 1000
 - before clicking the 'join' button, the user cannot see a contribution list because he is not a member
 - after clicking join button, user becomes member and the screen to make contributions is displayed
 - after making contribution, you can see the amount deducted from balance and in the contributions list
 - in the middle screen you can see it displays the amount the user has deposited and the total amount in the pool
 - the user requests a credit and the credit request is listed with 'false' next to it because it hasnt been approved
 - [ not in video but admin approval comes via webapp ]
 - after admin approval the list shows the credit request with 'true' showing the request was approved
 - back in the initial screen the balance has been increased because the user received the transfer requested


Note:
  - with the exception of the bank transfer which was simulated, all other transactions are real blockchain transactions with real amounts on a private blockchain.
