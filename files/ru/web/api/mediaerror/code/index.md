---
title: MediaError.code
slug: Web/API/MediaError/code
---

{{APIRef("HTML DOM")}}

Свойство **`MediaError.code`** доступно только для чтения, возвращает числовое значение, представляющее тип ошибки, возникшей на элементе носителя. Чтобы получить текстовую строку с конкретной диагностической информацией, см. раздел {{domxref("MediaError.message")}}.

## Синтаксис

```
var myError = mediaError.code;
```

### Значение

Числовое значение, указывающее общий тип возникшей ошибки. Возможные значения описаны ниже, в разделе [Media error code constants](#media_error_code_constants).

#### Константы кода ошибки носителя

| Name                          | Value | Description                                                                                                                   |
| ----------------------------- | ----- | ----------------------------------------------------------------------------------------------------------------------------- |
| `MEDIA_ERR_ABORTED`           | `1`   | Извлечение связанного ресурса было прервано запросом пользователя.                                                            |
| `MEDIA_ERR_NETWORK`           | `2`   | Произошла какая-то сетевая ошибка, которая помешала успешному извлечению носителя, несмотря на то, что он был ранее доступен. |
| `MEDIA_ERR_DECODE`            | `3`   | Несмотря на то, что ранее ресурс был определён, как используемый, при попытке декодировать медиаресурс произошла ошибка.      |
| `MEDIA_ERR_SRC_NOT_SUPPORTED` | `4`   | Связанный объект ресурса или поставщика мультимедиа (например, {{domxref ("MediaStream")}}) был признан неподходящим.         |

## Пример

В этом примере создаётся элемент {{HTMLElement("video")}}, устанавливается обработчик ошибок для него, а затем устанавливается атрибут элемента [`src`](/ru/docs/Web/HTML/Reference/Elements/video#src) для видеоресурса, который должен присутствовать в элементе. Обработчик ошибок просто выводит сообщение

```js
var obj = document.createElement("video");
obj.onerror = function () {
  console.log("Ошибка с носителями информации: " + obj.error.code);
};
obj.src = "https://example.com/blahblah.mp4";
```

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

## Изучите также

- Интерфейс, определяющий его, {{domxref("MediaError")}}.
