To configure transaction-related settings. Please see the detailed description for each corresponding section below. 

# PayFabric Settings

Navigate to Settings > DEV Central > PayFabric Settings.

## Design Mode

PayFabric Virtual Terminal have introduced two UI Modes for virtual terminal , `Legacy Design` and `Modern Design`

* `Legacy Design`: Maintain the existing user interface and experience for virtual terminal where user can mimic the hosted API calls for PayFabric and also review the custom’s device theme directly on PayFabric portal. 
![Legacy VT_General](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/Legacy%20VT_General.png)
![TrxOptionR20](./Sections/Screenshots/TrxOptionR20.png)


* `Modern Design`: Introduce a new user friendly design for Virtual Terminal to allow merchant to process transactions against PayFabric web portal via web entry and/or terminal entry. 
![ModernTrxOptionR13](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/ModernTrxOptionR13.png)
![Modern VT_PaymentDetails](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/Modern%20VT_FormSettings_PaymentDetails.png)
![Modern VT_TransactionDetails](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/Modern%20VT_FormSettings_TransactionDetails.png)
![Modern VT_Addresses](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/Modern%20VT_FormSettings_Address.png)
![Modern VT_ItemDetails](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/Modern%20VT_FormSettings_ItemDetails.png)

## Device Name
The drop-down consists all existing devices associated with the PayFabric account. PayFabric enable user to configure different transaction settings for every device. Choose the corresponding device from the drop-down list, then begin making changes to the settings.

## Form Settings
With `Modern Design` mode for Virtual Terminal, the defined field(s) that will be Hide/Optional/Required/Data Level Qualification on `Process a Transaction` page by tick or untick the field name from the list, to control the additional values for transaction processing.
|Field                          |Description  | 
|:------------------------------|:-------------| 
| Hide                          | Upon selected, this option will hide this field to user on modern VT.  |
| Optional                      | Upon selected, this option will show but optional this field to user on modern VT. |
| Required                      | Upon selected, this option will show and require this field to user on modern VT. |
| Data Level Qualification      | Upon selected, this option will dynamically display this field is only required to be populated if card level is purchasing/corporate/business card.|

## Accept Card Types
Define the supported card type(s) by tick or untick the card type from the list. 

## Transaction Options
These are settings relate to process a payment transaction. 

|Field                          |Description  | 
|:------------------------------|:-------------| 
|Fail On Zip Mismatch| Payment gateway verifies the zip code. By checking this option, By checking this option, PayFabric will automatically void any approved payment if the zip verification failed by the gateway/processor. this setting will be set to false if it is enabled for _Verify_ transaction. |
| Lock Transaction Amount        | If this option is check marked, system will prevent user from changing the transaction amount on PayFabric’s hosted payment page. |
| Lock Gateway Account           | If this option is check marked, system will prevent user from changing the gateway account profile on PayFabric’s hosted payment page. |
| Fail On CVV2 Mismatch          | Payment gateway verifies the CSC (Card Security Code). By checking this option, PayFabric will automatically void any approved payment if the CSC verification failed by the gateway/processor. this setting will be set to false if it is enabled for _Verify_ transaction. |
| Shipping Address Required | By default, shipping address is not required as processing transactions. Checking this option to enable this logic. |
| Partial Capture | This option is for capturing a pre-authorized transaction. By default (uncheck), the capturing amount must be same with pre-authorization. By checking this option, merchant allow the capturing amount less/more than the original pre-authorization transaction.|
| Lock Transaction Type| If this option is check marked, system will prevent user from changing the transaction type on PayFabric’s hosted payment page.|
|Fail On Address Mismatch | Payment gateway verifies the billing address. By checking this option, PayFabric will automatically void any approved payment if the address verification failed by the gateway/processor. this setting will be set to false if it is enabled for _Verify_ transaction. |
|Lock Currency| If this option is check marked, system will prevent user from changing the currency type on PayFabric’s hosted payment page.|
|Popup Message|If this option is check marked, system will display response or error message to end-user using popup message instead of inline within PayFabric’s hosted payment page and hosted wallet page.|
|IP Address Validation for Security Token|If enabled, PayFabric will validate the security token’s IP address. If the IP address associated with the security token at the time of token creation does not match the security token at the time of token consumption, PayFabric will return the ‘failed authentication’ error during API calls. If disabled, PayFabric will not validate the security’s token IP address during API calls. By default, this setting is enabled.|
|Partial Refund|If enabled, PayFabric will allow to process partial referenced credit/refund transaction for their customers from `Manage Transactions`. Note: This options is only available for Virtual Terminal. |
|Return Legacy Transaction Types |If enabled, when retrieving transactions through the use of the API, the transaction types returned will be those of the legacy Book, Ship and Credit instead of the new Authorization, Capture and Refund.|
|Credit Card Validation Required |If enabled, Payfabric will validate credit card before storing for later use.|
|Enable Bin Range Validation |If enabled, PayFabric will do BIN Range validation on all credit card data to determine the card type. If card level is a Non-Commercial card, PayFabric will exclude L2/L3 data when submitting to gateway/processing.|
|Enabled For Fraud|If enabled, transction processed with current device will be submitted to RiskShield.|
|Maximum Limit for Sale Transaction(Credit)|Specify a maximum amount for Sale/Authorization/Force transaction when process transaction with credit card.|
|Maximum Limit for Sale Transaction(eCheck)|Specify a maximum amount for Sale transaction when process transaction with eCheck.|
|Maximum Limit for Refund Transaction(Credit)|Specify a maximum amount for refund transaction when process transaction with credit card.|
|Maximum Limit for Refund Transaction(eCheck)|Specify a maximum amount for refund transaction when process transaction with eCheck.|
|Enable Tip Amount |If enabled, will show Tip - Option 1, Tip - Option 2 and Tip - Option 3 on the setting page; MRHPP will displays three buttons according to the rates of these Tip options. With that, "No Tip" and "Other" buttons will be added as well, which allow users to select tip rate or enter tip amount. <b>Note:</b> This setting is only applicable for created devices rather than Virtual Terminal.|
|Tip - Option 1|This option will be available after Enable Tip Amount, it allows 2 decimal places.|
|Tip - Option 2|This option will be available after Enable Tip Amount, it allows 2 decimal places. The value must be greater than the value entered in Tip - Option 1.|
|Tip - Option 3|This option will be available after Enable Tip Amount, it allows 2 decimal places. The value must be greater than the value entered in Tip - Option 2.|


