To configure transaction-related settings, navigate to Settings > DEV Central > PayFabric Settings. Please see the detailed description for each corresponding section below. 

![Settings](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/Settings.png)

## Device Name
The drop-down consists all existing devices associated with the PayFabric account. PayFabric enable user to configure different transaction settings for every device. Choose the corresponding device from the drop-down list, then begin making changes to the settings.

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
| Partial Shipping | This option is for capturing a pre-authorized transaction. By default (uncheck), the capturing amount must be same with pre-authorization. By checking this option, merchant allow the capturing amount less than the original pre-authorization transaction.|
| Lock Transaction Type| If this option is check marked, system will prevent user from changing the transaction type on PayFabric’s hosted payment page.|
|Fail On Address Mismatch | Payment gateway verifies the billing address. By checking this option, PayFabric will automatically void any approved payment if the address verification failed by the gateway/processor.|
|Lock Currency| If this option is check marked, system will prevent user from changing the currency type on PayFabric’s hosted payment page.|
|Popup Message|If this option is check marked, system will display response or error message to end-user using popup message instead of inline within PayFabric’s hosted payment page and hosted wallet page.|

## General Settings
|Field                          |Description  | 
|:------------------------------|:-------------| 
| Transaction Key Prefix          | User defined prefix for PayFabric transaction key. |
| PostURL       | PayFabric will post transaction response data (Non-sensitive fields) to this URL once this transaction is processed (successful or failed) |
| Maximum History Cards |Limit the number of wallet entries loaded on PayFabric hosted pages by specify the number of saved card. The default value is 10.|
| Return URL|A URL address that PayFabric can redirect to once a transaction is processed. The response fields will be encoded and attached into query string.|
| Maximum Shipping Address| Limit the number of shipping address(s) loaded on PayFabric hosted payment page by specify the number of saved card. The default value is 10.|
| Batch Number Prefix|User defined prefix for batch number.|
|Maximum Amount Per Transaction|Specify a maximum amount for each transaction.|

## Unit Of Measure Mapping for Payeezy (First Data GGE4)
For merchant using Payeezy gateway, item’s unit of measure needs to be mapped to the values supported by the gateway. See referenced URL for valid UOM from First Data. 

![Payeezy UOM](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/UOMMapping.png)

Reference: https://support.payeezy.com/hc/en-us/articles/203732159-Units-of-Measure
