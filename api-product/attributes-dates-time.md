##### Dates and time

A **required** `date_range` attribute must be added to the General Product attributes. It contains the following JSON attributes that define pricing.

| Req | Attribute       | Value       | Notes |
|:---:| --------------- | ----------- | ----- |
| *   | start           | start date in ISO format | |
|     | end             | end date in ISO format | |
|     | duration        | days or hours for each instance | |
|     | selectability   | start and end date open or fixed | |
|     | min_days        | minimum number of days to select | |
|     | max_days        | maximum number of days to select | |
|     | rrule           | RRule to specify recurrent dates | |
|     | times           | list of times in a day | | |

