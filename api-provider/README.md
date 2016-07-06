# Provider

A Provider is an organisation or company that provides Products.

To create a Provider using the _Make it Social_ API, you will need send a JSON
document to our "create Providers" API endpoint, with your authentication
credentials. Please ensure that you have already set these up, see the [quick set
up](/1-intro/README.md) page.


## Experimenting with the API

Using the `curl` tool against our API is an excellent way to get a feel for how
it works. The following sections describe how to interact with our API from your
computer's terminal. These examples use our API sandbox URL, if you wish to make
requests against a production system, you will need to change the URL
accordingly.
Finally these experiments assume you have credentials such as:

    APPID = joe@bloggs.com
    KEY   = 11111111111111111111111111111111


