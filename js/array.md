# Array
## Find
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const result = [];
for (const fruit of fruits) {
    if (fruit.name === "apple") {
        console.log("BANANA!", fruit);
        result.push(fruit);
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
const apples = fruis.filter(fruit => fruit.name === "apple");
```
</td></tr>
</tbody></table>


## Filter

## Map

## FlatMap

## Reduce
