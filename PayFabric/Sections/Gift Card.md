# Gift Card
PayFabric supports EVO Gift for USD currency, you can manage your gift card and process transaction with gift card in PayFabric. There is not settlement for Gift card transactions.

## Transaction Types for Gift Card
PayFabric supports below transaction types with Gift card, refer the [Transaction Type](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Transaction%20Types.md) for the definition.

* Sale
* Activate
* Reload
* Void

## Inquiry Balance for your Gift Card
1. Create an EVO Gift gateway, you can refer [Gateway Account Profile](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/Gateway%20Configuration.md)

2. Set the EVO Gift gateway as your Gift Card Default gateawy, you can refer [Default Gateway Profile](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/Gateway%20Configuration.md#default-gateway-profile)

3. Then you can inquiry balance on Gift Card Maintenance page Customers > Gift Card Maintenance

![GiftCardBalanceInquiry](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/Screenshots/GiftCardBalanceInquiry.png)

## Enable Gift Card Processing Method
### PAX Terminal
Navigate to Settings > Payment Terminals, check the option ["Allow Gift Card"](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/Payment%20Terminals.md#allow-gift-card). Then you can see the "Gift Card" button on Terminal Entry. Please refer to [Hosted Payment Page](https://github.com/PayFabric/Hosted-Pages/blob/master/Sections/Payment%20Page.md#terminal-entry)

### Process transaction with Gift Card on Hosted Payment Page 
Please refer to [Hosted payment page](https://github.com/PayFabric/Hosted-Pages/blob/master/Sections/Payment%20Page.md#hosted-payment-page-for-gift-card) for details.

### Process transaction with Gift Card on MRHPP
Please refer to [MRHPP](https://github.com/PayFabric/Hosted-Pages/blob/master/Sections/MRHPP.md#mobile-hosted-payment-page-gift-card-support) for details

### Process transaction with Gift Card via API
[Inquiry Balance API](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/GfitCardAPI.md)

[Gift Card Transaction API](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/ProcessGiftCardTransaction.md)
 
### Configure email receipt template for Gift Card transactions
Please refer to [Payment Receipt Template](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/Payment%20Receipt.md)
