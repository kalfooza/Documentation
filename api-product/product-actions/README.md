# Product Availability & Reservations

The Product API provides actions for checking availability and making a reservation.

The `products/{id}/availability` and `products/{id}/reserve` endpoints both
`POST` a JSON document containing the following attributes:

| Req | Attribute | Value       | Notes |
|:---:| --------- | ----------- | ----- |
| *   | sdate     | user selected start date, in ISO-format | |
|     | edate     | user selected end date if applicable | |
|     | gsize     | group size, number of members in the group | |
|     | rcode     | `rate_category` code for the selected price | |
|     | tcode     | user selected time-of-day `id`/code if applicable | |
|     | vcode     | voucher code, if any | |
|     | seat      | seat `id` if any | |
|     | extras    | list of product `ids` for `addons` | |
|     | rdcode    | user selected `rates_date` code if applicable | |
|     | pdcode    | user payment date code if applicable | |
|     | gdcode    | group-discount code if applicable | | |

The JSON document looks like this:

    {
      "sdate": "yyyy-mm-ddTHH:MM:SS+HH:MM",
      "edate": "yyyy-mm-ddTHH:MM:SS+HH:MM",
      "gsize": 5,
      "rcode": "rate-cat-code",
      "tcode": "time-of-day-code",
      "vcode": "VOUCHER",
      "seat": "123",
      "extras": ["111", "222"],
      "rdcode": "rates_date-code",
      "pdcode": "payment_date-code",
      "gdcode": "group_discount-code",
    }


