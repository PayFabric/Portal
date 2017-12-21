Quick Start Guide
=================

To start integrating with PayLink, users will have to pre-configure their PayLink account.  If the user is wishing to link their PayLink account with their PayFabric account, there are some additional steps listed separately below.


Register PayLink Account
------------------------

#### Live
The process of registering an account for Live PayLink is currently handled by our Sales Team.  Please contact our team at <sales@nodus.com>.

#### Sandbox
The process of registering an account for Sandbox PayLink is almost the same with other web applications in general. You will navigate your browser to https://sandbox.payfabric.com/v2/paylinkshell, click sign up button, and populate all necessary fields of registration form to submit and accept the terms and conditions. Later, you will receive an activation email from support@payfabric.com, which contains an activation link you have to confirm your registration.


Sign-In PayLink Account
-----------------------

If everything goes fine, you can login PayLink portal with your activated account. If this is your first landing on PayLink, a step-by-step wizard will be displayed to help you setup the necessary information. You can feel free to dismiss this wizard, because you can bring it back by clicking the button Show Startup at the top right corner at any time.


PayFabric Device
----------------

You will find that a PayFabric *Device ID* and *Password* has been automatically created and assigned to your account when you logged in the first time, you can see this by navigating to the **Settings** page, and under **Secure Token**.  Clicking on **Show** will show the generated password for this Device.

If you wish to associate an existing PayFabric account this is done through the use of a PayFabric *Device ID* and *Password*.  Associating an existing PayFabric account provides the benefit of synchronizing Payment Gateway Account Profiles and Themes between the two systems.  A PayFabric Device can only be associated with one PayLink account at a time.

To associate an account, please navigate to the **Settings** page, and under **Secure Token** please click on the "Associate existing PayFabric account" link.  Enter your unique *Device Id* and *Password* and click Save.

To generate a new Device for use with PayLink, please see our PayFabric documentation on [Creating a Device](https://github.com/PayFabric/Portal/wiki#define-devices).

*Note: You must cancel all existing open PayLinks and WalletLinks before associating your PayLink account with PayFabric.*


Setup Gateway Account
---------------------

A Payment Gateway Account is required for PayLink to be successfully used.  A gateway can be created in two ways:

#### PayLink Portal
By navigating to the **Settings** page, and under **Gateway Profile** you will find a list of your current gateways as well as the option of adding, removing or updating your gateway accounts.

- To add a new gateway, click on **New** on the right hand side.  
- To edit an existing gateway, click on the gateway name.  
- To remove an existing gateway, click on the **X** beside the gateway name when you mouse over it.

#### PayFabric Portal 
If you have associated a PayFabric Device with your PayLink account, the Payment Gateway Accounts are synchronized between the two systems.  Using our PayFabric documentation on [Setting up a Gateway Account](https://github.com/PayFabric/Portal/wiki#setup-gateway-account) will allow you to create a gateway for use in both systems.

Extended Reading
----------------

* [PayLink Portal Pages](Features.md)
* [API Documentation](../../../APIs/tree/v2)
* [PayFabric Portal Documentation](https://github.com/PayFabric/Portal/tree/v2)
* [PayFabric API Documentation](https://github.com/PayFabric/APIs/tree/v2)
