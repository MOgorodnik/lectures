## Основные элементы веб-страницы и их реализации.

> * [Логотип](#реализация-логотипа).
> * Цитаты.
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

_Реализация логотипа, если он в формате - GIF, PNG8/24, JPG/JPEG, используем следующие варианты:_

**Вариант 1.**

**HTML:**

```
<span class="logo">some logo text</span>
<strong class="logo"><a href="#">some logo text</a></strong>
<strong class="logo">some logo text</strong>
<h1 class="logo">some logo text</h1>
```

**CSS:**

```
.logo {
	width:100px;
	height:100px;
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
<h1><a href="#" class="logo">some logo text</a></h1>
<h1 class="logo">some logo text</h1>
<strong class="logo">some logo text</strong>
```

**CSS:**

```
.logo {
	 width:100px;
	 height:100px;
 	background:url(../images/logo.gif);
 	text-indent:-9999px;
 	overflow:hidden;
	margin:0;
 }
```



