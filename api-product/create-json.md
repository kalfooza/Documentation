### Create Product JSON...

Our JSON document describes all the attributes the _Make it Social_  `/products` API endpoint needs to create a new Product.

The `xid` must be unique, however internally when our system saves this Product
model it prepends the Provider `xid` to this Product `xid`. This makes products
unique across all Provider Products.

Again ensure that the `pay_id` is the value generated from our Client Portal.
For more information see the [Quick set up](/1-intro/quick.md) page.


    {
      "xid": "demoproduct_9",
      "provider_id": "democlient_1",
      "pay_id": "1234567",
      "name": "Lisbon Sunset Fado & Tapas ",
      "url": "https://twitter.com/",
      "image": "https://makeitsocial.com/media/holidays/223.jpg",
      "description": "Lisbon holidays book now to enjoy the sun",
      "prices": {
        "currency": "EUR",
        "base": 54,
        "rates_category": [
          {
            "name": "Senior",
            "price": 106,
            "id": "code1"
          },
          {
            "name": "Student",
            "price": 149,
            "id": "code2"
          }
        ]
      },
      "booking": {
        "engine": "local"
      },
      "date_range": {
        "start": "2016-05-01T00:00:00Z",
        "end": "2016-12-31T20:00:00Z",
        "selectability": "10",
        "duration": "3D"
      }
    }

_Figure 2: example Product JSON document_


