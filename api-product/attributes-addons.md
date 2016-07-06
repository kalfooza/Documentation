##### Addons - optional products

A Product can also have "add-on" or optional Products associated with it.
The Product attribute `addons` takes a list of add-on Product attributes, and
can be added to the General Product attributes.
A customer can purchase these `addons` together with the main event ticket. These `addons` can be required or optional and can be displayed in groups.

This JSON object defines a typical add-on list:

    "addons": [
      {
        "id": "product_id",
        "name": "product name",
        "prices": {*},
        "image": "URL",
        "description": "brief description",
        "category": "",
        "rrule": "",
        "min": 0,
        "max": 1,
        "group_discount": false
      },
      { ... }
    ]

This table outlines the definitions of the add-on attributes:

| Req | Attribute      | Value       | Notes |
|:---:| -------------- | ----------- | ----- |
|     | id             | Product `xid` | |
|     | name           | Product name | |
|     | image          | URL of image if any | |
|     | description    | brief Product description | |
|     | category       | category, e.g. accommodation, gift, etc. | |
|     | prices         | JSON object that is the same as the event `prices` property | |
|     | rrule          | dates this product is available / applicable | |
|     | min            | minimum number to select, 0=optional | |
|     | max            | maximum number to select, 1 by default| |
|     | group\_discount | true if group-discounts should apply to this | | |


* Note that the prices field shares the same structure as the event prices.  Please see the prices section for more details.
* If category is given, Products with the same category should be displayed
together. It also implies that only one of these in the same category needs to
be selected.
* If a Product applies to days, then the RRule can be used to specify the date
  format.
* If `min` is non-zero, then this Product is a **required** one.
* The `max` attribute specifies the maximum quantity of this product, that can be purchased.


