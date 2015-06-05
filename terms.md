* URL
  * path
  * hierarchy
  * query string
* convention over configuration
  * [Ember philosophy](http://www.ember-cli.com/#addon-conventions)
* ember-cli
  * https://github.com/ember-cli/ember-cli
  * options
    * [`storeConfigInMeta`](https://github.com/ember-cli/ember-cli/pull/2298) allows to get _equality between builds where only the config changes_.
* application
  * [Registry](https://github.com/emberjs/ember.js/pull/9981)
  * April 9, [RFC to encapsulate and make Registry private](https://github.com/emberjs/rfcs/pull/46) to Application
* Ember.Object
  * computed property
    * [improved syntax for computed propeties with a setter](http://emberjs.com/deprecations/v1.x/#toc_computed-properties-with-a-shared-getter-and-setter)
    * computed property's descriptor
  * [observers](http://guides.emberjs.com/v1.12.0/object-model/observers/)
    * `function(){}.observes()`
    * `Ember.observer()`
* run loop
  * Ember.run.once
* template
  * block
    * template inside of a block
    * [block params][run-up-to-two]
    * [chained else][run-up-to-two]
  * helper
    * [context-shifting helpers][another-two]
      * #with item as |i|
      * #each list as |item|
      * {{#each}}
        * can have matching {{else}}
    * block parameters
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
* components
  * angle bracket components [is likely to land in Ember 2.1][another-two]
    * also named "angle-bracket components"
    * [implemented in v1.13.0-beta.1](https://github.com/emberjs/ember.js/releases/tag/v1.13.0-beta.1)
  * attributes  
    * [`this.attrs`][run-up-to-two] beginning with angle-bracket components
  * lifecycle hooks
    * `didInsertElement`
    * [`didUpdateElement`][run-up-to-two] landed in 1.13
    * [`didUpdateAttrs`][another-two] landed in 1.13
    * [`willUpdate`][another-two] landed in 1.13
    * [`didUpdate`][another-two] landed in 1.13
    * [`didReceiveAttrs`][another-two] landed in 1.13
    * [`willRender`][another-two] landed in 1.13
    * [`didRender`][another-two] landed in 1.13
    * `valueDidChange`
    * `disabledDidChange`
  * [routeable components][run-up-to-two] are under active development, [it will probably land in 2.1 at the earliest][another-two]
    * [multiple asynchronous attributes][another-two]
    * [`attrs` hook][another-two]
* controller
  * controller has a property
  * [route-driven controllers][query-params]
  * [`queryParams`][query-params]
    * work to make it possible to [move query parameters fully to routes][another-two], is ongoing
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

[query-params]: http://guides.emberjs.com/v1.10.0/routing/query-params/
[run-up-to-two]: http://emberjs.com/blog/2015/05/10/run-up-to-two-oh.html
[another-two]: http://emberjs.com/blog/2015/05/24/another-two-oh-status-update.html
[ember-1.10.0]: http://emberjs.com/blog/2015/02/07/ember-1-10-0-released.html
[1.0-rc4]: http://emberjs.com/blog/2013/05/28/ember-1-0-rc4.html
