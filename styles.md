# Стили

------
Описать иначе!
------









## Основные положения:
* Чтобы определить html-структуру блока и задать ему оформление, мы используем параметр `view`.
* Параметр `view` можно задавать только в `btjson`. Мы считаем, что блок не может менять свои представление и html-структуру в браузере. Если это происходит, мы считаем, что блок становится чем-то иным, нежели он есть — становится другим блоком.
* `state` — состояния блока. Использовать их без конкретного view бессмысленно, потому что состояния существуют только в рамках конкретного варианта оформления. Состояния могут меняться прямо на странице в браузере.
* По умолчанию **каждый** `islets`-блок стилизуется с использованием параметра `view` в значении `islet`. У блока устанавливается зависимость от своего `view: islet`.
* Мы пишем стили с использованием [stylus](http://learnboost.github.io/stylus/).
* При формировании стилей для отображения (`view`) блоков, используются `stylus`-миксины. Миксины являются составными фрагментами для формирования оформления тех или иных типов оформления. Миксины расположены в модификаторе `skin`, и подключаются в `view` с помощью `deps`-файлов.

## В результате получаем

1. Гарантированная работа заранее известных вариантов оформления.
2. Понятный список вариаций оформления тех или иных библиотечных блоков.
3. Упрощение поддержки стилей и добавления новых.
4. Возможность для проектов, в которых используется `islets`, делать новые темы оформления, не отменяя уже существующие стили (так как по умолчанию в блоках без `view` нет стилизации).