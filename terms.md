* URL
  * path
  * hierarchy
  * query string
* convention over configuration
  * [Ember philosophy](http://www.ember-cli.com/#addon-conventions)
* Ember.Object
  * computed property
    * [improved syntax for computed properties with a setter](http://emberjs.com/deprecations/v1.x/#toc_computed-properties-with-a-shared-getter-and-setter)
    * computed property's descriptor
  * [observers](http://guides.emberjs.com/v1.12.0/object-model/observers/)
    * `function(){}.observes()`
    * `Ember.observer()`
  * `.get` function
    * exists because Ember supported IE8 prior to Ember 2.0
    * IE8 is only ES3 compatible, not ES5, so there is no `defineProperty`, thus the need for explicit `get` call
    * [`get` can be deprecated after 2.0][preparing-for-2.0]
* [run loop](deps/backburner.js/run-loop.md)
  * Ember.run.once
* route
  * [`controllerName`][query-params]
  * [`queryParams`][query-params]
    * [`refreshModel`][query-params]
  * [route hierarchy][query-params]
  * hooks
    * [`model`][query-params]
    * [`setupController`][query-params]
      * [landed in 1.0 RC4][1.0-rc4] (May 28, 2013)
* dependency injection
  * [services][run-up-to-two] landed in 1.10
  * [injected properties][ember-1.10.0] landed in 1.10
* [instance initializers][run-up-to-two] landed in 1.12
  * [initial implementation](https://github.com/emberjs/ember.js/pull/10256), January 23, 2015
  * [addition to ember-cli](https://github.com/ember-cli/ember-cli/issues/3159), April 2, 2015
* [FastBoot feature][another-two]
  * early version available as addon
    * [suitable for SEO][another-two]
  * rehydrating - [early in the 2.x release cycle][another-two]
* Engines feature are expected [to land in Canary early in the 2.x release cycle][another-two]
  * [Engines RFC](https://github.com/tomdale/rfcs/blob/master/active/0000-engines.md)
* resolver
  * https://github.com/ember-cli/ember-resolver
* ember-testing
  * [introduced in RC3][1.0-rc4] (1.0 RC3)

---

## templates

* block
  * template inside of a block
  * [block params][run-up-to-two]
  * [chained else][run-up-to-two]
* helpers
  * context-switching form
    * [don't use it][future-proof]
  * [context-shifting helpers][another-two] should be replaced with
    * #with item as |i|
    * #each list as |item|
    * {{#each}}
      * can have matching {{else}}
  * block parameters
    * http://emberjs.com/blog/2015/02/07/ember-1-10-0-released.html#toc_block-params
    * http://handlebarsjs.com/block_helpers.html#bloack-params
    * https://github.com/emberjs/rfcs/blob/master/complete/0002-block-params.md
  * is it a shorthand for "view helper"?
  * {{input}} - Ember.TextField
  * bindings-aware
    * data attributes
      * By default, view helpers do not accept data attributes, see http://guides.emberjs.com/v1.11.0/templates/binding-element-attributes/
  * can be used as a block expression
    * {{#if}}{{/if}}
    * {{#link-to}} - Ember.LinkView
  * inline form
    * {{link-to 'Title' 'index'}}
  * arguments
    * additional arguments
  * options
    * what is the difference with arguments?
    * e.g. replace=true option on link-to helper
  * component helper, [landed in 1.11][preparing-for-2.0]
    * `{{component componentName}}`
* bound attribute syntax, [landed in 1.11][preparing-for-2.0]
  * now `<a href="{{url}}">` is preferred way instead of old `<a {{bind-attr href=documentUrl}}>`
* [inline if][preparing-for-2.0], [landed in 1.11][preparing-for-2.0]
* [each with index][preparing-for-2.0], [landed in 1.11][preparing-for-2.0]
  * `{{#each people as |person index|}}`
* comments
  * `{{! Comment goes here }}`
* Glimmer rendering engine
  * [massive performance improvement][preparing-for-2.0], landed in 1.13.0

---

## `Router`

* [Use `this.route` instead of `this.resource` in `Router.map`][future-proof]
  * [_Couple this with pods and you'll quickly understand why you don't want to use `resource` anymore - your directory structure in `pods` will now mirror the view hierarchy of your UI._][future-proof]
* [named substates](http://emberjs.com/blog/2015/03/27/ember-1-11-0-released.html#toc_named-substates), [landed in 1.11][preparing-for-2.0]
* [loading and error substates](http://guides.emberjs.com/v1.12.0/routing/loading-and-error-substates/)
  * [`error` event](http://emberjs.com/api/classes/Ember.Route.html#event_error)
* `transition` object
  * `Transition` class undocumented
  * `#abort()`
  * `#retry()`
  * can be [stored for retry in future](http://guides.emberjs.com/v1.10.0/routing/preventing-and-retrying-transitions/)
* Route
  * `willTransition` hook
  * `transitionTo`
 
---

# pods

* [use pods][future-proof]

---

## ember-cli

* https://github.com/ember-cli/ember-cli
* always [use Ember CLI][future-proof]
* see [deps/ember-cli/terms.md](deps/ember-cli/terms.md)

---

## ember-data

* [async](http://emberjs.com/blog/2014/03/18/the-road-to-ember-data-1-0.html#toc_async-relationships)
  * relationships
    * links

---

## Deprecated

### controllers

* [expected to be deprecated in 1.13][preparing-for-2.0], to be replaced by routeable components
* `Ember.Controller`
  * should be used [only on route level for receiving data from the route][future-proof]
    * [fetch data in your route, and set it on `attrs` on your top-level controller][future-proof]
      * at April 16, advice was changed to propose setting normal properties on controller and use `Ember.RSVP.hash`
  * `Ember.ArrayController` is not deprecated, but [adwised to be replaced with `Ember.Controller`][future-proof]
  * `Ember.ArrayController.itemController` is not deprecated, but [is not future proof][future-proof]
  * [`Ember.ObjectController` is deprecated](http://emberjs.com/deprecations/v1.x/#toc_objectcontroller)
* controller has a property
* [route-driven controllers][query-params]
* [`queryParams`][query-params]
  * work to make it possible to [move query parameters fully to routes][another-two], is ongoing
* needs, deprecation planned in 1.12
  * use `Ember.inject`

### views

* [don't use views][future-proof]
* [replace views + controllers with components][future-proof]

[query-params]: http://guides.emberjs.com/v1.10.0/routing/query-params/
[run-up-to-two]: http://emberjs.com/blog/2015/05/10/run-up-to-two-oh.html
[another-two]: http://emberjs.com/blog/2015/05/24/another-two-oh-status-update.html
[ember-1.10.0]: http://emberjs.com/blog/2015/02/07/ember-1-10-0-released.html
[ember-1.11.0]: http://emberjs.com/blog/2015/03/27/ember-1-11-0-released.html
[1.0-rc4]: http://emberjs.com/blog/2013/05/28/ember-1-0-rc4.html
[future-proof]: https://gist.github.com/samselikoff/1d7300ce59d216fdaf97
[preparing-for-2.0]: https://www.youtube.com/watch?v=wsydQzQF4Ww
