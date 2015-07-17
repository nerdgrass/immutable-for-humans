# Human Docs
## `fromJS()`
Converts plain JS[objects](BASIC JS DOCS) and/or [arrays](BASIC JS DOCS) to Immutable [Maps](IMMUTABLE MAPS) and [Lists](IMMUTABLE LISTS).

```js
// Basic Usage, ES5
var myMutableObject = {
    exampleString: "I'm a string!",
    exampleStringArray: ["a", "b", "c"],
    exampleIntegerArray: [1, 2, 3, 4],
    exampleBoolean: true,
}
var myImmutableObject = Immutable.fromJS(muMutableObject)

// Proof - String
var stringExampleValue = myImmutableObject.get('exampleString')
console.log(getString) // returns "I'm a string!"

// Proof - Array
var arrayExample = myImmutableObject.get('exampleStringArray')
arrayExample.map(function(arrayItem) {
    console.log(arrayItem) // returns array item's value
})

// Proof - Boolean
var getBooleanValueExample = function(valueTested) {
    if (valueTested === true) {
        console.log(valueTested + ' is true.')
    } else if (valueTested === false) {
        console.log(valueTested + ' is false.')
    } else {
        console.log(valueTested + ' was not a boolean value!')
    }
}
var exampleBooleanValue = myImmutableObject.get('exampleBoolean')
getBooleanValueExample(exampleBooleanValue)// returns true

```

# Original Docs
## `fromJS()`
Deeply converts plain JS objects and arrays to Immutable Maps and Lists.
`fromJS(json: any, reviver?: (k: any, v: Iterable<any, any>) => any): any`

### DISCUSSION
If a `reviver` is optionally provided, it will be called with every collection as a Seq (beginning with the most nested collections and proceeding to the top-level collection itself), along with the key refering to each collection and the parent JS object provided as this. For the top level, object, the key will be `""`. This `reviver` is expected to return a new Immutable Iterable, allowing for custom convertions from deep JS objects.

This example converts JSON to List and OrderedMap:
```js
Immutable.fromJS({a: {b: [10, 20, 30]}, c: 40}, function (key, value) {
  var isIndexed = Immutable.Iterable.isIndexed(value);
  return isIndexed ? value.toList() : value.toOrderedMap();
});

// true, "b", {b: [10, 20, 30]}
// false, "a", {a: {b: [10, 20, 30]}, c: 40}
// false, "", {"": {a: {b: [10, 20, 30]}, c: 40}}
```
If `reviver` is not provided, the default behavior will convert Arrays into Lists and Objects into Maps.

`reviver` acts similarly to the [same parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse#Example.3A_Using_the_reviver_parameter) in `JSON.parse`.

`Immutable.fromJS` is conservative in it's conversion. It will only convert arrays which pass `Array.isArray` to `Lists`, and only raw objects (no custom prototype) to Map.

`"Using the reviver parameter"`