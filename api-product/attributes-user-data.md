##### User data capture

Data can be captured from the customer using standard HTML forms, and associated
with a Product using the `data\_capture` attribute, which defines a list of form
field types.

    "data_capture": [
      {
        "name": "Passport",
        "type": "number",
        "required": true,
        "options": "list",
        "validator": "/[0-9]+/"
      },
      { ... }
    ]

This table shows detailed information about the attributes.

| Req | Attribute      | Value       | Notes |
|:---:| -------------- | ----------- | ----- |
|     | name           | name of the field, e.g. "Passport" | |
|     | type           | data type, "text", "number" | |
|     | required       | true if this is required | |
|     | options        | list of choices if type="list" | |
|     | validator      | Regular expression patter to validate the answer | | |

