##### Avaliability with limited tickets

An `availability` attribute can be added to the General Product attributes. It
describes a _List_ of reservation blocks. For example this could be 1 coach of
people.

**NB: ** this availability property does not involve seat selectin. For seat
selection, please use the `seatmaps` attribute.

| Req | Attribute        | Value       | Notes |
|:---:| ---------------- | ----------- | ----- |
|     | quantity         | how many tickets in this block | |
|     | reserve_duration | **default** is 2 hours | |
|     | id               | code used to identify this block | |
|     | rrule            | dates this block of tickets are available | | |

