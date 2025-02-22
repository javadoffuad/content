---
title: "`window.navigator`"
description: "Возвращает описание браузера или приложения, которое выполняет скрипт."
authors:
  - doka-dog
tags:
  - doka
  - placeholder
---

## Кратко

Свойство `window.navigator` возвращает объект описания приложения (user agent), которое выполняет скрипт. В подавляющем большинстве случаев это приложение — браузер. Объект содержит свойства, описывающие браузер, и методы для выполнения действий.

Часто используемые свойства:

`userAgent` возвращает строку, которая содержит название браузера. Не стоит использовать это свойство, чтобы определить браузер пользователя! Спецификация рекомендует браузерам передавать минимум информации в `userAgent`, значение может меняться от версии к версии.

```js
navigator.userAgent
// "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:93.0) Gecko/20100101 Firefox/93.0"
```

`language` возвращает предпочитаемый язык интерфейса в виде [языкового тега](https://tools.ietf.org/rfc/bcp/bcp47.txt). Например, `en`, `ru`, `en-US` и т.д. Обычно это язык, установленный в настройках браузера.

`languages` возвращает массив предпочитаемых языков в порядке предпочтительности. Первый в списке будет язык, который возвращает `navigator.language`.

```js
navigator.language
// "ru"
navigator.languages
// ["ru", "en-US", "es-ES"]
```

`cookieEnabled` возвращает `true`, если браузер пользователя поддерживает [куки](/js/cookie) и они включены, `false` в противном случае.

`onLine` возвращает `true`, если у пользователя есть подключение к сети. Браузеры вкладывают разные смыслы в понятие «онлайн», поэтому это свойство ненадёжный источник данных.

Объект `navigator` содержит множество других свойств, большинство из них экспериментальные или поддерживаются конкретными браузерами.

Методы объекта `navigator` служат для взаимодействия с другими WebAPI. Например, метод `vibrate`, который вызывает вибрацию пользовательского устройства, если она поддерживается: `navigator.vibrate(200)`
