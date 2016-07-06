#### Details of Product JSON Sections

Products vary in the way they are priced, avaliability, group sizing, etc. Our
API is flexible enough to handle many variations, the main ones are outlined
below.

##### General properties

The general properties are the core properties that define a product.

| Req | Attribute     | Value       | Notes |
|:---:| ------------- | ----------- | ----- |
|     | _id           | MongoDB _id | |
| *   | xid           | Product-specific ID as a string | |
| *   | name          | Product name | |
|     | url           | URL to product web page to show a user more information | |
| *   | image         | URL to the Provider's Product image | |
|     | description   | Brief description of the product | |
| *   | provider_id   | `xid` of the Provider | |
|     | pay_id        | Seller ID on GroupPay | |
|     | type          | Product category | | |


