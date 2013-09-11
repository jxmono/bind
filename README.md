bind (for mono)
===============

Bind content and events to the DOM and create DOM Elements.

### Change Log

##### v0.1.5

* the filters now receive the original value (not a string representation of it)
* the `html` bind object will convert values to strings and `undefined` and `null` to empty strings

##### v0.1.4

* added delegated event support in the `on` bind configuration:

```json
{
    "target": ".myDynamicAddedElement",
    "on": [{
        "name": "click",
        "delegated": true,
        "handler": "myHandler"
    }]
}
```

##### v0.1.3
* Fixed major issue in handling functions with arguments.

##### v0.1.2

* added global namespaced function support:

```json
{
    "target": ".myClass",
    "on": [{
        "name": "click",
        "handler": "global.function.name"
    }]
}
```

where `global.function.name` can be either a **module** namespaced function or a **global** namesaced function

* added `args` support for `on` handlers:

```json
{
    "target": ".myClass",
    "on": [{
        "name": "click",
        "handler": {
            "name": "globalFunctionName",
            "args": ["an argument"]
        }
    }]
}
```

The `dataContext` will be appended to the given argument array.

##### v0.1.1

* added default value support in `source` value computations:

```json
{
    "html": {
        "source": "key.from.data.context",
        "default": "default value if the source is not found"
    }
}

```
