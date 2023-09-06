# Gateway Account Profiles

PayFabric has been named as a proprietary US gateway of EVO Payments to offer companies and software providers a streamlined payment service platform for digital payment acceptance and accounts receivables automation. EVO Payments (NASDAQ: EVOP) is among the largest fully integrated merchant acquirers and payment processors in the world. With PayFabric, EVO provides a one-stop-shop payment experience to merchants. PayFabric helps merchants accept electronic payments directly within their business applications and helps lower processing rates through qualified level 2 and 3 data submission.

Merchant needs to setup gateway profile on PayFabric and associate to their merchant processing account information. Follow the field description below to configure your PayFabric gateway profile(s) for credit card and/or ACH processing needs. 

## EVO

| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|EVO|
|Processor|Evo US, Evo eService and Evo Gift, Evo eService processor supports 3DS, Evo Gift processor supports Gift Card.  |
|Card Class|Credit for Evo US and Evo eService processors, GiftCard for Evo Gift processor.|
| MerchantProfile             | This is the Merchant ID for the API service obtained from EVO |
| ServiceId             | This is the Service ID for the API service obtained from EVO |
| SurchargeRate             | This rate provide merchant the ability to support surcharge, this rate is between 0.00% to 4.00%, once merchant configure this rate and when process transaction with a credit card*, PayFabric will auto calculate the surcharge amount (original transaction amount * Surcharge Rate) and include the surcharge amount into the final transaction amount. Possible values are between 0.00 and 4.00. |

Note: PayFabric uses `Card Validation Type` to indicate the used card is `Credit`, `Debit` or `PrePay`.

## EVOACH

| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|EVOACH|
|Processor|EVO ACH|
|Card Class|ECheck|
| Server.Url           | For Test Transactions: https://achcert.goevo.com |
|| For Live Transactions: https://ach.goevo.com |
| MerchantID             |Only B2B partner has ability to configure this field, so if merchants want to use EVOACH gateway, please contact your partner.|

Note: EVOACH gateway supports Sale, Void and Refund transaction types.

## Global Payments
| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|Global Payments|
|Processor|Portico  |
|Card Class|Credit and ECheck.|
| PrivateAPIKey             | This is the PrivateAPIKey for the API service obtained from Globa Payments. |
| MerchantID             | This is the Merchant ID for the API service obtained from Globa Payments. |
| IgnoreDuplicate             | This is a flag for accepting duplicate transactions or not. If true, Global Payments accepts the duplicate transactions; If false, Global Payments will fail the duplicate transaction. |
| SurchargeRate             | This rate provides merchants the ability to support surcharge, this rate is between 0.00% to 4.00%, once the merchant configures this rate and when processing a transaction with a credit card*, PayFabric will auto calculate the surcharge amount (original transaction amount * Surcharge Rate) and include the surcharge amount into the final transaction amount. Possible values are between 0.00 and 4.00. |

# Batch Close
Navigate to Settings > Gateway Account Configuration > Click the Batch Close button on an existing gateway profile.

PayFabric provide merchant the ability to specify their automatic batch close time at the gateway profile level based on hour, minute, am/pm with the interval of 30 minutes. By default, the batch close time is 8pm PT. When automatic batch close occurs, PayFabric will gather all transactions that were processed from the last 24-hours from the cut-off time and will send it through to EVO processing backend for batch capture. 

![BatchClose](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/BatchClose.png)

# Default Gateway Profile
Navigate to Settings->Gateway Account Configuration->Default Gateway Settings 

PayFabric provide merchant the ability to specify the default gateway for specific Device and specific currency, once configured, then if no gateway passed in when creating/processing transaction, PF will use the default one.

![DefaultGateways](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/Screenshots/DefaultGateway.png)



