Nodus PayFabric Cloud service has its own web portal where merchant can configure their PayFabric account settings, view and manage their transaction reports.

## PayFabric Portal URL:
https://www.payfabric.com/portal

## Service Mode

Under a single account login, user can toggle the service mode between Sandbox & Live using the toggle button on the top navigation bar.
By default, the account is set to sandbox mode when the account is first created. Merchant can promote it to live mode in order to process live transactions by toggle the button.

**Sandbox:**

![Sandbox](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/Sandbox.png)

**Live:**

![Live](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/Live.png)

## Devices

Any application that utilizes PayFabric in the backend for payment processing requires a set of device & password.

| Field                | Description  | 
| :--------------------|:-------------| 
| Device ID            | A unique & secure identifier to identify different applications under a single PayFabric merchant account. | 
| Device Password      | Assigned to a single device. Both device Id and device password are required when integrating with PayFabric. | 

Every merchant will get a **System Default** device by default when they were creating a PayFabric account. System default device is generally the device that is used if user creates wallet entry or process a transaction directly from the PayFabric portal.
To generate a new set of device and corresponding password, navigate through Settings. From **Settings** >  **Devices** (under **Dev Central** section) > click **Generate** button and populate fields "Device Name", "Password", "Confirm Password", and click "Save". 

![Device](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/DeviceManagement.png)

You can keep on adding multiple devices based on your business needs. A single device is corresponding to an application. 

## Themes

Different application may have different needs of utilizing PayFabric’s hosted payment page. A **Theme** can be assigned to a device to customize the layout and format of the PayFabric’s hosted payment page. 
The "Themes" page can be displayed by navigating **Settings** > **Themes** (under **Dev Central** section). 
1.	In the **DEV Central** section, select the ‘Themes’ option 
2.	Click the **Create New +** button and enter a name that would be relevant to the application 
3.	Click the **Save** button to save the changes to the theme.

## Assigning Theme to a Device

Go back to **Devices** page and click on the icon of **Default Theme** and select the desired theme to associate to the chosen device. 
Besides configuring theme for device, you can also "Change" device name, "Reset" device password, "Revoke" the device, or "Delete" this device. "Revoke" device will regenerate the GUID.

![Default theme](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/DefaultTheme.png)

## Gateway Profile

Payment gateway account is needed to process transactions with PayFabric. 
STEPS:
1.	If the payment gateway account is not associated to an existing PayFabric account, under **Settings** > **Gateway Account**, click ‘**+ Add New Gateway**’ to create new gateway profile.
2.	Choose ‘**Use your Existing Gateway**’ option
3.	Fill in the remaining fields based on the payment gateway that is being used

 * If a Gateway Account has already been setup, choose which of the supported gateways that will be used for processing transactions. 
 * If a gateway account is needed, please contact Nodus Technologies Support for information on setting up a Gateway Account. 

4.	Click the ‘Save’ button to save the changes
5.	If there are multiple gateway accounts that need to be setup, such as if both Credit Cards and eChecks will be processed from this website, then repeat the steps in this section for each gateway account.

## Advanced Settings

* [PayFabric Settings]()
* [L2/3 Fields Default]()
* [Receipt Email]()
* [Themes]()
