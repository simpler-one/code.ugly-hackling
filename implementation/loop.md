# Loop
## ForEach

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
</td></tr>
<tr><!-- ugly --><td valign="top">
</td><!-- beautiful --><td valign="top">

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
