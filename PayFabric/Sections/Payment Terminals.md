# Payment Terminals
PayFabric supports card-present transactions using EMV devices from PAX Technology. The supported devices from PAX are: S300, D210 and PX7. 
To configure terminal devices & settings, navigate to **Settings** > **Terminals** (under Payment Terminals). Please see the detailed description & instruction below.

## Terminals

Terminal devices need to be created on PayFabric portal prior to use within an application.

Steps:
1.	From **Terminals** tab > click **Create**;
2.	Populate the terminal device details & click **Save**.


|Field                          |Description  | 
|------------------------------|-------------| 
|**Terminal Name**| Enter a descriptive name for the device. |
|**Registration Mode**| Choose 'Manual IP Address' or 'DNS Provider'. Manual IP Address requires manual IP address entry and registering of the EMV terminal device. DNS Provider option offers the auto-registering capability for each EMV hardware terminal device based on the serial number.|
|**Serial Number**| This field exists if selected registration mode is 'DNS Provider'. Populate the serial number of the hardware terminal device. |
|**Local Network IP Address**| This field exists if selected registration mode is 'Manual IP Address'. Enter the local network IP address for the device. |
|**Local Network Port**| This field exists if selected registration mode is 'Manual IP Address'. Populate the network port number for the device. Default is 10009. |
|**Payment Terminal Type**| This field is to indicate the EMV connection type, supported options are 'PAX Generic' and 'Diamond Cloud'. 'PAX Generic': PayFabric initial request to the terminal via the browser being used for PayFabric. 'Diamond Cloud': PayFabric inital request to the terminal via Diamond cloud API. |
|**POSID**| This field exists if selected Payment Terminal Type 'Diamond Cloud'. Populate the POSID configured in Diamond Cloud. |

## Options

### Device Name

The drop-down consists all existing devices associated with the PayFabric account. PayFabric enable user to configure different terminal options for every PayFabric device/application. Choose the corresponding PayFabric device from the drop-down list, then begin making changes to the terminal settings.

![Terminal Device Name](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/TerminalsDeviceName.png)

### Available Terminals

Specify the terminals available for each PayFabric device/application by tick the box next to each terminal device.

![Terminal Available Terminals](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/TerminalsAvailableTerminals.png)

### Default Payment Terminal

Specify a terminal device under this option so the selected device is always the default terminal device to be used for the application. 

![Terminal Default Terminal](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/TerminalsDefaultTerminal.png)

### Processing Method

![Terminal Processing Method](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/TerminalsProcessingMethod.png)

|Field                          |Description  | 
|------------------------------|-------------| 
|Web Entry Only| Only allow transaction using web entry via hosted page |
|EMV Only| Only allow transaction using EMV device |
|Both EMV and Web Entry| Allow both EMV and web entry |

### Default Processing Method

This option is available when **Both EMV and Web Entry option** or **EMV Only** of **Processing Method** is selected. Specify the default processing method on payment processing page.

### Only Allow Default Payment Terminal

This option is available when **Both EMV and Web Entry option** or **EMV Only** of **Processing Method** is selected. If check marked, user will only be able to use the default payment terminal without the ability to switch to a different terminal device from the list.

### Require Credit Card Signature

This option is available when **Both EMV and Web Entry option** or **EMV Only** of **Processing Method** is selected. If check marked, customer will be required to provide signature for card-present transaction, as applicable. Please note that PayFabric will ignore the signature for reference transactions.

### Allow Gift Card

This option is to enable the ability to process transaction with Gift Card on the EMV entry.

###### Related Reading
* [How to retrieve signature image](../../../../../../PayFabric/Hosted-Pages/blob/master/Sections/Payment%20Terminals%20Signature%20Page.md)
