# bigint型

JavaScriptのbigint型は、数値型よりも大きな整数を扱えるプリミティブ型です。

## bigint型リテラル

JavaScriptのbigint型のリテラルは整数値の末尾に`n`をつけて書きます。

```ts twoslash
const x = 100n;
```

bigintリテラルをTypeScriptで用いるには、コンパイラーオプションのtargetをes2020以上にする必要があります。

## bigint型の型注釈

TypeScriptでbigint型を型注釈するには、`bigint`を用います。

```ts twoslash
const x: bigint = 100n;
```

## BigInt関数

bigint型はBigInt関数を使って作ることができます。BigInt関数は第1引数に数値もしくは文字列を渡します。

```ts twoslash
const x = BigInt(100);
const y = BigInt("9007199254740991");
```

TypeScriptでBigInt関数を用いるには、コンパイラーオプションのlibをes2020以上にする必要があります。

## bigint型を数値型と計算する

bigint型と数値型はそのままでは一緒に演算をすることはできません。どちらかに型を合わせる必要があります。

```ts twoslash
// @errors: 2365
2n + 3;
```

数値型が小数部を持っていない限り、より表現幅の広いbigint型に合わせる方が無難です。

```ts twoslash
const i = 2n + BigInt(3); //=> 5n

console.log(i);
// @log: 5
```
