# SideEffect / 副作用
## Multi setter / 複合セッター
Multi setter helps to improve readableness and consistency.

関連する一連の情報をまとめて設定すると可読性の向上と、整合性の保証に繋がります。

<table><tbody>
<tr><!-- ugly --><td valign="top">

```js
user.setFirstName("John");
user.setMiddleName("");
user.setLastName("Doe");
```
</td><!-- beautiful --><td valign="top">

```js
user.setName("John", "", "Doe");
```
</td></tr>
<tr><!-- ugly --><td valign="top">

```js
user.unregisterAddress();
user.setCountry("Japan");
user.setRegion("Tokyo");
user.setCity("Minato");
user.setAddress1("foo");
user.setAddress2("#501, bar");
user.registerAddress();
```
</td><!-- beautiful --><td valign="top">

```js
user.moveAddress("Japan", "Tokyo", "Minato", "foo", "#501, bar");
```
</td></tr>
</tbody></table>
