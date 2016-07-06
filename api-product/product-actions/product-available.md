## Product Availability

A Product can be queried to determine whether it is available for reservation.

The API request will look like this:

    curl -X POST -u <appId>:<appKey> \
      -d '{"sdate": ...}' \
      https://papi-sandbox.makeitsocial.com/products/{xid}/available \
      -H "Content-Type: application/json"

If the Product is "available" for booking, then the JSON response is:

    {
      "available": true,
      "final": 99
    }

**NB** The **final** value is the total price.

If the Product is "unavailable" for booking, then the JSON response is:

    {
      "available": false,
    }

