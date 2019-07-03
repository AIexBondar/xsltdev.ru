# &lt;a&gt;

Тег **`<a>`** _(от англ. **a**nchor - якорь, ссылка)_ предназначен для создания ссылок.

Для этого необходимо сообщить браузеру, что является ссылкой, а также указать адрес документа, на который следует сделать ссылку.

В качестве значения атрибута `href` используется адрес документа, на который происходит переход. Адрес ссылки может быть абсолютным и относительным. Абсолютные адреса работают везде и всюду независимо от имени сайта или веб-страницы, где прописана ссылка. Относительные ссылки, как следует из их названия, построены относительно текущего документа или корня сайта.

## Синтаксис

<!-- prettier-ignore -->
```html
<a
	download="имя файла"
	href="адрес"
	hreflang="код языка"
	rel="отношение"
	target="целевое окно"
	type="MIME-тип">
  ...
</a>
```

Закрывающий тег обязателен.

## Атрибуты

- `download` -- Предлагает скачать указанный по ссылке файл.
- `href` -- Задаёт адрес документа, на который следует перейти.
- `hreflang` -- Идентифицирует язык текста по ссылке.
- `ping` -- Этот атрибут уведомляет указанные в нём URL, что пользователь перешёл по ссылке.
- `rel` -- Отношения между ссылаемым и текущим документами.
- `target` -- Имя окна или фрейма, куда браузер будет загружать документ.
- `type` -- Указывает MIME-тип документа, на который ведёт ссылка.

Также для этого элемента доступны [универсальные атрибуты](/lib/uni-attr/) и [события](/lib/events/).

### download

При наличии атрибута **`download`** _(от англ. **download** - скачать)_ браузер не переходит по ссылке, а предложит скачать документ, указанный в адресе ссылки.

**Синтаксис**

```html
<a download>Ссылка</a> <a download="<текст>">Ссылка</a>
```

**Значения**

Если атрибут `download` пишется без значения, то файл скачивается и сохраняется под своим исходным именем, как оно написано на сервере. В качестве значения можно указать рекомендуемое имя файла для сохранения на диск пользователя. При этом файл будет скачан и сохранён с именем, указанным в значении `download`. Расширение файла при этом останется исходным.

**Значение по умолчанию**

По умолчанию этот атрибут выключен.

### href

Атрибут **`href`** _(от англ. **h**ypertext **ref**erence - гипертекстовая ссылка)_ задаёт адрес документа, на который следует перейти. Поскольку в качестве адреса ссылки может использоваться документ любого типа, то результат перехода по ссылке зависит от конечного файла. Так, архивы (файлы с расширением `zip` или `rar`) будут сохраняться на локальный диск. По умолчанию новый документ загружается в текущее окно браузера, однако это свойство можно изменить с помощью атрибута `target`.

**Синтаксис**

```html
<a href="<адрес>">...</a>
```

**Значение по умолчанию**

Нет.

### hreflang

Атрибут **`hreflang`** _(от англ. **h**ypertext **ref**erence **lang**uage - язык гипертекстовой ссылки)_ указывает язык документа, на который ведёт ссылка.

**Синтаксис**

```html
<a hreflang="<язык>">...</a>
```

**Значения**

Код языка

**Значение по умолчанию**

Нет.

**Примечание**

Атрибут можно использовать для стилизации ссылок, ведущих на иностранные ресурсы.

### rel

Атрибут **`rel`** _(от англ. **rel**ation - связь, отношение)_ определяет отношения между текущим документом и документом, на который ведёт ссылка, заданная атрибутом `href`. Несмотря на то, что большинство браузеров не поддерживают атрибут `rel`, на сайтах часто можно встретить код `rel="nofollow"`, предназначенный для поисковых систем Google и Яндекс. Ссылки, помеченные таким образом, не передают PageRank и ТИЦ.

**Синтаксис**

```html
<a rel="текст">...</a>
```

**Значения**

