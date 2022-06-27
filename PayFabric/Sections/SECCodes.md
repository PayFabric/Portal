# ACH Standard Entry Class (SEC) Codes

Each ACH application has a unique Standard Entry Class (SEC) Code that identifies a single ACH debit used by an Originator for the conversion of an eligible source document received via the U.S. mail or delivery service, at a lockbox location, or in person at a manned location for the payment of a bill. 

The SEC Code generally indicates:
- The nature of the transaction as consumer or corporate in nature (i.e., whether the funds transfer affects a consumer account or a corporate account at the RDFI). 
- Whether the transaction is single-entry or recurring.
- The specific computer record format that will be used to carry the payment and payment-related information relevant to the application.

## Supported SEC Codes by PayFabric with EVO ACH

| SEC Code             | ACH Application              | Application Use       |  Consumer/Corporate | Authorization Requirements    |
| -------------------- | :---------------------------- | :-------------------- | :-------------------- |:---------------------------- | 
| CCD | Corporate Credit or Debit | A single or a recurring ACH credit or debit originated to a corporate account. They are commonly used by Originators to pay vendors, concentrate funds from outlying accounts (cash concentration), to fund payroll, petty cash, or other disbursement accounts. A CCD entry can contain a single addenda record to relay payment-related information.| Corporate to Corporate | Agreement required for transfers between companies; written authorization implied. |
| TEL | Telephone Initiated Entries | A single or a recurring ACH debit that occurs when the consumer’s authorization for a transfer of funds is received orally via the telephone. | Corporate to Consumer | For Single, recorded oral authorization or written notice provided to the consumer confirming the oral authorization.  For Recurring, a copy of the authorization must be provided to the consumer. |
| WEB | Internet-Initiated/Mobile Entries | Credit WEB Entries: A Person-to-Person entry transmitted on behalf of one natural person to another natural person, or between accounts belonging to the same natural person. <br> Debit WEB Entries: ACH entry initiated according to an authorization obtained via the internet or a wireless network (e.g. mobile device) except for an oral authorization via a telephone call.| Corporate to Consumer | For credit WEB Entries: no authorization by the Receiver. <br> For debit WEB Entries: similarly authenticated. |
| PPD | Pre-arranged Payment or Deposit | A single or a recurring ACH credit or debit sent by an originator to a consumer account to make or collect a payment, where authorization is obtained in writing. Only one addenda record can be attached to each payment entry (the + denotes containing an addenda record)| Corporate to Consumer | For debit WEB Entries: similarly authenticated|Direct Deposit; Oral/Nonwritten; Direct Payments; Written. |
