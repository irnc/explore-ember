# XHR initiated code execution

- jQuery callbacks (see explore-jquery/ajax.md)
- `hash.success` from private `ajax` function of `RESTAdapter`
- call to `Ember.run` for resolving or rejecting the promise

# Backburner

- see `Queue#flush` which suggests to set `Ember.run.backburner.DEBUG = true;`