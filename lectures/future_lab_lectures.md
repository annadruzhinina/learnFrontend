# learnFrontend
учебный материал (на примере разбора лендинга)

## ТОDO
- создать пункт 'Ознакомится перед курсом' (видосы по верстке, текст не стоит, т.к меньше шансов что пройдут)
- создать общий структурированный раздел с полезными материалам
- показывать примеры одного и того же кода на css и scss
- немного основной инфы про верстку писем. Поянить что для верстки писем если есть возможность лучше создать свой проект (у меня есть примеры)
- Рассказать что в эпам есть приложение для сбора стандартных писем для нашего hr 
	- Documentation - https://kb.epam.com/display/EPMHRMKB/How+to+create+a+newsletter
    - Lego - http://static.cdn.epam.com/uploads/25de0eda2b8cb5eb21bf2ae0f5b479f7/LEGO/DEFAULT/lego_v2.4.html
- Когда попадаешь на прект с нуля лучше создать свою UI страничку для компонентов(аля бутстрап, у меня есть примеры), чтоб потом было проще найти элементы которые уже сверстаны.
- Рассказать про бутстрап и ему подобные, приложить ссылки. 
    - Рассказать что бутстрап не всегда хорошо. Например если дизайнер на проекете не придерживается стилей бутстрапа, выходит что мы подключаем огромную библиоттеку а потом еще столько же стилей чтоб все переопределить т.к у нас дизайно то совсем другой! вопрос "на кой."
    - если пришлось юзать бутстрап, рассказать что всю библиотеку тащить не нужно. нужно подключать только те компоненты, которое юзаем. + о том что все переопределения стилей должны лежать в отдельной папке, например: override-bootstrap и если переопределяешь кнопку -> создайт в этой папке отдельный файл buttons


## Цель курса
На примере разбора макета:
- Узнать какие бывают способы получения макетов от дизайнеров.
- Научиться компонентному подходу в верстке (собирая страницу как лего из независимых друг от друга блоков и элементов).
- Научиться пользоваться системами контроля версий
- Научиться верстать не забывая про респонсив для мобилок и планшетов
- Используя Scss/Html/Npm/Gulp сверстать и собрать сайт, по пути разбирая какие существуют подходы в верстке.
(для лучшего усваения материала на уроках верстается только часть компонентов, остальное учащийся должен сделать самостоятельно)

## Get Started
### 1. Какие бывают способы получения макетов от дизайнеров (рассматриваются наиболее часто используемые системы в EPAM).
- photoshop
- zeplin
- invision
- figma
- почему не стоит бездумно копипастить стили из систем которые генерирую css автоматически (типа zeplin или figma)
    
### 2. Система контроля версий Git, и как этим пользоваться + github (в данном курсе рассматриваются только основные моменты, необходимые для старта работ)
- что такое система контроля версий, какие бывают
- что такое github, как создать репозиторий и выдать права + как разместить репозиторий на хостинге Github для удаленного просмотра сайта.
- [GIT + github] клонировать проект на рабочий стол
- [GIT + github] сделать первый push
- [GIT + github] что такое ветка, как создать и как с этим работать

В конце этой части мы будем иметь:
- свой акаунт на github
- репозиторий для нашего приложения (размещенный на хостинге github), который содержит папку styles и index.html

