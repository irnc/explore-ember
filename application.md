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
* this module is loaded at https://github.com/ember-cli/ember-cli/blob/v1.13.1/lib/broccoli/ember-app.js#L268
