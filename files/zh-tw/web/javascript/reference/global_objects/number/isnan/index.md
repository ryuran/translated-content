---
title: Number.isNaN()
slug: Web/JavaScript/Reference/Global_Objects/Number/isNaN
---

{{JSRef}}

The **`Number.isNaN()`** method determines whether the passed value is {{jsxref("NaN")}} and its type is {{jsxref("Number")}}. It is a more robust version of the original, global {{jsxref("isNaN", "isNaN()")}}.

{{EmbedInteractiveExample("pages/js/number-isnan.html", "taller")}}

## Syntax

```plain
Number.isNaN(value)
```

### Parameters

- `value`
  - : The value to be tested for {{jsxref("NaN")}}.

### Return value

**true** if the given value is {{jsxref("NaN")}} and its type is {{jsxref("Number")}}; otherwise, **false**.

## Description

Due to both equality operators, {{jsxref("Operators/Comparison_Operators", "==", "#Equality")}} and {{jsxref("Operators/Comparison_Operators", "===", "#Identity")}}, evaluating to `false` when checking if {{jsxref("NaN")}} _is_ {{jsxref("NaN")}}, the function `Number.isNaN()` has become necessary. This situation is unlike all other possible value comparisons in JavaScript.

In comparison to the global {{jsxref("isNaN", "isNaN()")}} function, `Number.isNaN()` doesn't suffer the problem of forcefully converting the parameter to a number. This means it is now safe to pass values that would normally convert to {{jsxref("NaN")}}, but aren't actually the same value as {{jsxref("NaN")}}. This also means that only values of the type number, that are also {{jsxref("NaN")}}, return `true`.

## Examples

```js
Number.isNaN(NaN);        // true
Number.isNaN(Number.NaN); // true
Number.isNaN(0 / 0);      // true

// e.g. these would have been true with global isNaN()
Number.isNaN('NaN');      // false
Number.isNaN(undefined);  // false
Number.isNaN({});         // false
Number.isNaN('blabla');   // false

// These all return false
Number.isNaN(true);
Number.isNaN(null);
Number.isNaN(37);
Number.isNaN('37');
Number.isNaN('37.37');
Number.isNaN('');
Number.isNaN(' ');
```

## Polyfill

The following works because NaN is the only value in javascript which is not equal to itself.

```js
Number.isNaN = Number.isNaN || function(value) {
    return value !== value;
}
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat("javascript.builtins.Number.isNaN")}}

## See also

- {{jsxref("Number")}}
- {{jsxref("isNaN", "isNaN()")}}
