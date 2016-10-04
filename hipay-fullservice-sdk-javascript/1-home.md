# HiPay Fullservice - Javascript SDK

##Payment Gateway Direct Post Integration Guide

## HTML-based integration
This integration will merge with your existing HTML in a page using a payment form from which data will be used by the HiPay’s JavaScript Direct Post library.

This document is designed to give you details on how to integrate your business to the HiPay Fullservice Payment Gateway using a “direct post” method. It provides step-by-step instructions on how to simply and quickly get up and running with our services, as well as detailed reference material.

**Disclamer**
While every effort has been made to ensure the accuracy of the information contained in this publication, the information is supplied without representation or warranty of any kind, is subject to change without notice and does not represent a commitment on the part of HiPay. HiPay, therefore, assumes               no responsibility and shall have no liability, consequential or otherwise, of any kind arising from this material or any part thereof, or any supplementary materials subsequently issued by HiPay.

**Technical support**
If you need any complementary information concerning the technical implementation of HiPay Fullservice, don’t hesitate to contact our Business IT Services:

##HTML Form Example

```html
<form method="POST" action="#" id="hipay-direct-post">

##JavaScript
With the above HTML template, you must include the HiPay JavaScript library.

###JavaScript: Include this example
`<script type="text/javascript" src="javascripts/token-2.1.1.min.js"></script>`

You must also add JavaScript instructions so that no card data is sent to your server unencrypted.

###JavaScript request parameters

| Field name   |      Format      |  Description |
|----------|:-------------:|------:|
| setTarget |  AN | If you are testing in your stage or production account, you can choose the following targets:<br/>- test<br/>- live
| setCredentials |  AN | Your direct post API credentials. *Be careful*! Do not use classic API credentials but public API credentials created on the HiPay Fullservice back office.
| create |  - | Credit card information. Please refer to the “Create token request parameters” table below.

###Create token request parameters

| Field name   |  Format |  Length |   Req. |  Description |
|----------|:-------------:|------:|------:|------:|
| card_number |  N | 19 |  M | The card number. The length is from 12 to 19 digits.
| card_expiry_month |  N | 2|  M | The card expiry month. Expressed with two digits (e.g.: 01).
| card_expiry_year |  N | 4|  M | The card expiry year. Expressed with four digits (e.g.: 2014).
| card_holder |  AN | 25|  - | The cardholder’s name as it appears on the card (up to 25 characters).
| cvc |  N | 4|  - | The 3- or 4- digit security code (called CVC2, CVV2 or CID depending on the card brand) that appears on the credit card.
| multi_use |  N | 1|  - | Indicates if the token should be generated either for a single-use or a multi-use.<br/>Possible values:<br/>1 = Generate a multi-use token<br/>0 = Generate a single-use token.<br/>While a single-use token is typically generated for a short time and for processing a single transaction, multi-use tokens are generally generated for recurrent payments.
 
The following table lists and describes the response fields.

| Field name   |      Description     |
|----------|:------------:|
|token| Token that was created. |

##JavaScript direct post Example

```js
<script type="text/javascript">
            
```