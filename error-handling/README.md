[`error` substate][substates] would allow to handle only errors from `model` hooks, error occured while evaluating computed property in controller would not be catched by `error` substate.

* [loading and error substates](http://guides.emberjs.com/v1.12.0/routing/loading-and-error-substates/)
  * [`error` event](http://emberjs.com/api/classes/Ember.Route.html#event_error)

[substates]: http://guides.emberjs.com/v2.1.0/routing/loading-and-error-substates/

# Error thrown on computed property evaluation

Best practice:

If exception can be thrown when getting computed property, handle it right in the getter function.

Rationale:

There is no other API which would allow to handle exceptions from computed properties.

Details:

Error thrown at computed property would not be catched (see `finally` block at `Backburner.end`, it is the nearest point where Ember intercept exceptions, it is so far away from controller, that there is no way to delegate this unhandled error back to it).
