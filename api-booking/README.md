# Bookings

A booking acts on a Product.

The `/bookings` endpoint specifies actions that can be carried out on a booking.
Booking actions require a booking `id`, this is returned in the JSON response
when the `/products/{id}/reserve` endpoint is called. Please see the Product API documentation for more details.

## Bookings Confirm

The booking can be **confirmed** using the `/bookings/{id}/confirm` endpoint.
This is an HTTP `PUT` request that contains the JSON body of amount.
**NB:** The value of `amount` is the **paid pre-authorised amount (and if applicable the discount should have been applied).**

For example if the Leader paid a pre-authorised amount of 100 then, and met a
threshold of 5 group bookings to get a 10% discount. This amount would be 90.
If the Leader did **not** meet the threshold of 5 bookings, then the amount
would be 100.

    {
      "amount": 90
    }

The API request will look like this:

    curl -X PUT -u <appId>:<appKey> \
      -d '{"amount": <number>}' \
      https://papi-sandbox.makeitsocial.com/bookings/{id}/confirm \
      -H "Content-Type: application/json"


## Bookings Cancel

A booking can be cancelled sending an HTTP `PUT` request to the `/bookings/{id}/cancel` endpoint.

The booking `id` is the retrieved from the `/products/{id}/reserve` endpoint
body response.

The API request will look like this:

    curl -X PUT -u <appId>:<appKey> \
      https://papi-sandbox.makeitsocial.com/bookings/{id}/cancel \
      -H "Content-Type: application/json"


