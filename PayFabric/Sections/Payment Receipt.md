# Summary
Merchant can turn on the feature that send payment receipt to end customer after a transaction is processed. To do this, navigate through **Settings** > **Email Receipt Templates**, each [Transaction Type](Transaction%20Types.md) have their own email receipt template.

**Note**: Email receipt does not support for _Verify_ transaction.

![receipt](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/EmailReceiptTemplates.png)

### Send to Customer
Once checked, PayFabric will send receipt to customer once a transaction is processed. The email address of customer which will receive receipts is the email address in the billing address. The billing email address must be present for each transaction.

### Send to
The purpose of this field is to setup the addtional email addresses which are able to receive the copy of receipt. Normally, it's a staff in merchant's company.

*Note: There is an option to disable email receipt per transaction via API. Adding `DisableEmailReceipt` node in transaction request body, see `UserDefined` of [Document](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Objects.md#document) for more details. 

### Subject
Setup email subject.

### Body
Setup the email template. PayFabric support to setup seperate email templates for different transaction types and different tender types. The textboxes accepts html tags. PayFabric automatically setup a simple email template as below, you can preivew the email template by clicking the "preview" button on the right bottom corner of each textbox.

### Template Parameters
Following parameters are able to be embeded into email templates. At the moment of sending a receipt, these parameters are going to be replaced by the actual values.

| Field                 | Test Value                               | 
| --------------------- |:---------------------------------------- | 
| \[\[CompanyName\]\]   | Merchant's company name in profile page  | 
| \[\[CompanyPhone\]\]  | Merchant's company phone in profile page |
| \[\[CompanyCity\]\]   | Merchant's company city in profile page  |
| \[\[CompanyState\]\]  | Merchant's company state in profile page |
| \[\[CompanyCountry\]\]   | Merchant's company country in profile page|
| \[\[CompanyStreet1\]\]   | Merchant's street line 1 in profile page|
| \[\[CompanyStreet2\]\]   | Merchant's street line 2 in profile page|
| \[\[CompanyStreet3\]\]   | Merchant's street line 3 in profile page|
| \[\[CompanyEmail\]\]   | Merchant's company email in profile page|
| \[\[DocumentNumber\]\]   | Invoice number or order number of this transaction|
| \[\[PaymentNumber\]\]   | PayFabric transaction key|
| \[\[PaymentProcessDate\]\]   | Date and time of processing this transaction|
| \[\[CustomerName\]\]   | Customer unique name of this transaction |
| \[\[TaxAmount\]\]   | Tax amount of this transaction|
| \[\[PONumber\]\]   | Po number of this transaction|
| \[\[DiscountAmount\]\]   | Discounnt amount of this transaction |
| \[\[DutyAmount\]\]   | Duty amount of this transaction |
| \[\[FreightAmount\]\]   | Freight amount of this transaction|
| \[\[HandlingAmount\]\]   | Handling amount of this transaction|
| \[\[TotalAmount\]\]   | Total amount of this transaction. This amount will be equal to transaction amount |
| \[\[LineItemsHtmlTable\]\]   | Line items will be populated as HTML table to this table|
| \[\[BillToStreet1\]\]   | Billing address street line 1 of this transaction|
| \[\[BillToStreet2\]\]   | Billing address street line 2 of this transaction|
| \[\[BillToStreet3\]\]   | Billing address street line 3 of this transaction|
| \[\[BillToCity\]\]   | Billing address city of this transaction|
| \[\[BillToState\]\]   | Billing address state of this transaction|
| \[\[BillToCountry\]\]   | Billing address country of this transaction|
| \[\[BillToEmail\]\]   | Billing address email address of this transaction|
| \[\[BillToPhone\]\]   | Billing address phone number of this transaction|
| \[\[TransactionType\]\]   | Transaction type of this transaction. e.g. Sale, Pre-Authorization, Capture, Refund, Cancel|
| \[\[TransactionAmount\]\]   | Transaction amount of this transaction. This amount will be equal to total amount|
| \[\[TenderType\]\]   | Tender type of this transaction. |
| \[\[CardHolderFirstName\]\]   | Card holder first name|
| \[\[CardHolderMiddleName\]\]   | Card holder middle name|
| \[\[CardHolderLastName\]\]   | Card holder last name|
| \[\[MaskedAccount\]\]   | Masked credit card number|
| \[\[MaskedCheck\]\]   | Masked check number|
| \[\[OriginationID\]\]   | Gateway origination id|
| \[\[CardName\]\]   |Card Type of the card which used to process transaction, like Visa, MasterCard, JCB, etc...|
| \[\[BillToZip\]\]   | Billing zipcode of this transaction|
| \[\[SubTotal\]\]   | Subtotal amount of this transaciton, Subtotal amount is equal to Total amount - Discount amount - Duty amount - Freight amount - Tax amount - Handling amount|
| \[\[Last4Digits\]\]   | The last four digits of credit card number used to process transaction|
| \[\[ExpirationDate\]\]   | The expiration date of credit card number used to process transaction|
| \[\[CompanyZip\]\]   | Merchant's zipcode in profile page|
| \[\[TransactionStatus\]\]   | PayFabric Transaction Status|
| \[\[TransactionMsg\]\]   | PayFabric Transaction Message|
| \[\[AuthCode\]\]   | Gateway Authorization Code|
| \[\[CVV2Response\]\]   | Gateway CVV2 Response Code|
| \[\[AddressResponse\]\]   | Gateway Address Response Code|
| \[\[ZipResponse\]\]   | Gateway Zip Response Code|
| \[\[SurchargePercentage\]\]   | Surcharge Percentage|
| \[\[SurchargeAmount\]\]   | Surcharge amount (Original amount * SurchargeRate)|
| \[\[TipAmount\]\]   | Tip amount|
| \[\[Document.PaidInvoiceList\]\]   | Indicates the paid invoice list, this parameter is only available for the PayLink transactions. |
| \[\[Document.DocumentAmount\]\]   | Indicates the document amount, this parameter is only available for the PayLink transactions. |
| \[\[Document.DocumentDate\]\]   | Indicates the document date, this parameter is only available for the PayLink transactions. |
| \[\[Document.CustomerName\]\]   | Indicates the customer name, this parameter is only available for the PayLink transactions. |
