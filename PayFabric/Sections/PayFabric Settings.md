To configure transaction-related settings. Please see the detailed description for each corresponding section below. 

# PayFabric Settings

Navigate to Settings > DEV Central > PayFabric Settings.

## Design Mode

PayFabric Virtual Terminal have introduced two UI Modes for virtual terminal , `Legacy Design` and `Modern Design`

* `Legacy Design`: Maintain the existing user interface and experience for virtual terminal where user can mimic the hosted API calls for PayFabric and also review the custom’s device theme directly on PayFabric portal. 
![Legacy VT_General](https://github.com/PayFabric/Portal/blob/PayFabric-Release-11-features/PayFabric/Sections/Screenshots/Legacy%20VT_General.png)
![Legacy VT_TransactionOptions](https://github.com/PayFabric/Portal/blob/PayFabric-Release-11-features/PayFabric/Sections/Screenshots/Legacy%20VT_TransactionOptions.png)


* `Modern Design`: Introduce a new user friendly design for Virtual Terminal to allow merchant to process transactions against PayFabric web portal via web entry and/or terminal entry. 
![Modern VT_TransactionOptions](https://github.com/PayFabric/Portal/blob/PayFabric-Release-11-features/PayFabric/Sections/Screenshots/Modern%20VT_TransactionOptions.png)
![Modern VT_PaymentDetails](https://github.com/PayFabric/Portal/blob/PayFabric-Release-11-features/PayFabric/Sections/Screenshots/Modern%20VT_FormSettings_PaymentDetails.png)
![Modern VT_TransactionDetails](https://github.com/PayFabric/Portal/blob/PayFabric-Release-11-features/PayFabric/Sections/Screenshots/Modern%20VT_FormSettings_TransactionDetails.png)
![Modern VT_Addresses](https://github.com/PayFabric/Portal/blob/PayFabric-Release-11-features/PayFabric/Sections/Screenshots/Modern%20VT_FormSettings_Address.png)
![Modern VT_ItemDetails](https://github.com/PayFabric/Portal/blob/PayFabric-Release-11-features/PayFabric/Sections/Screenshots/Modern%20VT_FormSettings_ItemDetails.png)

## Device Name
The drop-down consists all existing devices associated with the PayFabric account. PayFabric enable user to configure different transaction settings for every device. Choose the corresponding device from the drop-down list, then begin making changes to the settings.

## Form settings
Define the field(s) that will be Hide/Optional/Required on `Process a Transaction` page by tick or untick the field name from the list, to control the additional values for transaction processing. This setting is only for ``Modern VT``

## Accept Card Types
Define the supported card type(s) by tick or untick the card type from the list. 

## Transaction Options
These are settings relate to process a payment transaction. 

|Field                          |Description  | 
|:------------------------------|:-------------| 
|Fail On Zip Mismatch| Payment gateway verifies the zip code. By checking this option, By checking this option, PayFabric will automatically void any approved payment if the zip verification failed by the gateway/processor. |
| Lock Transaction Amount        | If this option is check marked, system will prevent user from changing the transaction amount on PayFabric’s hosted payment page. |
| Lock Gateway Account           | If this option is check marked, system will prevent user from changing the gateway account profile on PayFabric’s hosted payment page. |
| Fail On CVV2 Mismatch          | Payment gateway verifies the CSC (Card Security Code). By checking this option, PayFabric will automatically void any approved payment if the CSC verification failed by the gateway/processor. |
| Shipping Address Required | By default, shipping address is not required as processing transactions. Checking this option to enable this logic. |
| Partial Capture | This option is for capturing a pre-authorized transaction. By default (uncheck), the capturing amount must be same with pre-authorization. By checking this option, merchant allow the capturing amount less/more than the original pre-authorization transaction.|
| Lock Transaction Type| If this option is check marked, system will prevent user from changing the transaction type on PayFabric’s hosted payment page.|
|Fail On Address Mismatch | Payment gateway verifies the billing address. By checking this option, PayFabric will automatically void any approved payment if the address verification failed by the gateway/processor.|
|Lock Currency| If this option is check marked, system will prevent user from changing the currency type on PayFabric’s hosted payment page.|
|Popup Message|If this option is check marked, system will display response or error message to end-user using popup message instead of inline within PayFabric’s hosted payment page and hosted wallet page.|
|IP Address Validation for Security Token|If enabled, PayFabric will validate the security token’s IP address. If the IP address associated with the security token at the time of token creation does not match the security token at the time of token consumption, PayFabric will return the ‘failed authentication’ error during API calls. If disabled, PayFabric will not validate the security’s token IP address during API calls. By default, this setting is enabled.|
|Partial Refund|If enabled, PayFabric will allow to process partial referenced credit/refund transaction for their customers from `Manage Transactions`. Note: This options is only available for Virtual Terminal. |
|Credit Card Validation Required |If Enable, Payfabric will validate credit card before storing for later use.|
|Enable Bin Range Validation |If enabled, PayFabric will do BIN Range validation on all credit card data to determine the card type. If card type is a non-purchasing card, PayFabric will exclude L2/L3 data when submitting to gateway/processing.|


## General Settings
|Field                          |Description  | 
|:------------------------------|:-------------| 
| Transaction Key Prefix          | User defined prefix for PayFabric transaction key. |
| PostURL       | PayFabric will post transaction response data (Non-sensitive fields) to this URL once this transaction is processed (successful or failed) |
| Maximum History Cards |Limit the number of wallet entries loaded on PayFabric hosted pages by specify the number of saved card. The default value is 10.|
| Return URL|A URL address that PayFabric can redirect to once a transaction is processed. The response fields will be encoded and attached into query string.|
| Maximum Shipping Address| Limit the number of shipping address(s) loaded on PayFabric hosted payment page by specify the number of saved card. The default value is 10. Note: this options is only available for `Legacy Design`|
| Batch Number Prefix|User defined prefix for batch number. Note: this options is only available for `Legacy Design`|
|Maximum Amount Per Transaction|Specify a maximum amount for each transaction.|
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

Navigate to Settings > DEV Central > Default Gateway Settings.

With `Modern Design`, PayFabric provides merchant the ability to specify default gateway profile based on currency types so their internal user does not need to select a gateway profile at the time of processing a transaction. This functionality is supported through PayFabric API calls for all PayFabric apps/devices.

![DefaultGatewaySetings](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/DefaultGatewaySetings.png)

Each Device is allowed to setup a Credit card and a eCheck gateway profile against currency, prior to setup default gateway, gateway profile must be created from `Settings` > `Gateway Account Profiles`. `Virtual Terminal` option of Device Name is only available when Design Mode is `Modern Design` under `PayFabric Settings`.

# P2PE Decryptx Settings

Navigate to Settings > P2PE Decryptx Settings

From P2PE Bluefin Decryptx configuration page, user can configure settings specific to Bluefin Decryptx service 
![Bluefin](https://github.com/PayFabric/Portal/blob/PayFabric-Release-11-features/PayFabric/Sections/Screenshots/Bluefin.png)

# Bluefin Entry Options
| - Use Non-Encrypted key Entry - | Default option. This option allow user to enter credit card information using PayFabric’s regular hosted page via regular keyboard, without using PTS device.  |
| - Use Encrypted key Entry - | All the basic functionality from PayFabric’s hosted pages to allow user to enter credit card information into the hosted pages will be disabled. User can only enter card data via PTS Device. |
| - Use Both -| Provide both entry options on the hosted page(s) so the user is able to choose their preferred option.  |

# Discretionary Data

Navigate to Settings > Discretionary Data.

With `Modern Design` mode for Virtual Terminal, merchant will have the ability to create their own custom field to associate additional data for each transaction with PayFabric. Discretionary data will only reside with PayFabric and will not be pass on to payment gateway or payment processor. 

# Products

Navigate to Settings > Products.

PayFabric provide the ability to manage the products. The uploaded products can be added to the transactions when processing transaction on ``Modern Design``