### 3. что такое NPM и сборщики (типа Gulp или Webpack)
(все что вы хотите сделать скорее всего уже написанно кем то другим и это можно переиспользовать или взять за основу и улучшить.)
- ищем NPM пакет который поможет компилировать препроцессор(например less/scss) в css
- ищем NPM пакет который позволит разделить наш код на отдельные компонеты интегрируемые в index.html
- ищем NPM пакет который минифицирует наш код.
- делаем сборку проекта (используется Gulp)
В конце этой части мы будем иметь структуру проекта:
```alias
...
project_name
    build/
        styles/
            styles.min.css
        index.html 
    src/
        styles/
            core/ (папка для хранения переменных проекта и глобальных стилей типа body)
                global.scss (покарасим body в красный)
                normolize.scss (файл для сброса браузерных дефолтных стилей, так же иногда называют reset)
            components/ (в этой папке лежат компоненты типа buttons, header, footer, inpyts и т.п.)
                header.scss (покарасим header в синий)
            styles.scss (файл содержит импорты всех стильников папки styles.)
            
        templates/
            header.html (тут лежит компонет шапки)
        index.html (делаем инпут нашей шапки(templates/header.html) в body)
        .editorconfig (для то го чтобы форматирование в ваших файлах не сбивалось, особенно актуально если над проектом работает команда)
        .gitignore (для исключения попадания не нужных файлов в ваш репозиторий)
        package.json
        gulpfile.js
        README.md
...
```
Создаем новую ветку в репозитории, называем её dev, пушим и далее работаем с ней.

### 4. Учимся компонентному подходу в верстке
- Немного про БЭM.
- Открываем макет и визуально разбиваем на отдельные блоки (шапка, кнопки, футер, ищем одинаковые элементы на странице(минимальные отличия типа цвета бордера не в счет)) Суть разбивки заключается в том что бы сверстать все эти блоки и элементы отдельно и независимо от чиго либо(например от других блоков) и после этого просто как конструктор лего собрать страничку.
- напишем список компонентов которые мы нашли для дальнейшей работы и заведем как задачи в гитхабе в разделе Projects.
    
## Начинаем верстать.

### 1. Респонив:
- почему о нем нужно думать до того как начал верстать (даже если этого нет в дизайне и менеджер проекта клянется Маском что приложение только для desktop).
- пропишем мета тег для респонива
- сделаем так чтобы на мобилке, планшете и desktop менялся фон шапки
Запушим наши правки.

### 2. Переменные и Миксины:
- зачем они нужны?
- пробуем использовать:
    - создадим структуру
```alias
...
project_name
    src/
        styles/
            core/
                mixins/
                    mixin-color-variant.scss (миксина которая позволяет не дублировать код раскрашивания кнопки)
                variables/
                    variables.scss (для любых переменных, кроме цвета)
                    variables-theme.scss (только переменные цветов)
                ...
                components/
                    ...
                    buttons/
                        button.scss (используем нашу миксину)
                styles.scss (имортируем стильник buttons/button.scss)
...
```
- variables-theme.scss - откроем макет, посмотрим какие есть цвета в проекте и запишем в файл
- variables.scss - запишем переменные основного размера шрифта(который используется для контента, например в теге <p>)
- global.scss - напишем стиль для body (размер шрифта, фон и т.п)
- button.scss - опишем кнопку используя миксину mixin-color-variant.scss (на данном этапе полностью не повторяем дизайн кнопки, цель научиться писать миксины)
- index.html - засунем в боди код кнопки

В конце этой части мы будем иметь:
- понимание переменных и миксин
- запушим наши изменения в репозиторий.

### 3. Берем первую задачу из нашего тасктрекера в github (например кнопки)
- наша структура уже готова(из предыдущего пункта), теперь можно верстать в соответствии с макетом.

# NOTE
- далее можно разобрать список карточек(с анимашкой цель показать transform и transition) на float, flex и grid
- отдельно рассказать про таблицы(очень важно, тут все косячат)
- описать раздел создания лейаута для сайта с учетом респонсива
- в каждом разделе дополнительно оставляем ссылки на полезные материалы или игрушки которые помогают лучше понять материал, например для флексов есть https://flexboxfroggy.com/#ru
- не нужно полность описывать ученику каждый компонент в дизайне, предлогаю: лейаут/список карточек(с какойниб анимашкой)/кнопки(т.к на них проще показать работу переменных и миксин) и все, остальное пусть делают сами и задают вопросы.