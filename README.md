This is a simple library to add parsing for simple objects.

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

And in reverse:

```js
let str = Objection.stringify(obj)
```

It auto-casts numbers and booleans. (optional).

The rest is turned to strings.

It's meant to be used in single lines.

It uses = to assign values.

Properties are separated by semicolons.

These can be configured by changing the variables:

`Objection.assigner` and `Objection.separator`.

To remove spacing on `stringify` set `Objection.spacing` to false.

Use this when you need simple concise declarations...

instead of verbose syntax like json.

Both functions accept a second argument, an object called `args`.

You can use this to override `Objection.assigner`, `Objection.separator`, and `Objection.spacing`.

For example:

```js
Objection.stringify(obj, {assigner: `:`, separator: `@`, spacing: false})
```

You don't need to provide all of them, just what you need.

You can also disable bool and number casting with:

`Objection.cast_bool` and `Objection.cast_number`.

You can also use those in the `args` argument.

You can escape assigner and separator chars using two `\`:

```js
Objection.parse(`math = 2 + 2 \\= 4`)
```

It will auto un/escape on parse and stringify.