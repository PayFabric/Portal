# Gift Card
PayFabric supports EVO Gift for USD currency, you can manage your gift card and process transaction with gift card in PayFabric. Gift card transactions won't be settled.

## Transaction Types for Gift Card
PayFabric supports to do below transaction types with Gift card, refer the [Transaction Type](https://github.com/PayFabric/APIs/blob/R19/PayFabric/Sections/Transaction%20Types.md) for the definition.

* Sale
* Activate
* Reload
* Void

## Inquiry Balance for your Gift Card
1. Create an Evo Gift gateway, you can refer [Gateway Account Profile](https://github.com/PayFabric/Portal/blob/R19/PayFabric/Sections/Gateway%20Configuration.md)

2. Set the Evo Gift gateway as your Gift Card Default gateawy, you can refer [Default Gateway Profile](https://github.com/PayFabric/Portal/blob/R19/PayFabric/Sections/Gateway%20Configuration.md#default-gateway-profile)

3. Then you can inquiry balance on Gift Card Maintenance page Customers->Gift Card Maintenance

![GiftCardBalanceInquiry](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/Screenshots/GiftCardBalanceInquiry.png)

## Enable Gift Card Processing Method
### PAX Terminal
Navigate to Settings->Payment Terminals, check the option "Allow Gift Card". Then you can see the "Gift Card" button on Terminal Entry. Please refer [Hosted Payment Page](https://github.com/PayFabric/Portal/blob/R19/PayFabric/Sections/Payment%20Terminals.md#allow-gift-card)

### Process transaction with Gift Card on Hosted Payment Page 
Please refer [Hosted payment page](https://github.com/PayFabric/Hosted-Pages/blob/R19/Sections/Payment%20Page.md#hosted-payment-page-for-gift-card) for details.

### Process transaction with Gift Card on MRHPP
Please refer [MRHPP](https://github.com/PayFabric/Hosted-Pages/blob/R19/Sections/MRHPP.md#mobile-hosted-payment-page-gift-card-support) for details

### Process transaction with Gift Card via API
[Inquiry Balance API](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/GfitCardAPI.md)
[Gift Card Transaction API]
 
