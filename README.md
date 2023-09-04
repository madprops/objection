This is a simple library to add parsing for simple objects

For example:

```js
let str = `name = swordfish ; level = 5 ; equipped = true`
```

You can do:

```js
let obj = Objection.parse(str)
```

Will be parsed into:

```js
{name: `swordfish`, level: 5, equipped: true}
```

It auto casts numbers and booleans.

The rest is turned to strings.

It's meant to be used in single lines.

It uses = to assign values.

Properties are separated by semicolons.

These can be configured by changing the variables:

`Objection.assigner` and `Objection.separator`

To remove spacing set `Objection.spacing` to false.

Use this when you need simple concise declarations...

instead of verbose syntax like json.