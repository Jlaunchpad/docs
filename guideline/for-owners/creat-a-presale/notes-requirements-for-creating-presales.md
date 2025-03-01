# Notes: Requirements for creating presales

## 1. Conditions for creating a new presale

* You must have enough funds to cover the required system fees
* The raise token must be on the whitelist
* Selecting a Dex Router is mandatory
* End date cannot be earlier than current block timestamp

**TOKEN WHITELIST**

| Token name | Type   |
| ---------- | ------ |
| BNB        | Native |
| TCAPY      | BEP20  |
| ZUKI       | BEP20  |
| JLP        | BEP20  |

**DEX ROUTER LIST**

| Name         | ID      |
| ------------ | ------- |
| PANCAKE SWAP | 0x12344 |

## 2. Conditions to initiate a presale

* The end date can't be earlier than the current block timestamp (the presale start date < the current block timestamp is NOT allowed)
* The end date can't be earlier than the start date (the presale end date < the presale start date is NOT allowed)
* The presale rate must be greater than zero (the presale rate = 0 is NOT allowed)
* The presale fee must be greater than zero (the presale fee < 0 is NOT allowed)
* The affiliate percent can't be less than zero (the affiliate percent < 0 is NOT allowed)
* The Hardcap must be greater than 4x of Softcap and Softcap must be greater than zero
* The liquidity listing rate must be greater than zero
* The liquidity percent must be in between 51 and 100
* The liquidity lock time must be greater than zero
* The liquidity DEX router must be selected

## 3. Presale status

| TITLE     | CODE | NOTES                                                                                                                                                                   | ACTION BUTTON                                                                           |
| --------- | ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| QUED      | 0    | Awaiting start block                                                                                                                                                    | Cancel (Owner)                                                                          |
| ACTIVE    | 1    | <p>Deposit enabled - Now in presale </p><p>the current block timestamp >= the presale start time</p><p>AND the current block timestamp &#x3C;= the presale end time</p> | <p>Buy (Investor),</p><p>Cancel (Owner),</p><p>Emergency Withdraw (Owner, Investor)</p> |
| SUCCESS   | 2    | <p>Presale ended with reaching the Softcap</p><p>the current block timestamp > the presale end time </p><p>AND the raised amount >= the Softcap</p>                     | <p>Claim Presale Token (Investor),</p><p>Finalize (Owner)</p>                           |
| WONDERFUL | 2    | <p>Reached to the Hardcap</p><p>the raised amount >= the Hardcap</p>                                                                                                    | <p>Claim Presale Token (Investor),</p><p>Finalize (Owner)</p>                           |
| FAILURE   | 3    | <p>Failure</p><p>the current block timestamp > the presale end time </p><p>AND the raised amount &#x3C; the Softcap</p>                                                 | <p>Claim Contribution (Investor),</p><p>Withdraw Presale Token (Owner)</p>              |
| CANCELLED | 4    | Cancelled                                                                                                                                                               | <p>Claim Contribution (Investor),</p><p>Withdraw Presale Token (Owner)</p>              |

\


## 4. Conditions for Investor/Owner to Contribute (buy presale)

* The presale status must be 1
* The presale amount must be greater than zero
* If whitelist is required, user must be in the whitelist
* The amount a user purchases must be greater than or equal to the minimum amount and less than or equal to the maximum amount
* Total raise must be less than the current contract balance
* The amount of native tokens must be sufficient

## 5. Conditions for Investor to Claim

* The presale status must be 2 (the presale status must be different from 0 and 1
* Claim Contribution: the contribution of investor must be greater than zero (the presale status must be 3 or 4)Claim Presale Token: (the presale status must be 2, and  the current block timestamp must be greater or equal to sum of presale end times and lock time)

## 6. Conditions for Investor to Emergency Withdraw Contributions

* The presale status must be 1
* The presale must NOT be Finalized
* The presale status must NOT be 3
* The emergency withdraw fee is valid

## 7. Conditions for Owner to Cancel Pool

* The presale status must be 1
* The presale must NOT be Finalized
* The presale must NOT be Canceled
* The presale status must NOT be 2

## 8. Conditions for Investor to Withdraw Presale Token

* The presale status must be 3 or 4
* The contribution must be greater than zero

## 9. Conditions for Owner to Finalize

* The presale must NOT be Finalized
* The presale status must be 2

## 10. Conditions for Owner/ Investor to Claim Referral Rewards

* The affiliate percent must be greater than zero
* The affiliate percent must be less than or equal to 10 percent and must be an integer
* The presale must be Finalized

**Related Wallet**&#x20;

Dead Wallet Address: 0x000000000000000000000000000000000000dEaD

\