## General Settings
|Field                          |Description  | 
|:------------------------------|:-------------| 
| Transaction Key Prefix          | User defined prefix for PayFabric transaction key. |
| PostURL       | PayFabric will post transaction response data (Non-sensitive fields) to this URL once this transaction is processed (successful or failed). **Note:** for 3DS transctions, you will get 2 webhooks. One that is 3DS Challenge status and one that is the final transaction response. |
| Maximum History Cards |Limit the number of wallet entries loaded on PayFabric hosted pages by specify the number of saved card. The default value is 10.|
| Return URL|A URL address that PayFabric can redirect to once a transaction is processed. The response fields will be encoded and attached into query string.|
| Maximum Shipping Address| Limit the number of shipping address(s) loaded on PayFabric hosted payment page by specify the number of saved card. The default value is 10. Note: this options is only available for `Legacy Design`|
| Batch Number Prefix|User defined prefix for batch number. Note: this options is only available for `Legacy Design`|
|Enable Security Token|For APIs and Hosted Pages: this is the default option where security token will be allow to use as the authentication method in both hosted pages and APIs. For Hosted Pages Only: with this option, security token will ONLY be allow to use as the authentication method in hosted pages. The API service response will fail authentication if any API calls was authenticated using security token.|
| Default Transaction Type|PayFabric offers the ability for merchant to specify the default transaction type on PayFabric’s Virtual Terminal.. Note: this options is only available for `Modern Design`|
| Credit card validation gateway profile| This is a sub setting for ``Credit Card Validation Required``, now support validate credit card from EVO,CybersourceSOAP,Paymentech|
| Authorization Type | Default indicator if API or Hosted page does not send in Authorization Type's option. |
| Transaction Schedule | Default indicator if API or Hosted page does not send in Transaction Schedule's option. |
| Transaction Initiation | Default indicator if API or Hosted page does not send in Transaction Initiation's option.  |

## Unit Of Measure Mapping for Payeezy (First Data GGE4)
For merchant using Payeezy gateway, item’s unit of measure needs to be mapped to the values supported by the gateway. See referenced URL for valid UOM from First Data. 

![Payeezy UOM](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/UOMMapping.png)

Reference: https://support.payeezy.com/hc/en-us/articles/203732159-Units-of-Measure

# Default Gateway Settings

Navigate to Settings > Gateway Account Configuration > Default Gateway Settings.

With `Modern Design` mode for Virtual Terminal, PayFabric provides merchant the ability to specify default gateway profile based on currency types so their internal user does not need to select a gateway profile at the time of processing a transaction. This functionality is supported through PayFabric API calls for all PayFabric apps/devices.

![DefaultGatewaySetings](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/DefaultGatewaySetings.png)

Each Device is allowed to setup a Credit card and a eCheck gateway profile against currency, prior to setup default gateway, gateway profile must be created from `Settings` > `Gateway Account Profiles`. `Virtual Terminal` option of Device Name is only available when Design Mode is `Modern Design` under `PayFabric Settings`.

# Discretionary Data

Navigate to Settings > Discretionary Data.

With `Modern Design` mode for Virtual Terminal, merchant will have the ability to create their own custom field to associate additional data for each transaction with PayFabric. Discretionary data will only reside with PayFabric and will not be pass on to payment gateway or payment processor. 

# Products

Navigate to Settings > Products.

With `Modern Design` mode for Virtual Terminal, PayFabric provide the ability to manage the products. The uploaded products can be added to the transactions when processing transaction.
