---
title: "`window.matchMedia`"
description: "Доступ к медиавыражениям из JavaScript"
authors:
  - akellbl4
keywords:
  - media
  - медиавыражение
  - match media
  - media query
tags:
  - doka
---

## Кратко

Интерфейс в глобальной области видимости `window.matchMedia`, который позволяет получить доступ к медиавыражениям из JavaScript и подписываться на их срабатывание. Также вы можете найти информацию про написание медиавыражений в CSS в статье [@media](/css/media).

## Пример

### Определение ширины экрана по заданному медиавыражению

Создадим медиавыражение с параметрами ширины и подпишемся его изменение. Теперь при изменении ширины экрана, в момент прохода через пороговое значение 420px, будет выведено сообщение:

```js
const mobileWidthMediaQuery = window.matchMedia('(max-width: 420px)')

function printLog(isMobileSize) {
  const size = event.matches ? 'уже или равен' : 'шире'

  console.log(`Размер экрана ${size} 420px`)
}

printLog(mobileWidthMediaQuery.matches)

mobileWidthMediaQuery.addEventListener('change', function (event) {
  printLog(event.matches)
})
```

### Определение системной темы оформления

Создадим медиавыражение и предадим условие, которое будет положительным в случае, когда установлена тёмная тема оформления. Выведем сообщение о текущем состоянии системы, а также подпишемся на её изменение.

При смене темы оформления, в системе будет выводиться сообщение и сообщать текущее состояние.

```js
const themeMediaQuery = window.matchMedia('(prefers-color-scheme: dark)')

function printLog(isDark) {
  const theme = isDark ? 'темная' : 'светлая'

  console.log(`В системе используется ${theme} тема`)
}

printLog(themeMediaQuery.matches)

themeMediaQuery.addEventListener('change', function (event) {
  printLog(event.matches)
})
```

## Как пишется

Для создания медиа объекта нужно вызвать функцию `matchMedia` и передать ей медиавыражение. Синтаксис медиавыражений и их варианты полностью совпадают с [выражениями, которые используются в CSS](/css/media).

```js
const mediaQueryList  = window.matchMedia('(медиавыражение)')
```

## Как понять

Если вам нужно реагировать на изменения в браузере одновременно с изменениями в вёрстке, вы можете создавать медиавыражения в JavaScript и реагировать на эти события синхронно с CSS.

