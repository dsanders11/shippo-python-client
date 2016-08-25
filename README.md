#Shippo API Python wrapper
[![PyPI version](https://badge.fury.io/py/shippo.svg)](https://badge.fury.io/py/shippo)
[![Build Status](https://travis-ci.org/goshippo/shippo-python-client.svg?branch=helper-merge-steveByerly-fork-2)](https://travis-ci.org/goshippo/shippo-python-client)

Shippo is a shipping API that connects you with [multiple shipping carriers](https://goshippo.com/carriers/) (such as USPS, UPS, DHL, Canada Post, Australia Post, UberRUSH and many others) through one interface.

Print a shipping label in 10 mins using our default USPS and DHL Express accounts. No need to register for a carrier account to get started.

You will first need to [register for a Shippo account](https://goshippo.com/) to use our API. It's free to sign up, free to use the API. Only pay to print a live label, test labels are free. 

### How do I get set up? ###

####To install from the source file:

```
#!shell
python setup.py install
```

or pip (https://pip.pypa.io/en/latest/index.html):
```
#!shell
sudo pip install shippo
``` 

#### To test:

Set your `SHIPPO_API_KEY` as an environment variable.
e.g. on OSX:

`export SHIPPO_API_KEY="<MY-API-KEY>"`

Run the test with the following command:

```
#!shell
python setup.py test --test-suite=shippo
```


#### Dependencies:

##### requests & mock

```
#!shell
sudo easy_install requests
sudo easy_install mock
``` 

#### Using the API:

```python

import shippo
shippo.api_key = "<API-KEY>"

address1 = shippo.Address.create(
    object_purpose='PURCHASE',
    name='John Smith',
    street1='6512 Greene Rd.',
    street2='',
    company='Initech',
    phone='+1 234 346 7333',
    city='Woodridge',
    state='IL',
    zip='60517',
    country='US',
    email='user@gmail.com',
    metadata='Customer ID 123456'
)

print 'Success with Address 1 : %r' % (address1, )

```

We've created a number of examples to cover the most common use cases. You can find the sample code files in the [examples folder](examples/).
Some of the use cases we covered include:

* [Basic domestic shipment](examples/basic-shipment.py)
* [Interntational shipment](examples/interntaional-shipment.py)  - Custom forms, interntational destinations
* [Price estimation matrix](examples/estimate-shipping-prices.py)
* [Retrieve rates, filter by delivery time and purchase appropriate label](examples/filter-by-delivery-time.py)
* [Retrieve rates, purchase label for fastest delivery option](examples/purchase-fastest-service.py)
* [Retrieve rates so customer can pick preferred shipping method, purchase label](examples/get-rates-to-show-customer.py)


## Documentation

Please see [https://goshippo.com/docs](https://goshippo.com/docs) for complete up-to-date documentation.

## About Shippo

Connect with multiple different carriers, get discounted shipping labels, track parcels, and much more with just one integration. You can use your own carrier accounts or take advantage of our discounted rates with the USPS and DHL Express. Using Shippo makes it easy to deal with multiple carrier integrations, rate shopping, tracking and other parts of the shipping workflow. We provide the API and dashboard for all your shipping needs.

## Supported Features

The Shippo API provides in depth support of carrier and shipping functionalities. Here are just some of the features we support through the API:

* Shipping rates & labels
* Tracking for any shipment with just the tracking number
* Batch label generation
* Multi-piece shipments
* Manifests and SCAN forms
* Customs declaration and commercial invoicing
* Address verification
* Signature and adult signature confirmation
* Consolidator support including:
	* DHL eCommerce
	* UPS Mail Innovations
	* FedEx Smartpost
* Additional services: cash-on-delivery, certified mail, delivery confirmation, and more.
