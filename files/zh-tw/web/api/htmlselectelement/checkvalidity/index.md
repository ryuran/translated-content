---
title: HTMLSelectElement.checkValidity()
slug: Web/API/HTMLSelectElement/checkValidity
---

{{ APIRef("HTML DOM") }}

**`HTMLSelectElement.checkValidity()`** 方法會檢查元素是否有任何的檢核、驗證條件，並且檢查是否滿足這些條件。如果元素沒有通過這些檢核，瀏覽器會於該元素上觸發一個可取消的 {{event("invalid")}} 事件，並回傳 `false`。

## 語法

```js
var result = selectElt.checkValidity();
```

## 規範

{{Specifications}}

## 瀏覽器相容性

{{Compat("api.HTMLSelectElement.checkValidity")}}

## 參見

- [Form validation.](/zh-TW/docs/Web/Guide/HTML/HTML5/Constraint_validation)
