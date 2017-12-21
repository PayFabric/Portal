PayLink
=======

Queues
------

You are able to perform various actions on your existing PayLinks and WalletLinks in their respecitive queues.  You are able to:

* Cancel Unpaid PayLinks or Incomplete WalletLinks
* Resend Notifications for PayLinks and WalletLinks
* Resend Confirmation Receipts
* View Transaction Details
* View and Modify ERP Posting Payloads

Settings
--------

The **Settings** page is used to define your ERP connection information, configure your Device and Gateway information and setting default gateways per currency in the event that you do not specify a particular gateway via the API.  If you need help configuration your ERP connection please contact our support team at <support@payfabric.com>.

For more information on how to configure your Device and Payment Gateway information please see our [Quick Start Guide](Quick%20Start%20Guide.md).


Templates
---------

The user is able to customize all of the notification templates that are distributed, either by email or SMS.  To get started please navigate to **Templates** page.  We have provided you with a default set of templates which you can copy and make changes to, or start from the beginning.

All of our templates have ability of inserting parameters.  Parameters are active areas of the text that will be dynamically replaced by unique document information prior to the message being sent.  Each template may have different available parameters, please click on the **Insert Parameter** link when creating or modifying the templates to see available parameters.


Test PayLinks
-------------

PayLink has included the ability to send test payment links, these allow you to test the notification templates, and payment page theme, and to also get a feel of how a PayLink will behave for your customers.  Please note these are for testing purposes only and **WILL NOT** process actual funds in any event.  There is a limit on these tests, if you happen to reach this limit and require more, please contact our support team at <support@payfabric.com>.  

To send a test PayLink please navigate to the **Templates** page, and under **Send a Test PayLink Notification** use this form to send your test payment link.

Extended Reading
----------------

* [Quick Start Guide](Quick%20Start%20Guide.md)
* [API Documentation](../../../APIs/tree/v2)
* [PayFabric Portal Documentation](https://github.com/PayFabric/Portal/tree/v2)
* [PayFabric API Documentation](https://github.com/PayFabric/APIs/tree/v2)
