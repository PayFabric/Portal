# JavaScript SDK V2
PayFabric provides a JavaScript library to support both Alternative Payment Methods as well as interaction with our new responsive Hosted Payment Page.  This JavaScript Library hosted by PayFabric will be responsible for configuring and presenting a payment popup or element that supports our hosted payment page as well as any alternative payment methods PayFabric supports today or into the future.

PayFabric released a new version of our JavaScript SDK during our May release of PayFabric.  This new version supports additional features, settings and callbacks. Looking for V1/Original version of our JavaScript SDK? Click [here](JavaScript-SDK-V1.md).

# Alternative Payment Methods
* [PayPal](APM.md#paypal)
* [Apple Pay](APM.md#apple-pay)
* [Google Pay](APM.md#Google-pay)

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

## Using our Hosted Bundled JavaScript SDK library to start the payment flow

Firstly, configure your checkout page to reference our JavaScript SDK and create an **Empty** DIV element with an id.
```HTML
<html>
  <head>
    <script src="https://www.payfabric.com/Payment/WebGate/Content/bundles/payfabricpayments.v2.bundle.min.js" 
            type="text/javascript" onload="payFabricSDKLoaded()"></script>
  </head>
  <body>
    <div id='uniquePaymentsDivId'></div>
  </body>
</html>
```

**Live Endpoint:** https://www.payfabric.com/Payment/WebGate/Content/bundles/payfabricpayments.v2.bundle.min.js

**Sandbox Endpoint:** https://sandbox.payfabric.com/Payment/WebGate/Content/bundles/payfabricpayments.v2.bundle.min.js

## Using our Hosted Standalone JavaScript SDK library to start the payment flow

If the platform that you are attempting to connect to PayFabric and our JavaScript SDK is experiencing some conflicts between the bundled PayFabric JS SDK and your platform, then we have provided a standalone version of the JS SDK.  This standalone version only includes the PayFabric JavaScript and none of the required dependencies.  

**Live Endpoint:** https://www.payfabric.com/Payment/WebGate/Content/bundles/payfabricpayments.v2.standalone.min.js

**Sandbox Endpoint:** https://sandbox.payfabric.com/Payment/WebGate/Content/bundles/payfabricpayments.v2.standalone.min.js

### Dependencies
* [Axios](https://axios-http.com/) >= v0.21.1
* [iFrameResizer](https://github.com/davidjbradshaw/iframe-resizer) >= v4.3.1

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
| debug | Optional | boolean | Receive some debugging and verbose logs to the Developer Console of your browser, to assist with understanding specific issues. |
| environment | Required | string | The PayFabric environment that you will be targeting.  Values are LIVE and SANDBOX. |
| target | Required | string | The target DIV will be responsible for displaying the payment box. |
| session | Required | string | The JWT Token value obtained from our Create JWT Token API. |
| successUrl | Conditional | string | A local URL from your website which will handle the redirect from the SDK in the event of an approved transaction.  Query parameters will be appended to the URL to indicate transaction status and information.<br/><br/>This field is **required** if successCallback is not populated. |
| failureUrl | Conditional | string | A local URL from your website which will handle the redirect from the SDK in the event of a declined or failed transaction.  Query parameters will be appended to the URL to indicate transaction status and information.<br/><br/>This field is **required** if failureCallback is not populated. |
| cancelUrl | Conditional | string | A local URL from your website which will handle the redirect from the SDK in the event of a customer cancelling the payment box. <br/><br/> To support retry we suggest using the cancelCallback option instead.<br/><br/>This field is **required** if cancelCallback is not populated and disableCancel is set to false or not provided. |
| successCallback | Optional | function | A local javascript function on your checkout page which will handle the call from the SDK in the event of an approved transaction.  A JavaScript object containing the transaction status and information will be provided. |
| failureCallback | Optional | function | A local javascript function on your checkout page which will handle the call from the SDK in the event of an declined or failed transaction.  A JavaScript object containing the transaction status and information will be provided. |
| cancelCallback | Optional | function | A local javascript function on your checkout page which will handle the call from the SDK in the event of a customer cancelling the payment box. |
| readyCallback | Optional | function | A local javascript function on your checkout page which will handle the call from the SDK when all payment methods are ready and able to be used for processing. |
| transactionProcessingCallback | Optional | function | A local javascript function on your checkout page which will handle the call from the SDK when a payment method is selected and processing starts. A JavaScript object containing the selected payment method type will be provided. |
| transactionStoppedProcessingCallback | Optional | function | A local javascript function on your checkout page which will handle the call from the SDK when the processing of a transaction stops before finializing (for example, if a user closes the `ApplePay` payment drawer or a local validation fails such as expiration date is incorrect or CVV is required). A JavaScript object containing the selected payment method type will be provided. |
| transaction3DSChallengeCallback | Optional | function | A local javascript function on your checkout page which will handle the call from the SDK when a 3DS challenge is presented to the consumer/cardholder.  **Note:** Only applies to transactions processing through countries that require 3DS. |
| displayMethod | Optional | string | The method in which PayFabric should display the payment box, list of methods are: <br/><br/>**DIALOG** – Will pop up a new dialog box with a grayed-out background displaying payment information. <br/><br/>**IN_PLACE** – Will just populate the HTML elements for payment processing within the placeholder DIV provided by the target option. |
| width | Optional | number | A parameter to resize the dialog's width, by default will use SDK default size of 600px.<br/><br/>Used only by the **DIALOG** display method. |
| requireShippingAddress | Optional | boolean | A parameter to determine whether the PayPal payment options flow requires a shipping address.<br/><br/>This method is currently only used by **PayPal** payment method.  It will inform PayPal to ask for shipping address information during the PayPal payment flow. |
| acceptedPaymentMethods | Optional | array of string | The list of available payment methods you wish to offer, available list of methods are:	`CreditCard`, `ECheck`, `GiftCard`, `PayPal`, `ApplePay` and `GooglePay`. By default it will use all the available configured payment methods. |
| disableCancel | Optional | boolean | A parameter to determine whether the cancel link is available for customer.<br/><br/>**True** indicates that the cancelUrl and cancelCallback will not fire. | 
| useBluefin | Optional | number | A parameter to control bluefin options on MRHPP when [BlueFin Profile](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/Bluefin.md) get enabled. When the value is '0', only regular keyboard entry for credit card is available, when the value is `1`, only encryption key entry via Bluefin device for credit card is available, when the value is `2`, both regular keyboard & encryption key entry for credit card is available.|
| useDefaultWallet | Optional | boolean | A parameter to control default wallet record will automatically load or not. If the value is `false`, then the default wallet record will not automatically load when the hosted payment page loads. If the value is `true`, then PayFabric will load the default wallet record on the hosted payment page when the hosted payment page loads. The default value is `true`. |
| iFrameSrcAdditionalParameters | Optional | Object | A JavaScript object providing a list of official and custom query paramters that should be appended to the generation of the URL used in the hosted page iFrame. |


## iFrameSrcAdditionalParameters Object

This object should be a standard object with a Key-Value pair of strings, for example:

```javascript
{
   "Field1": "Value1",
   "Field2": "Value2"
}
```

The field names can be any custom name that you would like to use in the generation of the URL used for the iFrame, or a list of fields to control the behavior of the PayFabric Hosted Page.  The list of official fields can be found [here](https://github.com/PayFabric/Hosted-Pages/blob/master/Sections/MRHPP.md#options).

This can be used to pass custom data to our hosted page, which can then be consumed through the use of our [Hosted Payment Page Themes](https://github.com/PayFabric/Themes).

# Mobile Hosted Payment Page with APM Example

![image](https://user-images.githubusercontent.com/12906817/145439223-5e43f1fe-a071-46da-a068-e4a09a8bf4e3.png)
