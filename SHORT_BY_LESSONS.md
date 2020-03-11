--------------------------------------
Введение:
 Необходимые инструменты для старта: Git, Node, npm, VSCode(WebStorm)
 Мои плагины: TsLint, AutoImport



--------------------------------------
Typescript, базовым синтаксис, базовые и продвинутые типы, tslint

 - Мотивация, зачем - https://basarat.gitbook.io/typescript/getting-started/why-typescript
 
 - Достоинства (можно погуглить)
 
 - Базовым синтаксис, типы, продвинутые типы - https://www.typescriptlang.org/docs/handbook/basic-types.html
 
 - Линтер (набор правил для консистентности кода) - https://palantir.github.io/tslint/
 
 - Typescript не понимает браузер, поэтому нужно транспилировать в JS. Но бывают много опций для транспиояции
 (в какой стандарт, в какую папку результат, типы из библиотек и тд) 
 Для этого нужен tsconfig - определет область транспиляции с конфигурацией - 
 https://www.typescriptlang.org/docs/handbook/compiler-options.html
 https://www.typescriptlang.org/docs/handbook/tsconfig-json.html
 
 - Откуда же беруться типы - устанавливаем npm i typescript - и в node_modules/typescript находим файлы определения
 Что возражает различные метобы, протипизированиые обьекты и тд
 
 - Нужно разделять реализацию и типизацию
 Например let a: number = 1 // number - это тип, а 1 значение
 
 Напримаер библиотека Lodash(https://lodash.com/) 
   - устанавилвам npm i lodash - но типов нет
   - устанавиваем типы для билиотеки npm i @types/lodash
   - Обычно пакеты с типами называются @types/имя-библиотеки
   - Можем проваливаться и видеть что возращают/принимают различные методы
   
 - Мы можем запускать typescript код без транспиляции в JS
Например библиотека ts-node (https://github.com/TypeStrong/ts-node)
--------------------------------------



Обзор фреймворка Angular
- Можно почитать  - https://habr.com/ru/post/348818/



--------------------------------------
Angular-cli - инструмент который позволяет создавать готовое ангулар приложение (стартер)
Сейчас это лидер и все его используют

- https://cli.angular.io/

- Установка на комп и команды для генерации/билда/запуска и тд - https://github.com/angular/angular-cli/wiki

- Так же позволяет генерировать сущности(компоненты/сервисы) - https://github.com/angular/angular-cli/wiki/generate

- В разеле Stories https://github.com/angular/angular-cli/wiki/stories
   - Можно прочитать как настроить assets(публичные данные - картинки, стили и тд)
   - Hot Module Replacement (перезагрузка только модуля изменений - без перезагрузки браузера)
   - Global Lib, Scripts, Styles
   - Про библиотеки - Material, Flex, AngularFire и тд
   - Proxy (как перенаправить запрос на другой адрес)
   - Интернационализация
   - Deploy to gh-pages
   - Application Environments
   - Universal Rendering
   - и тд (все все по ссылке Stories)