# BPMedia_Walmart
A sample integration for Magento 1.9 CE to the Walmart Seller API. 

#### *This version uses two off-server scripts, `inventory.php` and `call.php`, as a middle man between our RHEL6 PHP5.3 server and the Walmart API servers, as the SDK dependencies require PHP 5.4.*

## Dependencies

	- PHP >=5.4, either on the Magento server, or on a separate middleman web server (AWS Free Tier FTW!)
	- [fillup/walmart-partner-api-sdk-php:develop](https://github.com/fillup/walmart-partner-api-sdk-php/tree/develop)
	- guzzlehttp/guzzle-services:dev-master (included in fillup/walmart-partner-api-sdk-php:develop)
	
## Installation

	**If your Magento server is running PHP >=5.4...**

	- Install BPMedia_Walmart using [colinmollenhour/modman](https://github.com/colinmollenhour/modman/).
	- Run `composer.json` using [Composer](https://getcomposer.org/).
	- Place `inventory.php` and `call.php` in the Magento root web directory (/var/www/html for example).'
	- Update **Line 27** of `Observer.php` to point to the `inventory.php` script in your Magento root web directory.
	- Update **Line 3** of `call.php` to point correct `autoload.php` generated by Composer.


	**If your Magento server is NOT running PHP >=5.4...**

	- Install BPMedia_Walmart using [colinmollenhour/modman](https://github.com/colinmollenhour/modman/).
	- Run `composer.json` using [Composer](https://getcomposer.org/).
	- Place `inventory.php` and `call.php` on separate, PHP 5.4 or higher middleman web server. Highly recommend setting allow/deny or some kind of IP filtering on said server.
	- Update **Line 27** of `Observer.php` to point to the `inventory.php` script on your middleman server.
	- Check **Line 3** of `call.php` to point correct `autoload.php` generated by Composer.

## Further Documentation

	- [Walmart PHP SDK documentation](https://github.com/fillup/walmart-partner-api-sdk-php/blob/develop/docs/README.md)
	- [Walmart Seller API Documentation](https://developer.walmartapis.com/)


## Todo

	- [ ] Add price updates from Magento event observers
	- [ ] Add option to create Magento "dummy" order for all new Walmart orders
	- [ ] Make code suck less

## Reporting Issues
Please use Github Issues to report any problems you find or questions
about usage.

## Contributing
Pull requests are welcome for improvements to the core library, tests,
and documentation.

##  No Warranty

This package is a free distribution, provided at no cost.
It does not come with any warranty, expressed or implied.
Source code is provided for your convenience.
Walmart does not assume any responsibilities for its quality or support.

## License

The MIT License (MIT)

Copyright (c) 2016 Phillip Shipley

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