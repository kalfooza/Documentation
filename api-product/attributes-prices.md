##### General: prices

A **required** `prices` attribute must be added to the General Product attributes. It contains the following JSON attributes that define pricing.

| Req | Attribute       | Value       | Notes |
|:---:| --------------- | ----------- | ----- |
| *   | currency        | e.g. GBP, EUR, USD | |
| *   | base            | base/default/full/display price | |
|     | type            | per-person or per-group | |
|     | unit            | per-day, or per-event | |
|     | enquire         | booking Provider's server | |
|     | deposit         | deposit amount | |
|     | prepay          | required if pre-authorisation | |
|     | deadline        | deadline for booking, it can be fixed as 'yyyy-mm-dd' or a number of days before the starting date | |
|     | min_group_price | minimum amount for per-group payment | |
|     | url             | deeplink url of Provider | |
|     | fee             | booking fee - this will automatically be added to the amount charged to a user | | |

