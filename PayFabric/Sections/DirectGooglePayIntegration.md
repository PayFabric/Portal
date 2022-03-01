# Direct Google Pay:tm: Integration
PayFabric allows your customers to make payments through our platform using any credit or debit card saved to their Google Account using Google Pay.  This allows them to use this instead of using our normal credit card entry page, saving some time required to enter their card details again.

## Google Pay Terms

By accepting and integrating Google Pay, you agree to Google's [terms of service](https://payments.developers.google.com/terms/sellertos)

Where do I start?
-----------------

Want to get started with Direct Google Pay integration? Here's a quick check list:

1. Register and then configure a PayFabric account, check out the [Guide](https://github.com/PayFabric/Portal/tree/master/PayFabric/Sections/Configure%20Portal.md) to learn how.
2. Activate Google Pay, check out the [Guide](https://github.com/PayFabric/Portal/blob/R17/PayFabric/Sections/APM.md#google-pay) to learn how.
3. Intergrate Google Pay as you would for any standard implementation, [follow Google's instructions](https://developers.google.com/pay/api/web/overview).
4. Have a question or need help? Contact <support@payfabric.com>.


Google Pay Configuration
------------------------

In order to successfully use Google Pay, you are required to provide the target Payment Service Provider (PSP) or Gateway.  PayFabric's configured gateway name is `payfabric`.  In addition, you must provide an ID that identifies you as a PayFabric merchant.  This is required for `Step 2: Request a payment token for your payment provider` of the Google Pay instructions.

To obtain your PayFabric Merchant ID, please log into the [PayFabric Portal](https://www.payfabric.com/Portal) and navigate to the Activate Google Pay page.  On this page, take note of the URL in your browsers address bar.  The value identified as `srvInstId` is your PayFabric Merchant ID.

/Portal/AppCenter/PortalLoader?srvInstId=**1732b98e-4c2a-4aff-bfeb-8fe2e53d2361**&serviceType=PayFabric

```JS
const tokenizationSpecification = {
  type: 'PAYMENT_GATEWAY',
  parameters: {
    'gateway': 'payfabric',
    'gatewayMerchantId': '<Your PayFabric Merchant ID here>'
  }
};
```

In the provided example, replace `'<Your PayFabric Merchant ID here>'` with `'1732b98e-4c2a-4aff-bfeb-8fe2e53d2361'`.

  **Note**: This value will be unique for each PayFabric account, and will also be differen between Sandbox and Production environments.
  
PayFabric API Integration
-------------------------

To start submitting Google Pay payment token, PayFabric utilizies our existing [Create and Process Transaction API](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Transactions.md#create-and-process-a-transaction) and existing [Card](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Objects.md#card) object.  The Card object is required to be provided like:

```JSON
{
  "Card": {
    "Tender": "GooglePay",
    "EncryptedToken": "<Payment Data | Payment Token>"
  }
}
```

In order to submit a Google Pay token, you can submit in two ways, PayFabric can either consume the entire Google Pay payment data object, or just the individual payment token object.  PayFabric supports the following card networks and countries for Google Pay:
* Countries
  * United States of America - USD Only
* Card Networks
  * American Express
  * Discover
  * JCB
  * MasterCard
  * Visa

### Payment Data
```JS
googlePayPaymentsClient.loadPaymentData(paymentDataRequest).then(function (paymentData) {
  var googlePayPaymentData = JSON.stringify(paymentData);
}
```

### Payment Token
```JS
googlePayPaymentsClient.loadPaymentData(paymentDataRequest).then(function (paymentData) {
  var googlePayPaymentToken = paymentData.paymentMethodData.tokenizationData.token;
}
```

Both of these values are valid for the `Token` property of the `Card` object.
Note that the token should be a string value and **not** a JSON object.  See the below example.
  
### Example
  
  ```JSON
  {
    "Type": "Sale",
    "Amount": "1.00",
    "Currency": "USD",
    "SetupId": "EVO US_CC",
    "Card": {
      "Tender": "GooglePay",
      "EncryptedToken": "{ \"signature\": \"MEUCIChSWu3shwWceGGLMJ...lDecEp+KpSW0gVXdarbE=\", \"intermediateSigningKey\": { \"signedKey\": \"{\\\"keyValue\\\":\\\"MFkwEwYHKoZIzj0...YJuyfrQBg\\\\u003d\\\\u003d\\\",\\\"keyExpiration\\\":\\\"1612040747821\\\"}\", \"signatures\": [ \"MEUCIE8/acZOJIL...SHz3uBP08=\" ] }, \"protocolVersion\": \"ECv2\", \"signedMessage\": \"{\\\"encryptedMessage\\\":\\\"JLJLXYJLB7M...FKK4Z794yMQcldgFY8unxPwaH8QRrZVC0YZ\\\",\\\"ephemeralPublicKey\\\":\\\"BLTMDROl...hVYVyJuS4\\\\u003d\\\",\\\"tag\\\":\\\"kPRhTN1dl...uX2mU\\\\u003d\\\"}\" }"
    }
  }
  ```
