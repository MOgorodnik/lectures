# Общая разметка/структура страниц.

| Рекомендуемое название класса | Описание/ предназначение элемента |
| :---: | :---: |
| **.wrapper/.page** | Основной блок страницы |
| **.nav** | Основнaя навигация страницы |
| **.header** | «шапка» документа |
| **.main** | основное содержание страницы |
| **.twocolumns** | колонка, которая содержит в себе **.content** и боковую колонку |
| **.content** | колонка контентной части |
| **.sidebar** | уникальная колонка слева или справа от **.content'а** |
| **.footer** | «подвал» страницы |
| **.aside \(.aside1, .aside2, ....\)** | Для выделения боковой колонки, которая несет в себе второстепенную дополнительную информацию |

Больше, об этом, читайте в статье [ Именование классов](/imenovanie-klassov.md "больше о названиях классов и элементах тут.").

> ## Элементы на которых можно использовать **id**:
>
> * элементы для JavaScript имплементации;
> * элементы форм, которые связаны с соответствующими label через for/id.
>   \*\*\*

---

## Страница с основной колонкой и боковой уникальной колонкой.

```
<div class="wrapper">

    <header class="header"></header>

    <main class="main">
        <section class="content"></section>
        <div class="sidebar"></div>
    </main>

    <footer class="footer"></footer>

</div>
```

## Страница с основной колонкой, боковой уникальной колонкой и одной дополнительной колонкой.

```
<div class="wrapper">

    <header class="header"></header>

    <main class="main">

        <div class="twocolumns">
            <section class="content"></section>
            <div class="aside"></div>
        </div>
        <div class="sidebar"></div>

    </main>

    <footer class="footer"></footer>

</div>
```

## Страница с основной колонкой и двумя дополнительными колонками.

```
<div class="wrapper">

    <header class="header"></header>

    <main class="main">

        <div class="twocolumns">
            <section class="content"></section>
            <div class="aside"></div>
        </div>
        <div class="aside aside-2"></div>

    </main>

    <footer class="footer"></footer>

</div>
```



