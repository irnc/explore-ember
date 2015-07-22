# `Ember.Application`

* [Registry](https://github.com/emberjs/ember.js/pull/9981)
* April 9, [RFC to encapsulate and make Registry private](https://github.com/emberjs/rfcs/pull/46) to Application

## `.initializer`

* http://emberjs.com/api/classes/Ember.Application.html#toc_initializers

## `#register`

* http://emberjs.com/api/classes/Ember.Application.html#method_register

### `options`

* `singleton`
* `instantiate`

## `/app` directory

### `./initializers`

* initializers are loaded using [ember-load-initializers](https://github.com/ember-cli/ember-load-initializers)
  * which calls `.initializer` or `.instanceInitializer` functions on passed `Application` constructor
* bundling `ember-load-initializers` into a build happens on [ember-cli side](https://github.com/ember-cli/ember-cli/blob/v1.13.1/lib/broccoli/ember-app.js#L268)
* loading initializers into an app at [app/app.js#L3](https://github.com/ember-cli/ember-cli/blob/v1.13.1/blueprints/app/files/app/app.js#L3)

## Initializers

### When initializers are run?

* https://github.com/emberjs/ember.js/issues/4280#issuecomment-33889788

### Best practices on initializers

* https://github.com/emberjs/ember.js/issues/4280#issuecomment-48088291
