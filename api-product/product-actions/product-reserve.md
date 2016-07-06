## Product Reservations

Once the Product is [available](product-available.md), you can make a
"pre-payment booking". This is a Product reservation and you must make an HTTP `POST`
request to the `/products/{id}/reserve` endpoint containing the JSON body
previously mentioned in the [Product actions section](README.md).

A reservation must be carried out for each user, therefore the JSON body of the
request requires user information to be set in addition to the availability
attributes.

The general reservation attributes (not including the availability ones
previously mentioned) are:

| Req | Attribute | Value       | Notes |
|:---:| --------- | ----------- | ----- |
|     | uid       | `user_id` from the grouping API | |
|     | gid       | the group `groups_id` | |
|     | ssid      | the user basket `selection_id` | |
|     | gus       | total number of group member | |
|     | pus       | number of seats paid | |
|     | usr       | see below... | | |

In addition individual user data is required to make the reservation, `usr`
details:

| Req | Attribute | Value       | Notes |
|:---:| --------- | ----------- | ----- |
|     | fn        | first name | |
|     | sn        | surname | |
|     | em        | email | |
|     | ad        | address details see below... | |
|     | udc       | phone details see below... | | |

Address details, `ad` attributes, are an array of address objects. A typical
address object is defined as:

| Req | Attribute | Value       | Notes |
|:---:| --------- | ----------- | ----- |
|     | s1        | address line 1 | |
|     | s2        | address line 2 | |
|     | ci        | city | |
|     | co        | county | |
|     | cc        | country | |
|     | pc        | postcode | | |


Provider required contact details, `udc`, simply take the "phone type" as a key and the "number" as
the value. This could also contain address data. For example:

    "udc": { "Phone number": "+447777777777" }

Putting all this together including the availability attributes the resulting
JSON looks like this:

    {
      "sdate": "yyyy-mm-ddTHH:MM:SS+HH:MM",
      "edate": "yyyy-mm-ddTHH:MM:SS+HH:MM",
      "gsize": 5,
      "rcode": "rate-cat-code",
      "tcode": "time-of-day-code",
      "vcode": "VOUCHER",
      "seat": "123",
      "extras": [{
        xid: "xid-00",   //ID of this product
        nm: " T-shirt",  //name
        nt : "White and black T-shirts",  //brief note
        ct: "addon-0",   //category
        pr: { a: 20 }    //price for this product
       }],
      "rdcode": "rates_date-code",
      "pdcode": "payment_date-code",
      "gd": "55a3e159715c4111007682c1",
      "gid": "571a2fb41bfbad0f007971a4",
      "ssid": "571a2fb41bfbad0f007971a7",
      "gus": 1,
      "pus": 1,
      "usr": {
        "fn": "Joe",
        "sn": "Bloggs",
        "em": "joe@bloggs.com",
        "ad": [{
          "s1": "1 Princes Street",
          "s2": "",
          "ci": "Edinburgh",
          "co": "Midlothian",
          "cc": "UK",
          "pc": "EH1 1JB",
        }],
        "udc": {
          "Phone number": "+447777777777"
        }
      }
    }

The following `curl` request makes a `POST` to the `reserve` endpoint for the
user specified in the JSON body above:

    curl -X POST -u <appId>:<appKey> \
      -d '{"sdate": ...}' \
      https://papi-sandbox.makeitsocial.com/products/{xid}/reserve \
      -H "Content-Type: application/json"

Apart from the availability checking properties like `sdate`, payer information is
also required.  The `uid`, `gid` are for reference to the groups, and the `usr` object
contains names and address that pass on to the Provider for logging and
ticketing purpose, as well as the `udc` property which is required by the
Provider.

The successful response for a reservation contains the booking `id` which is
required for [confirming or cancelling a booking](/api-booking/README.md).

    { "ref_id": "123" }

A seat is now allocated for the user, and any further availability checks
with the same specification will fail.

However the reservation fails the response is:

    { "available": "false" }

