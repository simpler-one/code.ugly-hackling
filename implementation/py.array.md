# Array
## Copy(shallow)
<table><tbody>
<tr><!-- ugly --><td valign="top">

```python
copy = []
for item in array:
    copy.append(item)
```
</td><!-- beautiful --><td valign="top">

```python
copy = array.copy()
```
---
```python
copy = array[:]
```
</td></tr>
</tbody></table>


## Concat
<table><tbody>
<tr><!-- ugly --><td valign="top">

```python
const result = []
for item in array1:
    result.append(item)

for item in  array2:
    result.append(item)

for item in array3
    result.append(item);
```
</td><!-- beautiful --><td valign="top">

```python
result = [*array1, *array2, *array3]
```
---
```python
result = array1 + array2 + array3
```
</td></tr>
</tbody></table>


## Filter
<table><tbody>
<tr><!-- ugly --><td valign="top">

```python
bananas = []
for fruit in fruits:
    if fruit.name == "apple":
        bananas.append(fruit)
```
</td><!-- beautiful --><td valign="top">

```python
apples = [f for f in fruits if f.name == "apple"]
```
</td></tr>
</tbody></table>


## Map
<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
const values = ["1", "2", "3", "42"];
const result = [];
for (const v of values) {
    result.push(parseInt(v));
}
```
</td><!-- beautiful --><td valign="top">

```js
const values = ["1", "2", "3", "42"];
const result = values.map(v => parseInt(v));
```
</td></tr>
<tr><!-- ugly --><td valign="top">

```js
const result = [];
for (const apple of apples) {
    result.push("BANANA-" + apple.name);
}
```
</td><!-- beautiful --><td valign="top">

```js
const result = apples.map(apple => "Apple-" + apple.name);
```
</td></tr>
<tr><!-- ugly --><td valign="top">

```js
const result = [];
for (const apple of apples) {
    result.push({
        name: apple.name,
        density: apple.weight / apple.volume, 
    });
}
```
</td><!-- beautiful --><td valign="top">

```js
const result = apples.map(apple => ({
    name: apple.name,
    density: apple.weight / apple.volume, 
}));
```
</td></tr>
</tbody></table>
