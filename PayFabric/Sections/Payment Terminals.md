# Payment Terminals
PayFabric supports card-present transactions using EMV devices from PAX Technology. The 2 supported devices from PAX are: S300 and D210. 
To configure terminal devices & settings, navigate to **Settings** > **Terminals** (under Payment Terminals). Please see the detailed description & instruction below.

## Terminals

Terminal devices need to be created on PayFabric portal prior to use within an application.

Steps:
1.	From **Terminals** tab > click **Create**;
2.	Populate the terminal device details & click **Save**.


|Field                          |Description  | 
|------------------------------|-------------| 
|**Terminal Name**| Enter a descriptive name for the device. |
|**Local Network IP Address**| Enter the local network IP address for the device. |
|**Local Network Port**| Populate the network port number for the device. Default is 10009. |
|**Payment Terminal Type**| Use default option ‘PAX Generic’ for PAX’s EMV device. |

## Options

### Device Name

The drop-down consists all existing devices associated with the PayFabric account. PayFabric enable user to configure different terminal options for every PayFabric device/application. Choose the corresponding PayFabric device from the drop-down list, then begin making changes to the terminal settings.

![Terminal Device Name](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/TerminalsDeviceName.png)

### Available Terminals

Specify the terminals available for each PayFabric device/application by tick the box next to each terminal device.

![Terminal Available Terminals](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/TerminalsAvailableTerminals.png)

### Default Payment Terminal

Specify a terminal device under this option so the selected device is always the default terminal device to be used for the application. 

![Terminal Default Terminal](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/TerminalsDefaultTerminal.png)

### Processing Method

![Terminal Processing Method](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/TerminalsProcessingMethod.png)

|Field                          |Description  | 
|------------------------------|-------------| 
|Web Entry Only| Only allow transaction using web entry via hosted page |
|EMV Only| Only allow transaction using EMV device |
|Both EMV and Web Entry| Allow both EMV and web entry |

### Default Processing Method

This option is only available when **Both EMV and Web Entry option** of **Processing Method** are selected. Specify the default processing method on payment processing page.

### Only Allow Default Payment Terminal

This option is only available when **Both EMV and Web Entry option** of **Processing Method** are selected. If check marked, user will only be able to use the default payment terminal without the ability to switch to a different terminal device from the list.

### Require Credit Card Signature

This option is only available when **Both EMV and Web Entry option** of **Processing Method** are selected. If check marked, customer will be required to provide signature for card-present transaction, as applicable.

###### Related Reading
* [How to retrieve signature image](../../../../../../PayFabric/Hosted-Pages/blob/master/Sections/Payment%20Terminals%20Signature%20Page.md)
