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

Using our [Create a new Transaction](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Transactions.md#create-a-transaction) and [Create a JWT Token](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/JWTToken.md#json-web-tokens) API's you will receive a JWT Token which is used to indicate your payment intent, this token value is all you need to use to populate our new JavaScript Library.

Once you have obtained your JWT Token, you have all the data you need to initiate our payment flow using our JavaScript SDK library.

## Using our Hosted JavaScript SDK library to start the payment flow

Firstly, configure your checkout page to reference our JavaScript SDK and create an **Empty** DIV element with an id.
```HTML
<html>
  <head>
    <script src="https://www.payfabric.com/Payment/WebGate/Content/bundles/payfabricpayments.bundle.min.js" 
            type="text/javascript" onload="payFabricSDKLoaded()"></script>
  </head>
  <body>
    <div id='uniquePaymentsDivId'></div>
  </body>
</html>
```

Secondly, create a new function to load our payments SDK.  We will immediately display the payment box as soon as it is ready.  We recommend that you do this either on our script load, or through a button click.
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

function payFabricSDKLoaded() {
  // PayFabric SDK has loaded, you can call loadPaymentsSDK function directly from here for immediately presentment of the payment box.
}
```

# JavaScript SDK Options

| Option | Required | Data Type | Description |
| :-------------  | :------------- | :------------- | :------------- | 
| environment | Required | string | The PayFabric environment that you will be targeting.  Values are LIVE and SANDBOX. |
| target | Required | string | The target DIV that will be responsible for displaying the payment box. |
| session | Required | string | The JWT Token value obtained from our Create JWT Token API. |
| successUrl | Conditional | string | A local URL from your website which will handle the redirect from the SDK in the event of an approved transaction.  Query parameters will be appended to the URL to indicate transaction status and information.<br/><br/>This field is **required** if successCallback is not populated. |
| failureUrl | Conditional | string | A local URL from your website which will handle the redirect from the SDK in the event of a declined or failed transaction.  Query parameters will be appended to the URL to indicate transaction status and information.<br/><br/>This field is **required** if failureCallback is not populated. |
| cancelUrl | Conditional | string | A local URL from your website which will handle the redirect from the SDK in the event of a customer cancelling the payment box. <br/><br/> To support retry we suggest using the cancelCallback option instead.<br/><br/>This field is **required** if cancelCallback is not populated and disableCancel is set to false or not provided. |
| successCallback | Optional | function | A local javascript function on your checkout page which will handle the call from the SDK in the event of an approved transaction.  A JavaScript object containing the transaction status and information will be provided. |
| failureCallback | Optional | function | A local javascript function on your checkout page which will handle the call from the SDK in the event of an declined or failed transaction.  A JavaScript object containing the transaction status and information will be provided. |
| cancelCallback | Optional | function | A local javascript function on your checkout page which will handle the call from the SDK in the event of a customer cancelling the payment box. |
| displayMethod | Optional | string | The method in which PayFabric should display the payment box, list of methods are: <br/><br/>**DIALOG** – Will pop up a new dialog box with a grayed-out background displaying payment information. <br/><br/>**IN_PLACE** – Will just populate the HTML elements for payment processing within the placeholder DIV provided by the target option. |
| width | Optional | number | A parameter to resize the dialog's width, by default will use SDK default size of 600px.<br/><br/>Used only by the **DIALOG** display method. |
| requireShippingAddress | Optional | boolean | A parameter to determine whether the PayPal payment options flow requires a shipping address.<br/><br/>This method is currently only used by **PayPal** payment method.  It will inform PayPal to ask for shipping address information during the PayPal payment flow. |
| acceptedPaymentMethods | Optional | array of string | The list of available payment methods you wish to offer, available list of methods are:	`CreditCard`, `ECheck` and `PayPal`. By default it will use all the available configured payment methods. |
| disableCancel | Optional | boolean | A parameter to determine whether the cancel link is available for customer.<br/><br/>**True** indicates that the cancelUrl|cancalCallback will not fire. | 
