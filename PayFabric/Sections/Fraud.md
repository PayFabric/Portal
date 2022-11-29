# EVO Fraud
As EVO gateway service provider, PayFabric is able to provide merchants the ability to mitigate fraud risks with eCommerce transactions.  EVO has chosen Inform's RiskShield product to be its real-time fraud mitigation service.  RiskShield monitors authorization traffic, screens for fraud, and returns a fraud score. Initially EVO's implementation of RiskShield will be rules-based and score based on transaction data provided by PayFabric.

PayFabric supports a Merchant level configuration/feature flag that requires merchant contact PayFabric support to enable the Fraud integration.Once enabled at the Merchant level, they will have the ability to disable RiskShield on a per-device level.  By default, ALL new created PayFabric devices will be enabled once enabled at the Merchant level.

# Virtual Terminal
If Merchant enables Fraud check for Virtual terminal device, then transactions processed on both Legacy VT and Modern VT will submit the transaction info to RiskShield, and returns 3 additional fields in Transaction response page.



  
