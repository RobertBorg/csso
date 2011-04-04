# 1. Описание

CSSO (CSS Optimizer) является минимизатором CSS, выполняющим как минимизацию без изменения структуры, так и структурную минимизацию с целью получить как можно меньший текст стиля.

Этот документ является инструкцией по установке и использованию. Если вам нужна детальная инструкция по минимизации, она находится [здесь](https://github.com/afelix/csso/blob/master/MANUAL.ru.md).

# 2. Установка

## 2.1. Предварительные требования

* для использования из браузера: любая OS с современным браузером
* для использования из командной строки: OS Linux / Mac OS X

## 2.2. Установка с помощью git

Предварительные требования:

* git&nbsp;— [http://git-scm.com/](http://git-scm.com/)

Установка:

* выполнить `git clone git@github.com:afelix/csso.git`

## 2.3. Установка с помощью npm

Предварительные требования:

* nodejs версии 0.4.x&nbsp;— [http://nodejs.org](http://nodejs.org)
* npm&nbsp;— [http://github.com/isaacs/npm/](http://github.com/isaacs/npm/)

Установка:

* выполнить `npm install csso`

# 3. Использование

## 3.1. Через браузер (при установке с помощью git)

Открыть в браузере файл `web/csso.html`.

## 3.2. Через командную строку

При git-установке запускать `bin/csso`, но в таком случае потребуется nodejs версии 0.4.x&nbsp;— [http://nodejs.org](http://nodejs.org)

При npm-установке запускать `csso`.

Справка командной строки:
    csso
        показывает этот текст
    csso <имя_файла>
        минимизирует CSS из <имя_файла> и записывает результат в stdout
    csso --help
        показывает этот текст
    csso --version
        показывает номер версии CSSO

Пример использования:
    $ echo ".test { color: red; color: green }" > test.css
    $ csso test.css
    .test{color:green}

# 4. Минимизация (кратко)

Минимизация без изменения структуры:

* Удаление whitespace
* Удаление концевых `;`
* Удаление комментариев
* Удаление неправильных `@charset` и `@import`
* Удаление ошибочных элементов стиля
* Минимизация цвета
* Минимизация `0`
* Минимизация `margin` и `padding`
* Слияние многострочных строк в однострочные
* Минимизация `font-weight`

Минимизация с изменением структуры:

* Слияние блоков с одинаковыми селекторами
* Удаление перекрываемых свойств
* Частичное выделение свойств в отдельный блок
* Частичное слияние блоков

# 5. Авторы

* идея и поддержка&nbsp;— Виталий Харисов (vitaly@harisov.name)
* реализация&nbsp;— Сергей Крыжановский (skryzhanovsky@ya.ru)

# 6. Остальное

* [TODO](https://github.com/afelix/csso/blob/master/TODO.md)
* CSSO распространяется под [лицензией MIT](https://github.com/afelix/csso/blob/master/MIT-LICENSE.txt)
