# Listing Providers

To list all the Providers registered against your `APPID`, simply use `curl` to
call the `/providers` API endpoint.

The raw command is:

    curl -u <APPID>:<KEY> https://papi-sandbox.makeitsocial.com/providers

Then when you execute the `curl` command from your computer's terminal (ignore
the `$`):

    $ curl -u joe@bloggs.com:11111111111111111111111111111111 https://papi-sandbox.makeitsocial.com/providers

If there are Providers they will be listed in your terminal as a JSON document.
Otherwise an empty list is returned:

    []

