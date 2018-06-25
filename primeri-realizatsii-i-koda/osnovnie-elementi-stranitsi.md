## Основные элементы веб-страницы и их реализации.

> * [Логотип](#реализация-логотипа).
> * [Цитаты](#цитаты).
> * Посты, их оформление.
> * Заголовки, их оформление.
> * Выделение другим цветом.
> * Дополнительная информация на странице, баннеры.
> * Исправленные данные.
> * Навигации
>   * Основная
>   * Вспомогательная
> * Комментарии

### Реализация логотипа

_Реализация логотипа, если он в формате - GIF, PNG8, JPG/JPEG, используем следующие варианты:_

**Вариант 1.**

**HTML:**

```
<span class="logo">some logo text</span>

<strong class="logo">
    <a href="#">some logo text</a>
</strong>

<strong class="logo">some logo text</strong>

<h1 class="logo">some logo text</h1>
```

**CSS:**

```
.logo {
    width:110px;
    height:110px;
    background:url(../images/logo.gif);
    text-indent:-9999px;
    overflow:hidden;
    margin:0;
}
.logo a{
     display:block;
     height:100%;
}
```

**Вариант 2.**

**HTML:**

```
<h1>
    <a href="#" class="logo">some logo text</a>
</h1>

<h1 class="logo">some logo text</h1>

<strong class="logo">some logo text</strong>
```

**CSS:**

```
.logo {
     width:110px;
     height:110px;
     background:url(../images/logo.gif);
     text-indent:-9999px;
     overflow:hidden;
     margin:0;
 }
```

**Если логотип будет в PNG24, используем следующие варианты реализаций логотипов.**

**Вариант 1.**

**HTML:**

```
<h1 class="logo">
    <a href="#">some logo text</a>
</h1>

<h1 class="logo">some logo text</h1>

<strong class="logo">some logo text</strong>
```

**CSS:**

```
.logo {
    width:110px;
    height:110px;
    background:url(../images/logo.png);
    text-indent:-9999px;
    overflow:hidden;
    margin:0;
}
.logo a{
    display:block;
    height:100%;
    position:relative;
}
```

**Вариант 2.**

**HTML:**

```
<h1>
    <a href="#" class="logo">some logo text</a>
</h1>

<h1 class="logo">some logo text</h1>

<strong class="logo">some logo text</strong>
```

**CSS:**

```
.logo{
    width:110px;
    height:110px;
    background:url(../images/logo.png);
    text-indent:-9999px;
    overflow:hidden;
    margin:0;
}
a.logo{
    cursor:pointer;
}
```

> > В случае отсутствия `h1` в логотипе — `margin:0;` писать не нужно.
> >
> > В случае, если вместо `h1`, используется `strong` — необходимо добавить `display:block;`.
> >
> > ВАЖНО
> >
> > 1. В случае, если вы используете кликабельный PNG24 логотип со свойством `position:absolute` - используйте "Второй вариант" реализации, при этом `position:absolute;` необходимо задавать не на `<a>`, а на родительский элемент \(`strong или h1`\).
> >
> > 2. ВСЕГДА в html записывайте ВЕСЬ текст логотипа, изображенный на дизайне лого.

[Вверх](#основные-элементы-веб-страницы-и-их-реализации)

## Цитаты

> &lt;blockquote&gt;  -  предназначен для выделения длинных цитат, которые могут состоять из нескольких абзацев. Тег выделяет цитату как отдельный блок текста с отступами.
>
> &lt;q&gt;  -  предназначен для выделения коротких цитат в предложениях. Текст внутри этого тега автоматически обрамляется кавычками.
>
> &lt;cite&gt;  -   используется для того, чтобы выделить источник цитаты, название произведения или автора цитаты.

**HTML-элемент &lt;blockquote&gt;        
**указывает на то, что заключенный в нем текст является развернутой цитатой.

```
<blockquote cite="http://developer.mozilla.org">
    <p>This is a quotation taken from the Mozilla Developer Center.</p>
</blockquote>
```

**HTML-элемент &lt;cite&gt;**  
Представляет из себя ссылку на источник цитаты. Он должен включать в себя название произведения или URL.

```
<p>More information can be found in <cite>[ISO-0000]</cite>.</p>
```

**HTML-элемент &lt;q&gt;    
**

```
<p>In <cite>2001: A Space Odyssey</cite>, Dave asks HAL to open the pod bay door and HAL answers: <q cite="https://www.imdb.com/title/tt0062622/quotes/qt0396921">I'm sorry, Dave. I'm afraid I can't do that.</q></p>
```

Тут _атрибут_ **cite **- имеет URL, указывающий на исходный документ или сообщение, откуда была взята цитата. Этот атрибут предназначен для того, чтобы сослаться на информацию, объясняющую контекст, или ссылки, из которых была взята цитата. Глобальный атрибут - cite - может быть использован у blockquote & q.

