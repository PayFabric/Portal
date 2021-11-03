# Direct Google Pay Integration
PayFabric supports the Google Pay payment token being provided for payment processing.

Where do I start?
-----------------

Want to get started with Direct Google Pay integration? Here's a quick check list:

1. Register and then configure a PayFabric account, check out the [Guide](https://github.com/PayFabric/Portal/tree/master/PayFabric/Sections/Configure%20Portal.md) to learn how.
2. Activate Google Pay, check out the [Guide](https://github.com/PayFabric/Portal/blob/R17/PayFabric/Sections/APM.md#google-pay) to learn how.
3. Intergrate Google Pay as you would for any standard implementation, [follow Google's instructions](https://developers.google.com/pay/api/web/guides/setup).
4. Have a question or need help? Contact <support@payfabric.com>.

PayFabric API Integration
-------------------------

To start submitting Google Pay payment token, PayFabric utilizies our existing [Create and Process Transaction API](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Transactions.md#create-and-process-a-transaction) and existing [Card](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Objects.md#card) object.  The Card object is required to be provided like:

``` JSON
{
  "Card": {
    "Tender": "GooglePay",
    "Token": "<Payment Data | Payment Token>"
  }
}
```

In order to submit a Google Pay token, you can submit in two ways, PayFabric can either consume the entire Google Pay payment data object, or just the individual payment token object.

### Payment Data
``` JS
googlePayPaymentsClient.loadPaymentData(paymentDataRequest).then(function (paymentData) {
  var googlePayPaymentData = JSON.stringify(paymentData);
}
```

### Payment Token
``` JS
googlePayPaymentsClient.loadPaymentData(paymentDataRequest).then(function (paymentData) {
  var googlePayPaymentToken = paymentData.paymentMethodData.tokenizationData.token;
}
```

Both of these values are valid for the `Token` property of the `Card` object.
