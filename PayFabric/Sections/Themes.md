# Themes

Different application may have different needs of utilizing PayFabric’s hosted payment page. A **Theme** can be assigned to a device to customize the layout and format of the PayFabric’s hosted payment page. 
The "Themes" page can be displayed by navigating **Settings** > **Themes** (under **Dev Central** section). 
1.	In the **DEV Central** section, select the ‘Themes’ option 
2.	Click the **Create New +** button and enter a name that would be relevant to the application 
3.	Click the **Save** button to save the changes to the theme.

![Theme](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/Themes.png)

Also you can choose to show/hide the related fields on hosted payment page by check/uncheck the parameters of the theme.

![ThemeParams](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/ParamsofTheme.png)

## Assigning Theme to a Device

Go back to **Devices** page and click on the icon of **Default Theme** and select the desired theme to associate to the chosen device. 
Besides configuring theme for device, you can also "Change" device name, "Reset" device password, "Revoke" the device, or "Delete" this device. "Revoke" device will regenerate the GUID.

![Default theme](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/DefaultTheme.png)

# Field IDs

The PayFabric Hosted page has a variety of different elements on the page.  Here is a list of the most common of them and their HTML Element IDs, types and the controlling CSS class name of the label and element (here after referred to as the block).

PayFabric Themes support the use of both Cascading Style Sheets (CSS) and JavaScript.  Our Hosted Pages are automatically loaded with JQuery.  You are able to use the JQuery ID and CSS Class selectors, such as `$("#SetupID_ID")` for specific Element ID's and `$(".setupid")` for the Block Class Names, for additional ID's and Class Names please see the below tables.

| Field | Block Class Name | Element ID | Element Type | Note |
| :--- | :--- | :--- | :--- | :--- |
| Gateway Account | setupid | SetupID_ID | Drop Down Box |  |
| Transaction Type | trxtype | TransactionType | Drop Down Box | |
| Batch Number | batch | BatchNumber | Text Box | |
| Pay Later | paylater | PayLater | Text Box (Date Picker) | |
| Transaction Amount | total | TrxAmount | Text Box | |
| Currency | currency | CurrencyCode | Drop Down Box | |
| Billing Information | N/A | billaddress | Grouping | See [Billing Fields](#billing-fields) |
| Shipping Information | N/A | shipaddress| Grouping | See [Shipping Fields](#shipping-fields) |
| Payment Information | N/A | payment | Grouping | See [Payment Fields](#payment-fields) |


## Billing Fields

| Field | Block Class Name | Element ID | Element Type | Note |
| :--- | :--- | :--- | :--- | :--- |
| Address Line 1 | N/A | NewBillAddresses_AddressLine1 | Text Box |  |
| Address Line 2 | N/A | NewBillAddresses_AddressLine2 | Text Box |  |
| Address Line 3 | N/A | NewBillAddresses_AddressLine3 | Text Box |  |
| City | City | NewBillAddresses_CityCode | Text Box |  |
| State/Province | State | NewBillAddresses_StateCode | Text Box |  |
| Zip/Postal Code | Zip | NewBillAddresses_ZipCode | Text Box |  |
| Country | N/A | NewBillAddresses_CountryCode | Text Box |  |
| Phone | N/A | NewBillAddresses_Phone1 | Text Box |  |
| Email | N/A | NewBillAddresses_Email | Text Box |  |


## Shipping Fields

| Field | Block Class Name | Element ID | Element Type | Note |
| :--- | :--- | :--- | :--- | :--- |
| Historic Address Selector | addresslist | shipaddresslist | Drop Down Box |  |
| Use New Address | usenewaddress | shipuse | Check Box | Visible when Use History Address checked |
| Address Line 1 | N/A | NewShipAddresses_AddressLine1 | Text Box |  |
| Address Line 2 | N/A | NewShipAddresses_AddressLine2 | Text Box |  |
| Address Line 3 | N/A | NewShipAddresses_AddressLine3 | Text Box |  |
| City | City | NewShipAddresses_CityCode | Text Box |  |
| State/Province | State | NewShipAddresses_StateCode | Text Box |  |
| Zip/Postal Code | Zip | NewShipAddresses_ZipCode | Text Box |  |
| Country | N/A | NewShipAddresses_CountryCode | Text Box |  |
| Phone | N/A | NewShipAddresses_Phone1 | Text Box |  |
| Email | N/A | NewShipAddresses_Email | Text Box |  |
| Use History Address | N/A | useoldAddress | Check Box | Visible when Use New Address checked |
| Same As Billing | N/A | asbilluse | Check Box | Visible when Use New Address checked |


## Payment Fields

| Field | Block Class Name | Element ID | Element Type | Note |
| :--- | :--- | :--- | :--- | :--- |
| Historic Card Selector | historycards | ChosenCardID | Drop Down Box |  |
| Card Information | CardContainer | N/A | Grouping | Below Fields are included in this group |
| Account # | N/A | NewCard_CardNumber | Text Box |  |
| Expiration Date | CardDate | exptime1 *and* exptime2 | Text Box |  |
| CVV | cvv2 | NewCard_SecurityCode | Text Box |  |
| Card Name | NameOnCard | N/A | Grouping |  |
| First Name | FirstName | NewCard_CardHolderFirstName | Text Box |  |
| Middle Initial | MiddleInitial | NewCard_CardHolderMiddleName | Text Box |  |
| Last Name | LastName | NewCard_CardHolderLastName | Text Box |  |
| Save Card | savecard_h6Container | NewCard_IsSaveCard | Check Box |  |
| Is Default Card | savecard_h6Container | NewCard_IsDefaultCard | Check Box | Visible when Save Card is ticked or existing card |

## JQuery Examples

To remove the Transaction Type Block from the page, try `$('.trxtype').remove();`

To make the Transaction Amount Element read-only, try `$('#TrxAmount').attr('readonly', 'true')`
