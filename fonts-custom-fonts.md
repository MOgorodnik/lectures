# Нестандартные шрифты

## Google Web Fonts

Используем сервис Google для кроссбраузерного подключения нестандартных шрифтов на страницу.

[https://fonts.google.com/](https://fonts.google.com/)

Сначала находим те шрифты от Google, которые будем использовать в проекте.

Далее включаем нужные нам опции\(так называемая кастомизация шрифта\):

1. Начертание шрифта или шрифтов\(тонкие, жирные, курсив\)
2. Семейство шрифта по умолчанию только латинское, так что добавляем в набор нужный нам язык.

Теперь мы готовы подключать шрифт на страницу, для этого google предоставляет два способа:

```
<link href="https://fonts.googleapis.com/css?family=Mukta" rel="stylesheet">
```

```
<style>
    @import url('https://fonts.googleapis.com/css?family=Mukta');
</style>
```

Предпочтительнее первый вариант подключения.

Копируем код и вставляем его в секцию **head**  html файла.

Обычно используется как минимум 2 разных шрифта. Подключать их нужно одной ссылкой а не несколькими.

```
<link href="https://fonts.googleapis.com/css?family=Mukta:400,500|Roboto:100,400" rel="stylesheet">

или

<style>
    @import url('https://fonts.googleapis.com/css?family=Mukta:400,500|Roboto:100,400');
</style>
```

 В основном css файле нужно указать используемый шрифт от Google:

```
h1 {
    font-family: 'Roboto', sans-serif;
}
```

> ВАЖНО!  
> Если отсутствует нужное нам семейство языка, то нужно рассмотреть возможность замены используемого шрифта на похожий имеющий нужный язык, в противном случае, за неимением таковых либо настойчивому желанию заказчика использовать именно такой, рассмотреть возможность подключения используя  свойство @font-face



## @font-face Web fonts

 На данный момент, свойство @font-face поддерживается большинством браузеров\(~95%\)

Для работы в данном случае нам потребуется сконвертировать шрифт, поэтому заказчик должен предоставить файл шрифта для каждого из его начертаний желательно в формате **.ttf**.

### Конвертация шрифта 

Наиболее оптимальным, для конвертации шрифтов во все форматы сразу, является сервис [@font-face Kit Generator](http://www.fontsquirrel.com/fontface/generator) \(позволяет сгенерировать архив содержащий шрифты EOT, SVG и даже WOFF\). Также вы получите еще и готовый пример HTML+CSS для вставки шрифта на веб страницу, а также возможность некоторой оптимизации на этапе конвертации \(разложение шрифта, очистка обводов, автокоррекция глифов\).

 Данный сервис позволяет загрузить более одного шрифта и сразу \(одновременно\) сгенерировать необходимые форматы для всех загруженых шрифтов \(удобно если в проекте использется несколько различных шрифтов\).

### Внедрение шрифта

 По  [спецификации](http://www.w3.org/TR/css3-fonts/#the-font-face-rule), подключение шрифта с помощью font-face выглядит так:

```
@font-face {
    font-family: font;
    src: url(font.ttf);
}
```

**Важно: определять @font-face желательно в начале css файла.**

А использование так:

```
body { font-family: font, serif; }
```

 Далее представлен наиболее оптимальный кроссбраузерный код внедрения шрифта на страницу через свойство @font-face, предложенный [Полом Айришем \(Paul Irish\)](http://paulirish.com/2009/bulletproof-font-face-implementation-syntax/).

```
@font-face {
    font-family: 'GaramondPremierProSemiboldIta';
    src: url('garamondpremrpro-smbdit-webfont.eot#') format('eot'),
         url('garamondpremrpro-smbdit-webfont.woff') format('woff'),
         url('garamondpremrpro-smbdit-webfont.ttf') format('truetype'),
         url('garamondpremrpro-smbdit-webfont.svg#webfont0L0TsvhT') format('svg');
}
```

Первым делом мы объявляем семейство шрифтов **GaramondPremierProSemiboldIta**. Затем указываем источник со шрифтом в формате EOT для браузеров IE. Далее мы обращаемся к остальным браузерам с запросом на наличие локально установленного шрифта, если таковой отсутствует, браузеру предлагается его скачать.   
WOFF мы предлагаем для Firefox 3.6+, SVG для Opera 9.x и iPhone, а OTF для всех остальных браузеров.

Затем мы просто указываем семейство **GaramondPremierProSemiboldIta** для любого блока нашего документа или всей страницы в целом:

```
body { font-family: 'GaramondPremierProSemiboldIta', Georgia, serif; }
```

### Использование свойств font-style, font-weight и их комбинаций

 Единственно правильным и работоспособным, в поддерживаемых браузерах, способом использовать различные начертания для шрифта, является генерация отдельных форматов шрифтов и, соответственно, отдельной записи font-face.

```
@font-face {
    font-family: 'Your typeface';
    src: url('type/filename.eot#') format('eot'),
    url('type/filename.woff') format('woff'),
    url('type/filename.ttf') format('truetype'),
    url('type/filename.svg#filename') format('svg');
}
```

```
@font-face {
    font-family: 'Your italic typeface';
    src: url('type/filename-ital.eot') format('eot'),
    url('type/filename-ital.woff') format('woff'),
    url('type/filename-ital.ttf') format('truetype'),
    url('type/filename-ital.svg#filename-ital') format('svg');
}
```

 Второй пример показывает как необходимо объявлять наклонный тип шрифта. Естественно, что перед этим наклонный тип шрифта должен быть сгенерирован

 Использовать наклонный тип шрифта следует так:

```
h2 { font-family: "Your typeface", Georgia, serif; }
h2 em { font-family: "Your italic typeface", Georgia, serif; }
```

 Таким же образом можно использовать все остальные типы шрифтов \(Bold, Medium, Black и др.\). Всего же **@font-face** позволял указывать до 8-ми различных начертаний шрифта

### 

//

///

////

