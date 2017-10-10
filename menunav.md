# Drop-Down Menu

---

## One Level Drop Down

**HTML:**

```
<nav >
    <ul class="nav">

        <li class="nav__item">
            <a href="#" class="nav__link">link text</a>
        </li>

        <li class="nav__item">
            <a href="#" class="nav__link">link text</a>
        </li>

        <li class="nav__item">
            <a href="#" class="nav__link">link with drop</a>

            <!-- drop-down list -->
            <ul class="nav__drop drop">
                <li class="drop__item">
                    <a href="#" class="drop__link">sub link 1</a>
                </li>
                <li class="drop__item">
                    <a href="#" class="drop__link">Long long long long sub link 2</a>
                </li>
                <li class="drop__item">
                    <a href="#" class="drop__link">sub link 3</a>
                </li>
            </ul>    
        </li>

        <li class="nav__item">
            <a href="#" class="nav__link">link text</a>
        </li>
    </ul>
</nav>
```

**CSS:**

```
/* general styles*/
a{
    color: #fff;
    text-decoration: none;
}
a:hover{text-decoration: underline;}

/* elements/blocks styles */
/* nav styles */
.nav{
    width: 80%;
    margin: 50px auto 200px;
    list-style: none;
    font-weight: bold;
    text-transform: uppercase;
    background: #ffa500;
    padding: 15px;
    border-radius: 20px;
    box-shadow: inset 0 0 5px 0 #f00, 0 0 0 12px #ccc;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly; /* flex-start | flex-end | center | space-between | space-around | space-evenly  */
}
.nav__item{
    margin: 0 10px;
}
.nav__link{
    display: block;
    padding: 10px;
    border: 1px solid #fff;
    text-decoration: none;
}
.nav__link:hover{
    text-decoration: none;
    border-color: #000;
    color: #000;
}

/* drop styles */
.drop{
    position: absolute;
    top: 100%;
    left: -3000px;
    list-style: none;
    padding: 10px;
    margin: 0;
    background: #ccc;
    text-transform: none;
    line-height: 2;
    width: calc(100% - 2*10px);
    box-shadow: 0 0 10px #000;
    opacity: 0;
}
/* action styles */
.nav__item:hover{
    position: relative;
}
.nav__item:hover .nav__link{
    position: relative;
/*     z-index: 1; */
    background: #eee;
}
.nav__item:hover .drop{
    left: 0;
    opacity: 1;
    transition: left 0.7s linear 0.1s, opacity 1.5s linear;
}
```

Дополнительное задание:

1. Как ведет себя выпадающий список по ширине и почему
2. Зачем на `.nav__link` прописан `display: block;`
3. Зачем на `.navitem:hover .nav__link` прописан `position: relative; z-index: 1;`
4. Вторая ссылка в дропе длинная и выглядит как две ссылки, как можно улучшить визуальное отображение ссылок.
5. Как сделать чтоб ширина выпадающего списка была по ширине самого длинного внутреннего его элемента, а не по ширине элемента спискав котором находится этот дроп-даун
6. Сделать на основе этой одноуровневой дроп-даун навигации - многоуровневую
7. В дроп-дауне второго уровня слова текста ссылок должны начинаться с заглавных букв, при наведении цветт текста ссылки и фон должны изменяться.



