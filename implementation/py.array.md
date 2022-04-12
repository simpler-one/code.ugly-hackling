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
result = []
for item in array1:
    result.append(item)

for item in array2:
    result.append(item)

for item in array3
    result.append(item)
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

```python
values = ["1", "2", "3", "42"]
result = []
for v in values
    result.append(int(v))
```
</td><!-- beautiful --><td valign="top">

```python
values = ["1", "2", "3", "42"]
result = [int(v) for v in values]
```
</td></tr>
<tr><!-- ugly --><td valign="top">

```python
result = []
for apple in apples:
    result.push("BANANA-" + apple.name)
```
</td><!-- beautiful --><td valign="top">

```python
result = ["Apple-" + apple.name for apple in apples]
```
</td></tr>
<tr><!-- ugly --><td valign="top">

```python
result = []
for apple in apples:
    result.append({
        "name": apple.name,
        "density": apple.weight / apple.volume, 
    })
```
</td><!-- beautiful --><td valign="top">

```python
result = [{
    "name": apple.name,
    "density": apple.weight / apple.volume, 
} for apple in apples]
```
</td></tr>
</tbody></table>
