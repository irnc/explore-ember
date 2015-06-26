# Use bound attribute syntax instead of `bind-attr` 

```hbs
<li {{bind-attr class="rate.isActive:active"}}>
```

`bind-attr` was [deprecated in 1.13][1.13], use HTMLBars-style [attribute bindings][binding]
instead:

```hbs
<li class="{{if rate.isActive 'active'}}">
```

[1.13]: http://emberjs.com/blog/2015/06/12/ember-1-13-0-released.html#toc_notable-deprecations-in-1-13
[binding]: http://emberjs.com/blog/2015/02/07/ember-1-10-0-released.html#toc_bound-attribute-syntax
