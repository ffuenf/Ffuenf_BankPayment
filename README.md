<a href="http://www.ffuenf.de" title="ffuenf - code • design • e-commerce"><img src="https://github.com/ffuenf/Ffuenf_Common/blob/master/skin/adminhtml/default/default/ffuenf/ffuenf.png" alt="ffuenf - code • design • e-commerce" /></a>

Ffuenf_BankPayment
==================
[![GitHub tag](https://img.shields.io/github/tag/ffuenf/Ffuenf_BankPayment.svg)][tag]
[![Build Status](https://img.shields.io/travis/ffuenf/Ffuenf_BankPayment.svg)][travis]
[![Code Quality](https://scrutinizer-ci.com/g/ffuenf/Ffuenf_BankPayment/badges/quality-score.png)][code_quality]
[![Code Coverage](https://scrutinizer-ci.com/g/ffuenf/Ffuenf_BankPayment/badges/coverage.png)][code_coverage]
[![PayPal Donate](https://img.shields.io/badge/paypal-donate-blue.svg)][paypal_donate]
[tag]: https://github.com/ffuenf/Ffuenf_BankPayment
[travis]: https://travis-ci.org/ffuenf/Ffuenf_BankPayment
[code_quality]: https://scrutinizer-ci.com/g/ffuenf/Ffuenf_BankPayment
[code_coverage]: https://scrutinizer-ci.com/g/ffuenf/Ffuenf_BankPayment
[paypal_donate]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=J2PQS2WLT2Y8W&item_name=Magento%20Extension%3a%20Ffuenf_BankPayment&item_number=Ffuenf_BankPayment&currency_code=EUR

This is a extension for Magento Community Edition that adds the payment method prepayment by bank transfer.

Features
--------

* prepayment payment method
* SEPA ready
* allow to display multiple bank accounts
* [HOT] show bank accounts dependent on order currency
* define minimum order total
* define maximum order total
* show bank accounts in PDF
* pay within X days
* show custom text in checkout
* show custom text in PDF
* [HOT] show custom text in order confirmation emails
* [HOT] show custom text in order confirmation emails for specific billing countries
* show link to CMS-Page instead of displaying account details in checkout

_custom text in order confirmation emails_

To show the custom text in order confirmation emails, you have to adjust your transactional email templates accordingly.
We reccoment to add `{{layout handle="sales_email_order_payment_message"}}` just below `{{var payment_html}}` in "order new" and "order new guest" templates.
By default the extension includes the following message (you may adjust it to your own in template/bankpayment/email/message.phtml):
```
***IMPORTANT***
Please use the following reference on your bank transfer:
[Order-ID]
```

_show custom text in order confirmation emails for specific billing countries_

This might be useful if customers from foreign countries doesn't pay attention to additional fees for international transfers.
See template/bankpayment/email/message.phtml for a reference implementation.

Compatibility
-------------

This Extension is a fork of [Magento_BankPayment](https://github.com/PHOENIX-MEDIA/Magento-BankPayment) and uses the same namespace for its configuration.
In older versions of Magento there may be also a Mage_BankPayment core extension which is not compatible.
Please do not use this extension in any combination with the above!

Platform
--------

The following versions are supported and tested:

* Magento Community Edition 1.9.2.2
* Magento Community Edition 1.9.1.1
* Magento Community Edition 1.8.1.0
* Magento Community Edition 1.7.0.2
* Magento Community Edition 1.6.2.0

Other versions are assumed to work.

Requirements
------------

|                                                                     | PHP 5.4        | PHP 5.5           | PHP 5.6       | PHP 7.0       |
| ------------------------------------------------------------------- | -------------- | ----------------- | ------------- | ------------- |
| [EOL](https://secure.php.net/supported-versions.php) / STABLE / RC  | EOL            | STABLE            | **STABLE**    | STABLE        |
| automated tests on [travis]                                         | allow failure  | **required pass** | allow failure | allow failure |

Magento Community Edition officially supports PHP 5.4 and PHP 5.5.

Non-official compatibility to PHP 5.6 may be reached by following the tips on [Use of iconv.internal_encoding is deprecated](https://magento.stackexchange.com/questions/34015/magento-1-9-php-5-6-use-of-iconv-internal-encoding-is-deprecated).
Non-official compatibility to PHP 7.0 may be reached by using [Inchoo_PHP7](https://github.com/Inchoo/Inchoo_PHP7).

Installation
------------

Use [modman](https://github.com/colinmollenhour/modman) to install:
```
modman init
modman clone https://github.com/ffuenf/Ffuenf_Common
modman clone https://github.com/ffuenf/Ffuenf_BankPayment
```

Deinstallation
--------------

#### via [Ffuenf_MageTrashApp](https://github.com/ffuenf/Ffuenf_MageTrashApp)

An additional module called [Ffuenf_MageTrashApp](https://github.com/ffuenf/Ffuenf_MageTrashApp) has been installed to help you to uninstall this extension in a clean way.
If it is not yet installed, please install it from [Ffuenf_MageTrashApp](https://github.com/ffuenf/Ffuenf_MageTrashApp)
If it is installed, go to your backend menu System > Configuration > Advanced > MageTrashApp, then click on the tab "Extension Installed", select the drop down option "Uninstall" of this extension and press "Save Config" button to uninstall
If you use this extension, you don't need to make any queries in your database as explained below in case of manually uninstallation.

#### via [modman](https://github.com/colinmollenhour/modman)

Use [modman](https://github.com/colinmollenhour/modman) to clear all files and symlinks:
```
modman clean Ffuenf_BankPayment
```
see `sql/ffuenf_bankpayment_setup/uninstall.sql` to clear all entries of this extension from your database.

Development
-----------
1. Fork the repository from GitHub.
2. Clone your fork to your local machine:

        $ git clone https://github.com/USER/Ffuenf_BankPayment

3. Create a git branch

        $ git checkout -b my_bug_fix

4. Make your changes/patches/fixes, committing appropriately
5. Push your changes to GitHub
6. Open a Pull Request

License and Author
------------------

- Author:: Achim Rosenhagen (<a.rosenhagen@ffuenf.de>)
- Copyright:: 2015, ffuenf

The MIT License (MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.