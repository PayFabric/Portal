# Alternative Payment Methods
Alternative payment methods are not applicable for the transactions contain Surcharge or Tip amounts.

# PayPal
Provide PayPal as a new form of alternative payment method (APM) on PayFabric. After activate your connection to PayPal, it will be available as an alternative payment method on your PayFabric account. Please see the detailed description & instruction below.

### Activate PayPal
Steps:
1.	Navigate to **Settings** > **Alternative Payment Methods**.
2.	From **Alternative Payment Methods** page > click **Configure** button on PayPal box.
3.	Click **Activate** button, PF will direct to PayPal login page.
4.	Once merchant login PayPal successfully and go back to PayFabric side, PayPal status will changed to **ACTIVE**.

# Google Pay:tm:
Provide Google Pay as a new form of alternative payment method (APM) on PayFabric. After activating Google Pay, it will be available as an alternative payment method on your PayFabric account. Please see the detailed description & instruction below.

## Google Pay Terms

By accepting and integrating Google Pay, you agree to Google's [terms of service](https://payments.developers.google.com/terms/sellertos)

### Activate Google Pay
Steps:
1.	Navigate to **Settings** > **Alternative Payment Methods**.
2.	From **Alternative Payment Methods** page > click **Configure** button on Google Pay box.
3.	Click **Activate** button, status will changed to **ACTIVE**.

If you will be using our Mobile Hosted Payment Page, then no other steps are needed aside from the below instructions for our [JavaScript SDK](JavaScript%20SDK.md).

If you would like to integrate directly to the Google Pay API, then please [follow Google's instructions](https://developers.google.com/pay/api/web/overview).  For the details on how to provide the Google Pay provided Token's to PayFabric for payment processing, please follow the details found in our [Direct Google Pay Integration](DirectGooglePayIntegration.md) documentation.


# Apple Pay
Provide Apple Pay as a new form of alternative payment method (APM) on PayFabric. After activate Apple Pay, it will be available as an alternative payment method on your PayFabric account. Apple Pay button only available on IOS device. Please see the detailed description & instruction below.

### Activate Apple Pay
Steps:
1.	Navigate to **Settings** > **Alternative Payment Methods**.
2.	From **Alternative Payment Methods** page > click **Configure** button on Apple Pay box.
3.	Click **Add a Domain** button, specify the top-level domain (ex: payfabric.com) or sub-domain (ex: manage.payfabric.com) that you wish to enable Apple Pay against.
4.  Click **Download Files** button to download verification file.
    > Download and hosting the Apple's domain-verification file will only have to be done once for each domain registering with PayFabric. You do not need to download the file again if the domain has already been registered with another PayFabric account.
5.  Host the Apple's domain-verification file you downloaded from the step above at the following path:

    `https://[[DOMAIN_NAME]/.well-known/apple-developer-merchantid-domain-association`
6.  Click the **Confirm** button to register the domain.

### Embed Pay by PayPal/Google Pay/Apple Pay to your page
Please check the detailed instructions for [JavaScript SDK](JavaScript%20SDK.md)
