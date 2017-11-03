# Ember.Component

## Ember.Component.extend

* actions
  * `this`
    * [`getAttr`](http://discuss.emberjs.com/t/mut-keyword-with-angle-bracket-component-attributes/8034/2)
  * return
    * [_To continue bubbling the action, you must return `true` from the handler_](http://guides.emberjs.com/v1.12.0/templates/actions/#toc_action-bubbling)
  * see also [`action` helper](helpers/action.md)

## Terms

* [use components for everything][future-proof]
* _data down, actions up_ paradigm
  * [stay away][future-proof] from two-way binding and mutability
  * [paradigm described for Ember](https://gist.github.com/samselikoff/1d7300ce59d216fdaf97#comment-1340897)
* angle bracket components [is likely to land in Ember 2.1][another-two]
  * also named "angle-bracket components"
  * [implemented in v1.13.0-beta.1](https://github.com/emberjs/ember.js/releases/tag/v1.13.0-beta.1)
* attributes  
  * [`this.attrs`][run-up-to-two] beginning with angle-bracket components
  * was introduced to split data coming into a component and internal state modifieble by component
* [routeable components][run-up-to-two] are under active development, [it will probably land in 2.1 at the earliest][another-two]
  * aka, "routable components"
  * [multiple asynchronous attributes][another-two]
  * [`attrs` hook][another-two]
* properties
  * `_state`
    * `preRender`, `inDOM`
    
[run-up-to-two]: http://emberjs.com/blog/2015/05/10/run-up-to-two-oh.html
[future-proof]: https://gist.github.com/samselikoff/1d7300ce59d216fdaf97
[another-two]: http://emberjs.com/blog/2015/05/24/another-two-oh-status-update.html

## Attrbiute

Component receives attrbitures.

```hbs
{{component-name first-attribute=property second-attribute="value"}}
```

See `didReceiveAttrs` lifecycle hook.

## Lifecycle hook

Lifecycle hook is [fired on component](http://emberjs.com/blog/2015/05/24/another-two-oh-status-update.html#toc_new-lifecycle-hooks).

Known lifecycle hooks:

- `didInsertElement`
- [`didUpdateElement`][run-up-to-two] landed in 1.13
- [`didUpdateAttrs`][another-two] landed in 1.13
- [`willUpdate`][another-two] landed in 1.13
- [`didUpdate`][another-two] landed in 1.13
- [`didReceiveAttrs`][another-two] landed in 1.13
- [`willRender`][another-two] landed in 1.13
- [`didRender`][another-two] landed in 1.13
- `valueDidChange`
- `disabledDidChange`

Is seams that lifecycle hook is actually an event.

Listening on events:

- http://emberjs.com/api/classes/Function.html#method_on
- http://emberjs.com/api/classes/Ember.html#method_on