# Mithril-Myth

Forked from [mithril](http://lhorie.github.io/mithril)

## Differences

- Adds a m.debug capture of controllers as they are instantiated
- Different m.route strategy
- Different m.prop strategy

### m.route

In mithril, a route change will redraw everything.
In mithril-myth, a route change is treated only as a m.redraw.strategy('diff').

### m.prop

In mithril-myth m.prop everything is a function.

It is the same as mithril in this simple case:
```
let foo = m.prop('foo')
foo() // 'foo'
```

The difference is when nested, mithril's m.prop would not require this additional function call:
```
let foo = m.prop(['foo'])
foo()[0]() // 'foo'
```