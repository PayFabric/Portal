ERP Integration Payloads
========================

Payment Line XML
----------------

| Attribute                  | Description    | 
| -------------------------- | :------------- | 
| \<CCNumber\>                 | Masked card number you used to pay for this payment | 
| \<CCType\>                   | Mapped card name in PayLink. If you do not map your cards, then CCType will be the standard card type.\brFor example, you map 'Visa' as 'V', then CCType will be 'V' when you process transaction with Visa card. |
| \<CCExpDate\>                | Credit card expiration date. |
| \<TrxAmount\>                | Transaction amount |
| \<AuthCode\>                 | Transaction auth code, returned by gateway|
| \<Connection name="paymentech"\br connector="Paymentech" \/\>| Connection name: Gateway name;Connectoer: connector name|
|\<ResponseData\>              |[Response Object](#response-field)|
|\<RequestData\>               |[Request Object](#request-field)|
|\<CustomerID\>               | The document ID you entered when you send paylink|
|\<BatchID\>                  | The Batch ID you entered when you send paylink|
|\<CustomerID\>               | The Customer ID you entered when you send paylink |
|\<Date\>                     | The Post back ERP timestamp |
|\<SOPTYPE\>                  | 3-Invoice; 2-Order |
|\<DocTypeID\>                | 2-Order;3-Invoice;|
|\<TradeDiscount\>            | Document discount|
|\<FreightAmount\>            | Freight amount|
|\<MiscAmount\>               | Misc amount|
|\<TransactionType\>          | 1-Sale; 2-Book;|

Cash Receipt XML
----------------

| Attribute                  | Description    | 
| -------------------------- | :------------- | 
| \<CCNumber\>                 | Masked card number you used to pay for this payment | 
| \<CCType\>                   | Mapped card name in PayLink. If you do not map your cards, then CCType will be the standard card type.\brFor example, you map 'Visa' as 'V', then CCType will be 'V' when you process transaction with Visa card. |
| \<CCExpDate\>                | Credit card expiration date. |
| \<TrxAmount\>                | Transaction amount |
| \<AuthCode\>                 | Transaction auth code, returned by gateway|
| \<Connection name="paymentech"\br connector="Paymentech" \/\>| Connection name: Gateway name;Connectoer: connector name|
|\<ResponseData\>              |[Response Object](#response-field)|
|\<RequestData\>               |[Request Ojbect](#request-field)|
|\<Invoices\>		       |List of [Invoice object](#invoice)|
|\<CustomerID\>               | The document ID you entered when you send paylink|
|\<BatchID\>                  | The Batch ID you entered when you send paylink|
|\<CustomerID\>               | The Customer ID you entered when you send paylink |
|\<Date\>                     | The Post back ERP timestamp |
|\<SOPTYPE\>                  | 3-Invoice; 2-Order |
|\<DocTypeID\>                | 2-Order;3-Invoice;|
|\<TradeDiscount\>            | Document discount|
|\<FreightAmount\>            | Freight amount|
|\<MiscAmount\>               | Misc amount|
|\<TransactionType\>          | 1-Sale; 2-Book;|
|\<DocumentID\>		      | The auto generated cash receipt number when post back to GP|


ResponseData Object
-------------------

This object is the transaction response get from gateway.
 
| Attribute                  | Description    | 
| -------------------------- | :------------- | 
|\<Type\>                    |1 - 'Sale'; 2 - 'Book';|
|\<Status\>                  |Transaction status|
|\<Category\>                |Mark the current object|
|\<Fields\>                  |List of [Field object](#field-object)|

Field Object
------------

| Attribute                  | Description    | 
| -------------------------- | :------------- | 
|\<Name\>     | Field name|
|\<Desc\>     | Field description|
|\<Value\>    | Field Value|
|\<Required\> | Mark if this field is required|
|\<Encrypted\>| Mark if this field is encrypted|
|\<Type\>     | Field type, all are '1'| 

Response Field
--------------

| Field id    | Name   |Desc   |Value  |Comments | 
| --------- | :-------- | :-------- | :-------- | :-------- | 
|TrxField_D16|OriginationID|||Transaction origination ID of gateway|
|TrxField_D17|ResultCode|||Transaction result code respond from gateway|
|TrxField_D80|TrxRefIndex||||
|TrxField_D24|AuthCode|||Auth code respond from gateway|
|TrxField_D186|Token|||The card token|
|TrxField_D32|AVSAddResponse|||Address verification result code|
|TrxField_D33|AVSZipResponse|||Zip verification result code|
|TrxField_D31|ResponseMsg|||Response message of gateway|


Request Field
-------------

| Field id | Name |Desc |Comments | 
| --------- | :-------- | :-------- | :-------- |
|TrxField_D1|AccountNum|Credit Card Number|Credit Card Number|Transaction origination ID of gateway|
|TrxField_D3|Exp|Expiration Date MMYY|Transaction result code respond from gateway|
|TrxField_D5|AVSname|First Name|Card holder first name|
|TrxField_D7|AVSname|Last Name|Card holder last name|
|TrxField_D8|AVSaddress1|Address 1|Billing address street 1|
|TrxField_D11|AVScity|City|Billing city|
|TrxField_D12|AVSstate|State|Billing state|
|TrxField_D13|AVSzip|Zip|Billing zip|
|TrxField_D15|Amount|Transaction Amount|Transaction amount|
|TrxField_D40|OrderID|Invoice Number|Document number you entered when send paylink|
|TrxField_D57|CustomerEmail|Email|Email address you entered when send paylink|
|TrxField_D19|PaymentType|||
|TrxField_D48|CustomerCode||Customer number you entered when send paylink|
|TrxField_D74|CurrencyCode||Currency code|
|TrxField_D2 |TRXFIELD_D2||Masked card number\/account number|
|TrxField_D18|CCType||Mapped card name in PayLink. If you do not map your cards, then CCType will be the standard card type.\br For example, you map 'Visa' as 'V', then CCType will be 'V' when you process transaction with Visa card.|
|TrxField_D6 |MiddleName||Card holder middle name|
|TrxField_D54|AccountName||Card holder first name + middle name + last name|
|TrxField_D55|AccountStreet||Billing address street 1|
|TrxField_D47|CountryCode||Billing country|
|TrxField_D13|SaveCreditCard||0-not save;1-save;|
|MSO_PFTrxKey|||PayFabric transaction key|
|MSO_WalletID|||PayFabric wallet ID|
|MSO_EngineGUID|||Gateway GUID|
|MSO_Last_<br/>Xmit_Date|MSO_Last_<br\>Xmit_Date||Last process transaction date|
|MSO_Last_<br\>Xmit_Time|MSO_Last_<br\>Xmit_Time||Last process transaction time|
|MSO_Last_<br\>Settled_Date|MSO_Last_<br\>Settled_Date||Transaction settled date|
|MSO_Last_<br\>Settled_Time|MSO_Last_<br\>Settled_Time||Transaction settled time|
|MSO_Doc_Number|MSO_Doc_Number||Document Number you entered when send paylink|
|MSO_Doc_Type|MSO_Doc_Type||2-Order; 3-Invoice;|
|MSO_Source_<br\>Of_Document|MSO_Source_<br\>Of_Document||1-SOP; 5-Cash Receipt|
|BACHNUMB|BACHNUMB||Batch number you entered when send paylink|
|MSO_IsBatched|MSO_IsBatched||Mark if this document is batched, 0-Not batched; 1-Batched;|
|CUSTNMBR|CUSTNMBR||Customer number you entered when send paylink|
|MSO_FirstName|MSO_FirstName||card holder first name|
|MSO_LastName|MSO_LastName||card holder last name|
|MSO_CardExpDate|MSO_CardExpDate||Card expiration date|
|MSO_CardName|MSO_CardName|card name|
|MSO_Default|MSO_Default|||
|Status|Status|||
|SEQNUMBR|SEQNUMBR||Only for GP|
|CRCRDAMT|CRCRDAMT||Transaction amount|
|CCode|CCode||Billing country code|
|PHONNAME|PHONNAME||Billing phone number|
|MSO_COMMENT3|MSO_COMMENT3||Filled with transaction amount because CCA requires this|
|MSO_COMMENT4|MSO_COMMENT4||MSO_COMMENT4 is a fixed value to mark the transaction is post from PayLink;|
|MSO_IsCardValid|MSO_IsCardValid||0-invalid;1-valid|
|MSO_TrxStatus|MSO_TrxStatus|||
|MSO_TrxType|MSO_TrxType|||
|MSO_Auth_Amount|MSO_Auth_Amount||Transaction amount|
|MSO_Capture<br/>_Amount|MSO_Capture<br/>_Amount||captured amount|
|BCHSOURC|BCHSOURC||'Sales Entry' when the post data type is Payment Line|


Invoice
-------

| Attribute                  | Description    | 
| ------------------ | :------------- |
| \<ApplyAmount\>    |Apply amount|
| \<InvoiceID\>	     |Apply to invoice number,Document Number you entered when send paylink|
| \<RMType\>	     |1-Invoice|
| \<Discount\>	     |Document discount|
| \<PaymentType\>    |9-Cash Receipt|	