- `alternate` -- Даёт альтернативные представления текущего документа.
- `author` -- Указывает ссылку на автора текущего документа или статьи.
- `bookmark` -- Постоянная ссылка на ближайший родительский раздел.
- `help` -- Ссылка на контекстно-зависимую справку.
- `icon` -- Импортирует иконку для представления текущего документа.
- `license` -- Указывает, что основное содержание текущего документа распространяется по лицензии, описанной в указанном документе.
- `next` -- Указывает, что текущий документ является частью серии и ссылка ведёт на следующий документ в серии.
- `nofollow` -- Не передавать по ссылке ТИЦ и PR.
- `noreferrer` -- Требует, чтобы пользовательский агент не посылал в HTTP-заголовке Referer, если пользователь переходит по ссылке.
- `prefetch` -- Указывает, что целевой ресурс должен быть заранее кэширован.
- `prev` -- Указывает, что текущий документ является частью серии и ссылка ведёт на предыдущий документ в серии.
- `search` -- Даёт ссылку на ресурс, который может быть использован для поиска по текущему документу и связанных с ней страниц.
- `stylesheet` -- Импортирует таблицу стилей.
- `tag` -- Указывает, что метка (тег) имеет отношение к текущему документу.

**Значение по умолчанию**

Нет.

### target

По умолчанию, при переходе по ссылке документ открывается в текущей вкладке браузера. Это поведение можно изменить с помощью атрибута **`target`** _(от англ. **target** - цель)_ элемента `<a>`. В качестве значения используется имя фрейма, заданное атрибутом `name` элемента [`<iframe>`](iframe.md), или зарезервированное ключевое слово. При указании имени фрейма ссылка будет открываться во фрейме.

**Синтаксис**

```html
<a target="...">...</a>
```

**Значения**

В качестве значения используется имя фрейма, заданное атрибутом `name`. Если установлено несуществующее имя, то будет открыта новая вкладка браузера. В качестве зарезервированных имен используются следующие.

- `_blank` -- Загружает страницу в новую вкладку браузера.
- `_self` -- Загружает страницу в текущую вкладку.
- `_parent` -- Загружает страницу во фрейм-родитель; если фреймов нет, то это значение работает как `_self`.
- `_top` -- Отменяет все фреймы и загружает страницу в полном окне браузера; если фреймов нет, то это значение работает как `_self`.

**Значение по умолчанию**

`_self`

### type

Атрибут **`type`** _(от англ. **type** - тип)_ устанавливает MIME-тип документа, на который указывает ссылка. Этот атрибут носит рекомендательный характер и может использоваться для стилизации ссылок с заданным типом документа. Атрибут `type` должен добавляться только при наличии атрибута `href`.

**Синтаксис**

```html
<a href="<адрес>" type="<MIME-тип>">...</a>
```

**Значения**

MIME-тип

**Значение по умолчанию**

Нет.

## Спецификации

- [WHATWG HTML Living Standard](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-a-element)
- [HTML5](http://www.w3.org/TR/html5/text-level-semantics.html#the-a-element)
- [HTML 4.01 Specification](http://www.w3.org/TR/html401/struct/links.html#h-12.2)

## Описание и примеры

Пример со ссылкой:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>А</title>
  </head>
  <body>
    <p><a href="image/xxx.jpg">Посмотрите на мою фотографию!</a></p>
    <p><a href="page/tip.html">Как сделать такое же фото?</a></p>
  </body>
</html>
```

Результат:

<iframe srcdoc='<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>А</title>
  </head>
  <body>
    <p><a href="image/xxx.jpg">Посмотрите на мою фотографию!</a></p>
    <p><a href="page/tip.html">Как сделать такое же фото?</a></p>
  </body>
</html>'></iframe>

Пример с якорем:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>anchor</title>
    <style>
      #anchor {
        margin-top: 999px;
      }
    </style>
  </head>
  <body>
    <a href="#anchor">Go to anchor</a>
    <div id="anchor">Anchor</div>
  </body>
</html>
```

Результат:

<iframe srcdoc='<!DOCTYPE html>
<html>
  <head>
    <title>anchor</title>
    <style>
      #anchor {
        margin-top: 999px;
      }
    </style>
  </head>
  <body>
    <a href="#anchor">Go to anchor</a>
    <div id="anchor">Anchor</div>
  </body>
</html>'></iframe>

### Создания ссылки для написания письма

```html
<a href="mailto:nowhere@mozilla.org">Отправить сообщение в никуда</a>
```

Для дополнительных деталей использования mailto, таких как тема, текст или другое, смотрите [RFC 6068](http://tools.ietf.org/html/6068). ### Создание ссылки с номером телефона С телефонами, способными выходить в Интернет и ноутбуками, которые привязаны к телефонам, ссылки с номером телефона становятся всё больше и больше полезными.

```html
<a href="tel:+491570156">+49 157 0156</a>
```

Для дополнителных деталей о протоколе tel, смотрите [RFC 2806](http://tools.ietf.org/html/2806) и [RFC 2396](http://tools.ietf.org/html/2396).