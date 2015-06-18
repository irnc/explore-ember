## Incorrect behaviour

Given `npm-shrinkwrap.json` exists with `{ ember-browserify: "1.0.0" }`, running `ember install ember-browserify` with intention to update to `1.0.1` results in following change to `package.json`:

```diff
-    "ember-browserify": "1.0.0",
+    "ember-browserify": "https://registry.npmjs.org/ember-browserify/-/ember-browserify-1.0.0.tgz",
```

Proper command flow should be:

```sh
rm npm-shrinkwrap.json &&
ember install ember-browserify &&
npm shrinkwrap
```
