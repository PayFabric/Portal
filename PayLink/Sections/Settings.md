# Settings

## DEV Central

The **Settings** page is used to configure your Device, define your ERP connection information and Gateway information and setting default gateways per currency in the event that you do not specify a particular gateway via the API.  If you need help configuration your ERP connection please contact our support team at <support@payfabric.com>.

For more information on how to configure your Device and Payment Gateway information please see our [Configure Portal](Configure%20Portal.md).

### PayFabric Device

**Settings** > **PayFabric Device**. PayLink leverage the PayFabric's hosted page to process transaction nand save wallet, set PayFabric Device to make PayLink have authentication to utilize PayFabric. The PayFabric Device will only list the device name of the PayFabric, which is in the same organization as the PayLink.

![PayLinkDevice](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/PayLinkDevice.png)

### Send a Test PayLink Notification

**Settings** > **Send a Test PayLink Notification**. PayLink has included the ability to send test payment links, these allow you to test the notification templates, and payment page theme, and to also get a feel of how a PayLink will behave for your customers.  Please note these are for testing purposes only and **WILL NOT** process actual funds in any event.  There is a limit on these tests, if you happen to reach this limit and require more, please contact our support team at <support@payfabric.com>.

![PayLinkTest](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/PayLinkTest.png)

### Configure ERP Connection

**Settings** > **Configure ERP Connection**. PayLink is able to send payment information back to Microsoft Dynamics GP, Microsofot Dynamics SL and Salespad after payment get proceseed via setup ERP Connection.

|Field                          |Description  |
|:------------------------------|:-------------|
| ERP Connection          | Setup connection for specific ERP. |
| Card Name Mapping       | Setup mapping bewteen supported card type in PayLink and card name in selected ERP. |
| Document Batch ID       |  This option allow to specify Batch ID for post document. |
| Generate Payment Number Setting       | When PayLink document's Post Data Type is Cash Receipt, specify the document prefix and the length of the PayLink’s payment document with this setting. Only available for Microsoft Dynamics GP integration. |
| Generate Debit Memo Number Setting       | When PayLink document contains Surcharge amount, a debit memo will be posted to Microsoft Dynamics GP with the amount. Only available for Microsoft Dynamics GP integration. |

![PayLinkERPConfiguration](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/PayLinkERPConfiguration.png)

### $ Configure Default Gateways

**Settings** > **$ Configure Default Gateways**. PayLink allow to send the API request without CreditCardGateway and ECheckGateway, and use default gateway profile instead, default credit card/eCheck gateway profile is set against currency code.

![PayLinkDefaultGateway](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/PayLinkDefaultGateway.png)

## Templates

**Settings** > **Templates**.The user is able to customize all of the notification templates that are distributed, either by email or SMS.  We have provided you with a default set of templates which you can copy and make changes to, or start from scratch.

All of our templates have ability of inserting parameters.  Parameters are active areas of the text that will be dynamically replaced by unique document information prior to the message being sent.  Each template may have different available parameters, please click on the **Insert Parameter** link when creating or modifying the templates to see available parameters.

![PayLinkEmailNotificationTemplates](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/PayLinkEmailNotificationTemplates.png)

Extended Reading
----------------

* [API Documentation](https://github.com/PayFabric/APIs/tree/master/PayLink)
* [PayFabric Portal Documentation](https://github.com/PayFabric/Portal)
* [PayFabric API Documentation](https://github.com/PayFabric/APIs)
