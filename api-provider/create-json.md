### Create Providers JSON...

Our JSON document describes all the attributes the _Make it Social_  `/providers` API endpoint needs to create a new Provider.
Notice the `pay_id` below, this is where you need to enter your `pay_id` (`sid`) as
mentioned in the [Quick set up](/1-intro/quick.md) page.
Additionally you must ensure that the `xid` value is unique.

    {
     "xid": "democlient_4",
     "name": "Demo Client",
     "description": "Fun company",
     "email": "a@b.c",
     "terms": "http://terms_and_conditions/",
     "logo": "https://makeitsocial.com/media/organisers/badlamb.png",
     "booking": {
         "engine": "local",
         "webhook": "https://client_webhook/",
         "hashkey": "used_to_hash_content"
     },
     "payment": {
         "method": "mispay",
         "sid": "12345678",
         "live": false
     }
    }


_Figure 1: example Provider JSON document_
