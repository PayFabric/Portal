# Fraud Service
As EVO gateway service provider, PayFabric is able to provide merchants the ability to mitigate fraud risks with eCommerce transactions.

PayFabric supports a Merchant level configuration/feature flag that requires merchant contact PayFabric support to enable the Fraud integration. Once enabled at the Merchant level, they will have the ability to disable RiskShield on a per-device level. By default, ALL new created PayFabric devices will be enabled once enabled at the Merchant level.

PayFabric will have some more additional validation with below rules when processing transaction while merchant enables Fraud Service. The related fields info, please refer to the [Object](https://github.com/PayFabric/APIs/blob/R20/PayFabric/Sections/Objects.md) for details.
* Invalid formats provided – Transaction will fail for field validation error.
* Required fields missing – Transaction will fail for field validation error 
* Field Maximum Length Exceed – Instead of failing, we will just trim the field to the maximum length before submission.  

# Transaction Response
The transactions submitted for Fraud check will return three more fields, ExoneratingText, IncriminatingText and FraudScore.
And Transaction may failed because of the Fraud check, Transaction status for this transaction is 'FraudReject' with message 'Unable to process the transaction. Rejected due to fraud.'
