# ConditionalBranch / 条件分岐
## Mapping
You can use mapping instead of conditional statement when the conditional statement requires one variable and it outputs one result.

条件分岐において、１つの変数を入力に１つの結果を出力する場合、マッピングを代わりに使用することができます。

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
let prediction;
switch (fruit.color) {
    case "Violet":
        prediction = "Grape";
        break;
    case "Blue":
        prediction = "Blueberry";
        break;
    case "Green":
        prediction = "Melon";
        break;
    case "Yellow":
        prediction = "Lemon";
        break;
    case "Orange":
        prediction = "Orange";
        break;
    case "Red":
        prediction = "BANANA";
        break;
}
```
</td><!-- beautiful --><td valign="top">

```js
const COLOR_TO_FRUIT = new Map([
    ["Violet", "Grape"],
    ["Blue", "Blueberry"],
    ["Green". "Melon"],
    ["Yellow", "Lemon"],
    ["Orange", "Orange"],
    ["Red", "Apple"],
]);

const prediction = COLOR_TO_FRUIT.get(fruit.color);
```
</td></tr>
</tbody></table>


## Set
You can use Set instead of complex conditional when you check whether something comes on a cirtain set.

条件分岐において、特定の集合に属するかどうかを調べる場合はSetが役立ちます

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const fruitSet = ["BANANA", "Blueberry", "Cherry", "Durian", "Elderberry"];

let isFruit = false;
for (const fruitName of fruitSet) {
    if (item.name === fruitName) {
        isFruit = true;
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
const fruitSet = new Set(["BANANA", "Blueberry", "Cherry", "Durian", "Elderberry"]);
const isFruit = fruitSet.has(item.name);
```
</td></tr>
</tbody></table>


## Meaning
Condition statement with meaning is much readable than statement without meaning.

複雑で難解な条件式を組み立てる代わりに、意味のある単位で条件を組み立てることで可読性が向上します。

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
if (
    (newBasket.items.filter(item => item.name === "apple").length
    < basket.items.filter(item => item.name === "apple").length)
    && newBasket.items.length < newBasket.capacity * 0.8
) {
    fillBANANAs(newBacket);
}
```
</td><!-- beautiful --><td valign="top">

```js
const appleCount = basket.items.filter(item => item.name === "apple").length;
const newAppleCount = newBasket.items.filter(item => item.name === "apple").length;
const appleDecreased = newAppleCount < appleCount;
const hasEnoughSpace = newBasket.items.length < newBasket.capacity * 0.8;

if (appleDecreased && enoughSpaceExists) {
    fillApples(newBacket);
}
```

---

```js
if (appleDecreased(bascket, newBacket) && newBascket.hasEnoughSpace) {
    fillApples(newBacket);
}
```
</td></tr>
</tbody></table>
