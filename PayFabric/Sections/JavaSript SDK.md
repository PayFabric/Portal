# JavaScript SDK
PayFabric provides a JavaScript library to support both Alternative Payment Methods as well as interaction with our new responsive Hosted Payment Page.  This JavaScript Library hosted by PayFabric will be responsible for configuring and presenting a payment popup or element that supports our hosted payment page as well as any alternative payments methods PayFabric supports today or into the future.

# Features
* Support for Credit Card payment processing
* Support for ACH payment processing
* Support for PayPal Payments

# Alternative Payment Methods
* [PayPal](Sections/APM.md#paypal)
* [**Future**] Apple Pay
* [**Future**] Google Pay

# Where do I start?

Want to get started with our PayFabric JavaScript SDK integration?  Here's a quick check list:

1. Read up on our [guides and information](https://github.com/PayFabric/APIs/tree/master/PayFabric) for our APIs
2. Read up on how to [Create a new Transaction](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Transactions.md#create-a-transaction) with our APIs.
3. Read up on how to [Create a JWT Token](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/JWTToken.md) with our APIs. 
4. Have a question or need help? Contact <support@payfabric.com>.

# Ready to Go?

Once you have followed our guides and information, you are ready to go.  Our JavaScript SDK is split into two (2) components:
* Initiating a new Transaction and Payment Intent
* Using our Hosted JavaScript SDK library to start the payment flow

## Initiating a new Transaction and Payment Intent

Using our [Create a new Transaction](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Transactions.md#create-a-transaction) and [Create a JWT Token](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/JWTToken.md#json-web-tokens) API's you will receive a JWT Token, this token value is all you need to use to populate our new JavaScript Library.

```HTML
<html>
  <head>
    <script src="https://www.payfabric.com/Payment/WebGate/Content/bundles/payfabricpayments.bundle.min.js" 
            type="text/javascript"></script>
  </head>
  <body>
    <div id='uniquePaymentsDivId'></div>
  </body>
</html>
```

```javascript
var jwtToken = '<JWT Token obtained from Generate a JWT Token API>';
var payfabricpaymentssdk;
function loadPaymentsSDK() {
  try {
    payfabricpaymentssdk = new payfabricpayments({
      environment: 'SANDBOX|LIVE',
      target: 'uniquePaymentsDivId',
      displayMethod: 'DIALOG|IN_PLACE',
      session: jwtToken,
      successUrl: '/OrderSuccess',
      failureUrl: '/OrderFailure',
      cancelUrl: '/OrderCancel'
    });
  } catch (error) {
    // Handle unexpected SDK initialization errors
  }
}
```

# JavaScript SDK Options

| Option | Required | Description |
| :-------------  | :-------------  | :------------- | 
| environment | Required | The PayFabric environment that you will be targeting.  Values values are LIVE and SANDBOX. |
| target | Required | The target DIV that will be responsible for displaying the payment box. |
| session | Required | The JWT Token value obtained from our Create JWT Token API. |
| successUrl | Conditional | A local URL from your website which will handle the redirect from the SDK in the event of an approved transaction.  Query parameters will be appended to the URL to indicate transaction status and information.<br/><br/>This field is **required** if successCallback is not populated. |
| failureUrl | Conditional | A local URL from your website which will handle the redirect from the SDK in the event of a declined or failed transaction.  Query parameters will be appended to the URL to indicate transaction status and information.<br/><br/>This field is **required** if failureCallback is not populated. |
| cancelUrl | Conditional | A local URL from your website which will handle the redirect from the SDK in the event of a customer cancelling the payment box. <br/><br/> To support retry we suggest using the cancelCallback option instead.<br/><br/>This field is **required** if cancelCallback is not populated and disableCancel is set to false or not provided. |
| successCallback | Optional | A local javascript function on your checkout page which will handle the call from the SDK in the event of an approved transaction.  A JavaScript object containing the transaction status and information will be provided. |
| failureCallback | Optional | A local javascript function on your checkout page which will handle the call from the SDK in the event of an declined or failed transaction.  A JavaScript object containing the transaction status and information will be provided. |
| cancelCallback | Optional | A local javascript function on your checkout page which will handle the call from the SDK in the event of a customer cancelling the payment box. |
| displayMethod | Optional |The method in which PayFabric should display the payment options, list of methods is:**DIALOG** – Will pop up a new dialog box with a grayed-out background displaying payment information. **IN_PLACE** – Will just populate the HTML elements for payment processing within the placeholder DIV provided by the target option. |
| width | Optional | A parameter to resize the dialog width, by default will use SDK default size. |
| requireShippingAddress | Optional |A bool parameter to determin whether the PayPal payment options flow should require a shipping address to be obtained. |
| acceptedPaymentMethods | Optional |The list of available payment methods you wish to offer, list of methods is:	CreditCard, ECheck and PayPal, if accept multiple payment methods, then seperate the methods with ','. By default it will use all the available payment methods. |
| disableCancel | Optional | A bool parameter to determin whether the cancel link available for customer. | 
