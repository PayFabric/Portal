# Gateway Account Profiles
PayFabric support multiple and growing payment gateways. Each gateway will have their own setup information , therefore PayFabric support these setup with a flexible way. As you are switching the "Connector" field on the Gateway Account Profiles page, the "Gateway Fields" section will be refreshed in accordance with your selection.

And currently, PayFabric support below gateways.
* [Payflowpro (Paypal)](#payflowpro-paypal)
* [Payeezy (First Data GGe4)](#payeezy-first-data-gge4)
* [USAePaySOAP](#usaepaysoap)
* [Authorize.Net](#authorizenet)
* [CybersourceSOAP](#cybersourcesoap)
* [Cybersource](#cybersource)
* [Paymentech Orbital](#paymentech)
* [WorldPay](#worldpay)
* [Moneris (Canadian currency only)](#moneris)
* [Forte](#forte)
* [FrontStream Fundraising Pro](#frontstream-fundraising-pro)
* [EVO](#evo)
* [EziDebit](#ezidebit)
* [NMI](#nmi)

Configure the Gateway Account Profile using the following information. Fields not mentioned here are not required for the minimum configuration.

## Payflowpro (PayPal)
| Field         | Value                   | 
| ------------- |:---------------------------- | 
|Connector|PayFlowPro|
|Processor|Choose the Processor that the PayPal PayFlowPro account is connected to|
|Card Class|Choose ‘Credit’ for Credit Card Transactions|
||Choose ‘ECheck’ for eCheck Transactions|
| Server.Address| For Test Transactions: https://pilot-payflowpro.paypal.com |
|| For Live Transactions: https://payflowpro.paypal.com | 
| Partner  | This is the partner that setup the PayFlowPro account. This is the same as the ‘Partner’ field used to log into https://manager.paypal.com |
| Vendor   | This is the ‘Merchant Login’ used to identify the PayFlowPro account. This is the same as the ‘Merchant Login’ used to log into https://manager.paypal.com|      |
| UserID   | The PayFlowPro account may utilize a User when logging into https://manager.paypal.com. If no ‘User’ is used when logging into the PayPal Manager, fill in this field with the same value as the ‘Vendor’ field.     |
| Password | This is the password associated with the ‘User’ or ‘Merchant Login’ to log into https://manager.paypal.com.      |

## Payeezy (First Data GGe4)

To obtain most of this information, log into the gateway account, browse to ‘Terminals’ and select the desired Terminal associated to the desired merchant account.

| Field         | Value                   | 
| ------------- |:---------------------------- |
|Connector|FirstDataGGe4|
|Processor|FirstDataGGe4|
|Card Class|Credit|
| Server.Url      | For Test Transactions: https://api.demo.globalgatewaye4.firstdata.com/transaction/v12 | 
|| For Live Transactions: https://api-alt.globalgatewaye4.firstdata.com/transaction/v12 |
| APIKeyID        | ‘Key ID’ associated to the Terminal for the Payeezy account. This value is located under the ‘API Access’ tab after selecting the terminal.   |
| HMACKey         | ‘Hmac key’ identifier associated to the Terminal for the Payeezy account. This value is generated under the ‘API Access’ tab after selecting the terminal.     |
| GatewayID       |‘Gateway ID’ associated to the Terminal for the Payeezy account. This value is located under the ‘Details’ tab after selecting the terminal.     |
| GatewayPassword | ‘Password’ associated to the Terminal for the Payeezy account. This value is generated under the ‘Details’ tab after selecting the terminal.    |

Note: Support multiple captures against one authorized transaction.

## USAePaySOAP
| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|USAePaySOAP|
|Processor|USAePay|
|Card Class|Choose ‘Credit’ for Credit Card Transactions|
||Choose ‘ECheck’ for eCheck Transactions|
|Server.Address|For Test Transactions: https://sandbox.usaepay.com/soap/gate|
|| For Live Transactions: https://secure.usaepay.com/soap/gate | 
|Server.Port|443|
|Server.APIKey|245VMXN8|
| SourceKey           | This is the Source Key that is obtained from the settings of the USAePay gateway    |
| Pin            | This is the Pin of the Source Key that is obtained from the settings of the USAePay gateway   |

Note: Support multiple captures against one authorized transaction.

## Authorize.Net
| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|Authorize.Net|
|Processor|Authorize.Net|
|Card Class|Choose ‘Credit Card’ for Credit Card Transactions|
||Choose ‘ECheck’ for eCheck Transactions|
| Server.Address      | For Test Transactions: https://test.authorize.net/gateway/transact.dll |
|| For Live Transactions: https://secure2.authorize.net/gateway/transact.dll | 
| Server.Port         | 443 |
| LoginID             | This is the login id used for the Authorize.net account  |
| TransactionKey      | This key can be obtained from the Authorize.Net Gateway. Contact the Authorize.net gateway provider for more details.      |

Note: Support multiple captures against one authorized transaction.

## CybersourceSOAP

| Field                | Value                   | 
| -------------------- |:---------------------------- |
|Connector|CybersourceSOAP|
|Processor|Choose the Processor that the Cybersource account is connected to|
|Card Class|Choose ‘Credit’ for Credit Card Transactions|
||Choose ‘ECheck’ for eCheck Transactions|
| Server.Address       | For Test Transactions: https://ics2wstesta.ic3.com/commerce/1.x/transactionProcessor |
|| For Live Transactions: https://ics2wsa.ic3.com/commerce/1.x/transactionProcessor/ | 
| MerchantID           | This is the merchant ID for the Cybersource account |
| TRANSACTION_Key      | Generated from CyberSource Business Center > Account Management > Transaction Security Keys > Security Keys for the SOAP Toolkit API |
| CurrencyCode         | Transaction currency, e.g. 'USD' |

## Cybersource

| Field                | Value                   | 
| -------------------- |:---------------------------- |
|Connector|Cybersource|
|Processor|Choose the Processor that the Cybersource account is connected to|
|Card Class|Credit|
| Server.Address       | For Test Transactions: ics2test.ic3.com | 
|| For Live Transactions: ics2.ic3.com|
| MerchantID           | This is the merchant ID for the Cybersource account |
| CurrencyCode         | Transaction currency, e.g. 'USD' for US Dollar |

To use the Cybersource Gateway, it is necessary to obtain the secure CyberSource Keys from the Cybersource eCert Application. Contact the CyberSource partner for more information on obtaining these keys. Upload the keys on PayFabric like below:

![Cybersource](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/GatewayCyberSource.png)

## Paymentech Orbital

| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|Paymentech|
|Processor|Paymentech|
|Card Class|Choose ‘Credit’ for Credit Card Transactions|
||Choose ‘ECheck’ for eCheck Transactions|
| Server.Address       | For Test Transactions: https://orbitalvar1.chasepaymentech.com/authorize |
|| For Live Transactions: https://orbital1.chasepaymentech.com/authorize | 
|Port|443|
| MerchantID           | This is the Merchant identifier used for the Paymentech Account|
| BIN                  | This is the typically 6 digits bin number associated with the Paymentech Account |
| TerminalID           | This is the identifier for the Terminal ID used with the Paymentech Account |
| IndustryType         | EC |
| CurrencyCode         | Transaction currency, e.g. '840' for US Dollar, '124' for Canadian Dollar |
| CurrencyExponent     | 2 |
| DropLevel2Data       | This will prevent sending Level 2 data when value is set to true or 1 |
| DropLevel3Data       | This will prevent sending Level 3 data when value is set to true or 1 |

## WorldPay

| Field                | Value                   | 
| -------------------- |:---------------------------- |
|Connector|WorldPay|
|Processor|Choose the Processor that the WorldPay account is connected to|
|Card Class|Credit|
| Server.Url           |https://trans.worldpay.us/Web/services/TransactionService |
| AcctID               | This is the Account identifier for the account     |
| SubID                | This is the Sub Identifier for the account      |
| MerchantPIN          | This is the Merchant Pin associated to the account     |

## Moneris 

| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|Moneris|
|Processor|Moneris|
|Card Class|Credit|
| Server.Address       | For Test Transactions: https://esqa.moneris.com/gateway2/servlet/MpgRequest |
|| For Live Transactions: https://www3.moneris.com/gateway2/servlet/MpgRequest | 
| Server.Port          |43924          |
| StoreID              | This is the Store identifier obtained from Moneris |
| APIToken             | This is the API Token value obtained from Moneris |

Note: For Canadian currency only.

## Forte

| Field                | Value                   | 
| -------------------- |:---------------------------- |
|Connector|Forte|
|Processor|Forte|
|Card Class|Choose ‘Credit’ for Credit Card Transactions|
||Choose ‘ECheck’ for eCheck Transactions|
| Server.Address       | For Test Transactions: https://sandbox.forte.net/api/v3 |
|| For Live Transactions: must contact Forte Technical Support at go Live. | 
| OrganizationID       | This is the organization identifier obtained from Forte|
| LocationID           | This is the location identifier obtained from Forte |
| APIAccessID          | This is the API access identifier obtained from Forte |
| APISecureKey         | This is the API secure key obtained from Forte |

## FrontStream Fundraising Pro

| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|FrontStreamFundraisingPro|
|Processor|FrontStreamFundraisingPro|
|Card Class|Credit|
| Server.Url           | For Test Transactions: https://secureuat.artezhq.com/api/ |
|| For Live Transactions: https://secure.e2rm.com/api/Donations | 
| UserName             | This is the user name for the API service obtained from FrontStream Fundraising Pro|
| Password             | This is the password for the user name obtained from FrontStream Fundraising Pro |
| EventID              | This is the event identifier obtained from FrontStream Fundraising Pro |
| CurrencyID           | Transaction currency, e.g. 'USD' for US Dollar, 'CAD' for Canadian Dollar |
| OrganizationNameUDFID|This is the organization identifier obtained from FrontStream Fundraising Pro |
| CustomerIDUDFID      | This is the customer identifier obtained from FrontStream Fundraising Pro |
| InvoiceNumbersUDFID  | This is the invoice number identifier obtained from FrontStream Fundraising Pro |

## EVO

| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|EVO|
|Processor|Evo US|
|Card Class|Credit|
| MerchantProfile             | This is the Merchant ID for the API service obtained from EVO |
| ServiceId             | This is the Service ID for the API service obtained from EVO |
| SurchargeRate             | This rate provide merchant the ability to support surcharge, this rate is between 0.00% to 4.00%, once merchant configure this rate and when process transaction with credit card, PayFabric will auto calculate the surcharge amount (original transaction amount * Surcharge Rate) and include the surcharge amount into the final transaction amount. Possible values are between 0.00 and 4.00. |


## EziDebit

| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|EziDebit|
|Processor|EziDebit|
|Card Class|ECheck|
| Server.Url           | For Test Transactions: https://api.demo.ezidebit.com.au/v3-5/pci |
|| For Live Transactions: https://api.ezidebit.com.au/v3-5/pci |
| Digital Key             | This is the Digital Key for the API service obtained from EziDebit|

## NMI

| Field                | Value                   | 
| -------------------- |:---------------------------- | 
|Connector|NMIPayment|
|Processor|NMI Payment|
|Card Class|Credit|
| Server.Address           | For both Live and Test Transactions: https://secure.networkmerchants.com/api/transact.php |
| UserName             | This is the user name for the API service obtained from NMI|
| Password             | This is the password for the user name obtained from NMI |
| SecurityKey             | This is the Security Key for the API service obtained from NMI|

Note: Provide either UserName/Password or SecurityKey for creating NMI gateway profile, if both UserName/Password and SecurityKey are provided, SecurityKey will be used.

# Batch Close
Navigate to Settings > Gateway Account Configuration > Click Batch Close button on an existing gateway.

PayFabric provide merchant the ability to specify their automatic batch close time at the gateway profile level based on hour, minute, am/pm with the interval of 30 minutes. By default, the batch close time is 8pm PT. When automatic batch closes occurs, PayFabric will gather all transactions that were processed from the last 24-hours from the cut-off time and will send it through to EVO Snap for batch capture. For gateways that are non-EVO, Payfabric will not send it through to EVO Snap, PayFabric will only mimic settlement occurring at the gateway level. The timestamp used here should match with the time used at the gateway for settlement time.

![BatchClose](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/BatchClose.png)


