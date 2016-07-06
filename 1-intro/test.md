#### Quick test

If you would like to test whether you can access our raw API directly you can
use the [curl](https://curl.haxx.se/) tool from your computer's terminal, to talk to our sandbox service.

The command below uses the `-u` switch to specify the **u**ser authentication
and make an HTTP GET request to our sandbox URL endpoint, to list your Providers.

    curl -u <APPID>:<KEY> https://papi-sandbox.makeitsocial.com/providers

Assuming you have credentials such as:

    APPID = joe@bloggs.com
    KEY   = 11111111111111111111111111111111

Then when you execute the `curl` command from your computer's terminal (ignore
the `$`):

    $ curl -u joe@bloggs.com:11111111111111111111111111111111 https://papi-sandbox.makeitsocial.com/providers

The system should return empty list of Providers (as we haven't created any
yet). Something like this:

    []

It should not return any error messages, such as:

    {"message": "Internal server error"}

Which could be due to your `APPID` or `KEY` not being correct.

