# Summary

In order to better protect card data at point of interaction, PayFabric integrates with Bluefin Decrytpx to allow end user to pass credit card number to PayFabric’s hosted page using point-to-point encryption (P2PE) device.

With P2PE, it helps with reduce PCI Scope and protects against malware in regard to card data protection. 

Supported P2PE device: IDTech SRED.

To configure Bluefin profile, navigate to **Settings** > **Bluefin Profile** (under **P2PE Decryptx Settings**).

![Bluefin Profile](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/BluefinProfile.png)

|Field                          |Description  | 
|------------------------------|-------------| 
|**Enable**| By default, Bluefin option is unchecked (disabled). If merchant would like to use P2PE device with PayFabric & Bluefin Decryptx, check mark this option. |
|**Partner ID**| Populate Bluefin Partner ID|
|**Partner Key**| Populate Bluefin Partner Key |
|**Client ID**| Populate Bluefin Client ID |
|**Web Service URL**| **Sandbox**: https://secure-cert.decryptx.com|
||**Production**: https://secure-prod.Decryptx.com/api/|
|**Raw Data**| Enter sample raw data to ensure connection is successfully established to test the Bluefin account credentials. |

## Entry Options

For all existing devices associated with the PayFabric account, PayFabric enables user to configure different entry option using the drop-down list.

|Field                          |Description  | 
|------------------------------|-------------| 
|**Use Non-Encrypted Key Entry**| User will use regular keyboard entry for entering card data into PayFabric’s hosted page. |
|**Use Encrypted Key Entry**| User will use P2PE device for entering card data into PayFabric’s hosted page.|
|**Use Both**|Enable user to switch between regular keyboard entry and P2PE device for entering card data into PayFabric’s hosted page.|
