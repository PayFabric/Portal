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
3. Read up on how to [Generate a JWT Token](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/JWTToken.md) with our APIs. 
4. Have a question or need help? Contact <support@payfabric.com>.

# Ready to Go?

Once you have followed our guides and information, you are ready to go.  Our JavaScript SDK is split into two (2) components:
* Initiating a new Transaction and Payment Intent
* Using our Hosted JavaScript SDK library to start the payment flow

## Initiating a new Transaction and Payment Intent

Using our Create a new Transaction and Generate a JWT Token API's you will receive a JWT Token, this token value is all you need to use to populate our new JavaScript Library.

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

