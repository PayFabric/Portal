Transaction Types
=================

This section explains each of the transaction types in PayLink. The names chosen for PayLink are among the more common but not universal. Though the names may vary, the processing details do not.  

The transaction types available in PayLink are:

* Sale
* Book

You can find what each of these transaction types mean below.

#### Sale
A _Sale_ at one processor may be called _Capture_ at another. An approved _Sale_ is an immediate charge to the customer’s credit card or account.  Money will not be moved until settlement has occurred.  A _Sale_ can only be reversed with a _Void_ or a _Credit_.   A _Sale_ transaction does the same thing regardless of it being a credit card transaction, an eCheck transaction, or an ACH transaction.

#### Book
A _Book_ may also be known as a _Pre-Authorize_, _Pre-Authorization_ or _Authorization_. When dealing with credit card transactions a _Book_ is the reserve of a specified amount on the customer’s credit card or account. A _Book_ prevents the customer from using that portion of their credit / funds, but does not actually charge the card nor transfer any money. A _Book_ is useful for companies that ship merchandise one or more days after receiving an order. By issuing a _Book_, a company reserves the necessary amount on the customer’s card at order placement time.  As long as the book transaction remains open an approved _Ship_ transaction is guaranteed. A _Ship_ transaction is necessary to complete the _Book_. 

The number of days a _Book_ will stay open is determined by each cardholder’s issuing bank. The most common number is seven to ten days, but some banks may hold _Books_ for as long as four weeks and little as three days.

A _Book_ transaction cannot be reversed.  Issuing a _Void_ for a _Book_ transaction will not free up any money on the customer’s credit card.  To free up the reserved money you would need to issue a _Ship_ transaction and then _Void_ that shipped amount.

When dealing with eChecks and ACH, a _Book_ is not supported.
