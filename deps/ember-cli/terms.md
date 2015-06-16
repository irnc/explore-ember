# ember-cli

* https://github.com/ember-cli/ember-cli
* always [use Ember CLI][future-proof]
* [ember-cli/ARCHITECTURE.md](https://github.com/ember-cli/ember-cli/blob/master/ARCHITECTURE.md)
* `models` directory
  * 
* `preprocessors` module
* [`EmberApp` constructor](https://github.com/ember-cli/ember-cli/blob/master/lib/broccoli/ember-app.js)
  * options
    * trees
  * `project`
    * `name()`
  * `env`
    * `'production'`
  * `registry`
  * `trees`
* blueprints
  * [addons using private npm modules](https://github.com/ember-cli/ember-cli/issues/4256)
* options
  * [`storeConfigInMeta`](https://github.com/ember-cli/ember-cli/pull/2298) allows to get _equality between builds where only the config changes_.
  
## Addons

* initially [implemented by Robert Jackson](https://github.com/ember-cli/ember-cli/pull/1025), June 13, 2014
* [Introducing Ember CLI Addons](https://dockyard.com/blog/2014/06/24/introducing_ember_cli_addons) by Robert Jackson, June 24th, 2014
* http://hashrocket.com/blog/posts/a-compendium-of-hooks-in-embercli
    
## Writing addons

* `package.json`
  * `keywords: [ 'ember-addon' ]`
* `index.js`
  * should export plain object with `included` and `treeFor` properties
  * initial implementation exported constructor which build such object

### Experience, `ember-cli-super-number`

See [Building Ember CLI Addons Simply][jj-addon-post] blog post by Jonathan
Jackson describing how [ember-cli-super-number][] was converted to addon.

[jj-addon-post]: http://hashrocket.com/blog/posts/building-ember-addons
[ember-cli-super-number]: https://github.com/rondale-sc/ember-cli-super-number

### Converting libraries to Ember CLI addons

* https://gist.github.com/kristianmandrup/ae3174217f68a6a51ed5
* written on September 28th, 2014
