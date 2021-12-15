# Array
## Find
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const apple = null;
for (const fruit of fruits) {
    if (fruit.name === "apple") {
        console.log("BANANA!", fruit);
        apple = fruit;
        break;
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
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const apples = [];
for (const fruit of fruits) {
    if (fruit.name === "apple") {
        console.log("BANANA!", fruit);
        apples.push(fruit);
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
const apples = fruis.filter(fruit => fruit.name === "apple");
```
</td></tr>
</tbody></table>


## Map

## FlatMap

## Reduce
