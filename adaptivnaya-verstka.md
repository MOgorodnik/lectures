# Адаптивная верстка

---

## Терминология

**RWD** -  responsive web design

**Адаптивная верстка** - фиксированные размеры и компоновка

**Отзывчивая** - относительные размеры и компоновка

**Viewport** - тег указывающий браузеру, как корректировать содержание страницы

---

## Полезные ссылки

[http://www.liquidapsive.com/](http://www.liquidapsive.com/)

[https://css-tricks.com/the-difference-between-responsive-and-adaptive-design/](https://css-tricks.com/the-difference-between-responsive-and-adaptive-design/)

[http://frontender.com.ua/media-queries/](http://frontender.com.ua/media-queries/)

[https://css-tricks.com/snippets/css/media-queries-for-standard-devices/](https://css-tricks.com/snippets/css/media-queries-for-standard-devices/)

[http://html5.by/blog/viewport-meta-tag/](http://html5.by/blog/viewport-meta-tag/)

[Разрешения экранов популярных смартфонов](http://myresolutionis.ru/page/smapage.php)

---

## Общее

Каждый макет можно отнести к одному из следующих типов верстки: **фиксированная. резиновая, адаптивная и отзывчивая. **[Наглядный пример тут.](http://www.liquidapsive.com/)

Первую попытку создавать сайты еще и для мобильных устройств и задать тон и направление совершил Аарон Густавсон предложив технику **Адаптивной верстки**. Основной идеей было использование @media контрольных точек под определенные устройства. В таком подходе не учитывается как ведет себя страница в промежутках между контрольными точками.

Чуть позже свою идею предоставил Итан Маркот - **Отзывчивый дизайн** - В основе лежали следующие принципы: использование отзывчивого макета, гибких картинок, @media, % вместо пикселей. В итоге мы получаем плавное изменение страницы зависящее от содержимого, а не от устройства. Более подробно об этом подходе можно почитать в его книге "Сначала мобильные"

## [Viewport](https://www.quirksmode.org/mobile/viewports2.html)

Для лучшего понимания размеров viewport страницы следует взглянуть на то, что происходит при наименьшем возможном масштабе страницы. Большинство мобильных браузеров по-умолчанию отображают любую страницу в наименьшем масштабе.

Дело в том, что размеры viewport страницы браузеров полностью совпадают с экраном при максимально уменьшенном масштабе и поэтому равны визуальному viewport.

Таким образом, ширина и высота viewport страницы равна всему тому, что отображено на экране при наименьшем масштабе. При увеличении масштаба пользователем эти размеры остаются неизменными.

Ширина viewport страницы всегда неизменна. Если изменить ориентацию экрана смартфона, визуальный viewport изменится, но в то же время мобильный браузер приспособится к новой ориентации, немного увеличив масштаб таким образом, что viewport страницы снова станет таким же по ширине, как и визуальный viewport.

При сравнении мобильных и десктопных браузеров наиболее очевидное различие — размер экрана. Мобильные браузеры по-умолчанию отображают сайты, созданные для обычных десктопных браузеров, гораздо хуже, чем могли бы. К примеру, Вы открыли сайт, а он выглядит как-то необычно. Это происходит либо путем уменьшения масштаба, делая текст и другой контент слишком мелким либо отображая лишь небольшую часть сайта, которая умещается на экране.

Одним из самых распространенных вариантов определения области просмотра является следующий вариант который определяет ширину страницы и задает начальный масштаб:

`<meta name="viewport" content="width=device-width, initial-scale=1.0">`

или

```
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
```

Для чего [shrink-to-fit](https://bitsofco.de/ios-safari-and-shrink-to-fit/)?

![](/assets/Viewport.png)

**layout viewport** - это область на которой размещены все элементы страницы

**visual viewport** - это часть layout viewport-а, которая отображается в данный момент на экране.

**viewport** - задает размер layout viewport-а, для того чтобы при открытии на мобильном устройстве, ширина viewport-a была задана наиболее удобным значением, обычно это device-width. В этом случае страница будет вписана в размер экрана.

//

////

## А как в Bootstrap?

```
// Extra small devices (portrait phones, less than 576px)
// No media query since this is the default in Bootstrap

// Small devices (landscape phones, 576px and up)
@media (min-width: 576px) { ... }

// Medium devices (tablets, 768px and up)
@media (min-width: 768px) { ... }

// Large devices (desktops, 992px and up)
@media (min-width: 992px) { ... }

// Extra large devices (large desktops, 1200px and up)
@media (min-width: 1200px) { ... }
```

или еще можно так

```
// Extra small devices (portrait phones, less than 576px)
@media (max-width: 575px) { ... }

// Small devices (landscape phones, less than 768px)
@media (max-width: 767px) { ... }

// Medium devices (tablets, less than 992px)
@media (max-width: 991px) { ... }

// Large devices (desktops, less than 1200px)
@media (max-width: 1199px) { ... }

// Extra large devices (large desktops)
// No media query since the extra-large breakpoint has no upper bound on its width
```

еще так

```
// Extra small devices (portrait phones, less than 576px)
@media (max-width: 575px) { ... }

// Small devices (landscape phones, 576px and up)
@media (min-width: 576px) and (max-width: 767px) { ... }

// Medium devices (tablets, 768px and up)
@media (min-width: 768px) and (max-width: 991px) { ... }

// Large devices (desktops, 992px and up)
@media (min-width: 992px) and (max-width: 1199px) { ... }

// Extra large devices (large desktops, 1200px and up)
@media (min-width: 1200px) { ... }
```



