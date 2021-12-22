# Loop
## for ... of
Self explanatory, it isn't a great improvement but it isn't little advantage over using `i` and `j`.

説明は不要でしょう。目覚ましい改善ではないですが、 `i` と `j` を使わずに済むことは少なくない利点です。

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
for (let i = 0; i < fruits.length; i++) {
    const fruit = fruits[i];
    for (let j = 0; j < cameras.length; i++) {
        const camera = cameras[j];
        camera.takePictureOf(fruit);
        camera.savePicture(fruit.name);
    }
}
```
</td><!-- beautiful --><td valign="top">

```js
for (const fruit of fruits) {
    for (const camera of cameras) {
        camera.takePictureOf(fruit);
        camera.savePicture(fruit.name);
    }
}
```
</td></tr>
</tbody></table>


## Object.entries
It transform an object into key-value pair array. It enables you to use any array function you want.

オブジェクトをキー・バリューの配列にできます。配列になるということは、配列用の関数すべてのサポートを得られるということです。

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const obj = {
    a: "BANANA", b: "Blueberry",
    c: "Cherry", : d: "Durian",
    e: "Elderberry",
};

const result = [];
for (const k in obj) {
    result.push({
        id: k,
        name: obj[k],
    });
}
```
</td><!-- beautiful --><td valign="top">

```js
const obj = {
    a: "BANANA", b: "Blueberry",
    c: "Cherry", : d: "Durian",
    e: "Elderberry",
};

const result = [];
for (const [k, v] of Object.entries(obj)) {
    result.push({
        id: k,
        name: v,
    });
}
```

---

```js
const obj = {
    a: "BANANA", b: "Blueberry",
    c: "Cherry", : d: "Durian",
    e: "Elderberry",
};
const result = Object.entries(obj)).map(([k, v]) => ({
    id: k,
    name: v,
}));
```
</td></tr>
</tbody></table>
