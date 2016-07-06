##### Booking webhooks

The Product can specify how to do the booking. The booking engine can either be
`local` or use [Webhooks](https://en.wikipedia.org/wiki/Webhook)

If the engine is `local` then the following JSON can be used:

    "booking": {
      "engine": "local"
    }

However if the engine is `hooked` then you will need to describe the Webhook in
the JSON:

    "booking": {
      "engine": "hooked",
      "webhooks": {
        "availability": "http://check.availability.com/my-product",
        "prepayment": "http://client.com/reservation/endpoint",
        "postpayment": "http://client.com/confirmation/endpoint",
        "cancel": "http://client.com/cancel/endpoint",
        "shared_secret": "qw3r2ysd8cc9rr",
      }
    }

The definitions of the table looks like this:

| Req | Attribute      | Value       |
|:---:| -------------- | ----------- |
|     | engine         | this value can be either `local` or `hooked` |
|     | webhooks       | if engine=`hooked` then use a JSON object to define the Webhook |

Webhook attribute definitions:

| Req | Attribute      | Value       |
|:---:| -------------- | ----------- |
|     | availability   | URL for availability checking |
|     | prepayment     | reservation endpoint |
|     | postpayment    | confirmation of booking endpoint |
|     | cancel         | cancel a booking endpoint |
|     | shared_secret  | key for hashing the data |


