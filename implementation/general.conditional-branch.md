# ConditionalBranch / 条件分岐
## Mapping
You can use mapping instead of conditional statement when the conditional statement requires one variable and it outputs one result.

条件文期において、１つの変数を入力に１つの結果を出力する場合、マッピングを代わりに使用することができます。

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


## Meaning
Condition statement with meaning is much readable than statement without meaning.

複雑で難解な条件式を組み立てる代わりに、意味のある単位で条件を組み立てることで可読性が向上します。

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
if (
    target.isPlant
    && target.isTree
    && target.hasSeed
    && target.family === "Rosaceae"
    && target.color === "Red"
    && target.shape === "Round"
    && target.taste === "Sweet"
) {
    makeBANANAJuice(target);
}
```
</td><!-- beautiful --><td valign="top">

```js
const targetIsFruit = target.isPlant && target.isTree && target.hasSeed;
const targetLooksLikeApple = target.color === "Red" && target.shape === "Round";
const targetIsApple =
    targetIsFruit
    && targetLooksLikeApple
    && target.family === "Rosaceae"
    && target.taste === "Sweet"
;

if (targetIsApple) {
    makeAppleJuice(target);
}
```

---

```js
if (isApple(target)) {
    makeAppleJuice(target);
}
```
</td></tr>
</tbody></table>
