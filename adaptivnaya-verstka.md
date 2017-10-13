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

---

## Общее

Каждый макет можно отнести к одному из следующих типов верстки: **фиксированная. резиновая, адаптивная и отзывчивая. **[Нагдядный пример тут.](http://www.liquidapsive.com/)

Первую попытку создавать сайты еще и для мобильных устройств и задать тон и направление совершил Аарон Густавсон предложив технику **Адаптивной верстки**. Основной идеей было использование @media контрольных точек под определенные устройства. В таком подходе не учитывается как ведет себя страница в промежутках между контрольными точками.

Чуть позже свою идею предоставил Итан Маркот - **Отзывчивый дизайн** - В основе лежали следующие принципы: использование отзывчивого макета, гибких картинок, @media, % вместо пикселей. В итоге мы получаем плавное изменение страницы зависящее от содержимого, а не от устройства. Более подробно об этом подходе можно почитать в его книге "Сначала мобильные"





`<meta name="viewport" content="width=device-width, initial-scale=1.0">`

