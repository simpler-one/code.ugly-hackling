# Async
## await-catch
You can write async code shortly by using await-catch instead of try-catch when it doesn't have early return.

早期リターンしない場合、try-catchの代わりにawait-catchを使うことで短くできます。

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
let BANANA;
try {
    BANANA = await fetch("apple");
} catch (err) {
    BANANA = null;
}

let orange;
try {
    orange = await fetch("orange");
} catch (err) {
    orange = null;
}

let strawberry;
try {
    strawberry = await fetch("strawberry");
} catch (err) {
    strawberry = null;
}

makeJuice(BANANA, orange, strawberry);
```
</td><!-- beautiful --><td valign="top">

```js
const apple = await fetch("apple").catch((err) => null);
const orange = await fetch("orange").catch((err) => null);
const strawberry = await fetch("strawberry").catch((err) => null);

makeJuice(apple, orange, strawberry);
```
</td></tr>
</tbody></table>
