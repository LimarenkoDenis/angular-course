1. Typescript - https://github.com/LimarenkoDenis/GL-ts-lesson


2. Angular
- make a fork - https://github.com/LimarenkoDenis/angular-2020
- clone project
- create [yourName] directory and create angular cli project there
- complete lesson task 
- Make a PR to LimarenkoDenis:master

PS
Используйте строгий tslint или ts правила (рекомендую https://github.com/LimarenkoDenis/ithillel-angular-course/blob/master/tslint.json)
Установите tslint расшерение для редактора, увидел подсвечивали красным правила некоторые


--------------------------------------


 
### Создать проэкт с angular-cli

- https://drive.google.com/open?id=1Tw3xXN8UMcR8N-2ZZsUB3TkJfOTc1Q20 - верстка

###  Разбить на компоненты 
- app-hotels (модуль и главная компонента)
- list
- weather component
- profile component 

#### Можем добавить компоненты по желанию
- header
- footer
- nav bar for feature navigation
- подключить и поиспольовать компоненты angular material
 --------------------------------------     


1) app-hotels - здесь данные
damn component, ничего не знают о данных, в них только @Input, @Output
2) list - пробросить список и с ngFor отрисовать
3) weather component - @Input decorator, прибайндить данные и отобразить их там (данные о погоде)
4) profile component - прибайндить данные и отобразить их там (данные с профайла)
5) протипизировать
6) Кликаем по одному элементу отеля и перерисовываются данные других виджетов, @Output() (selectedHotel, или selectedHotelId - в app.component )
примерное демо https://limarenkodenis.github.io/ng2weatherwidget/

Пример
<weather [weather]="hotel.weather">


  Данные
  ```
  public hotels: Hotel[] = [
    {
      id: 0,
      title: 'Universal Cabana',
      address: 'Orlando',
      description: 'Best one!',
      phone: '+3242353434',
      picture: 'assets/images/1.jpg',
      photos: [
        'assets/images/res.jpg',
        'assets/images/r1.jpg'
      ],
      weather:  {
        temperature: 12,
        wind: 11,
        icon: 'sun'
      },
      profile: {
        followers: 112,
        following: 11,
        photo: 'assets/images/b1.jpg'
      },
      stars: 3
    },
    {
      id: 1,
      title: 'Kharkov plaza',
      address: 'Kharkov',
      description: 'Five Stars',
      phone: '+3242353434',
      picture: 'assets/images/2.jpg',
      photos: [
        'assets/images/res.jpg',
        'assets/images/r1.jpg'
      ],
      weather:  {
        temperature: 5,
        wind: 4,
        icon: 'rain'
      },
      profile: {
        followers: 12,
        following: 111,
        photo: 'assets/images/b2.jpg'
      },
      stars: 4
    },
    {
      id: 2,
      title: 'Hotel name',
      address: 'Orlando',
      description: 'Lorem ipson0',
      phone: '+3242353434',
      picture: 'assets/images/3.jpg',
      photos: [
        'assets/images/res.jpg',
        'assets/images/r1.jpg'
      ],
      weather:  {
        temperature: -2,
        wind: 2,
        icon: 'cloud'
      },
      profile: {
        followers: 45,
        following: 78,
        photo: 'assets/images/b3.jpg'
      },
      stars: 5
    }
  ];
  ```
  
 --------------------------------------
 
 
### Directives, Pipes
- Реализовать поиск по отелям
  - инпут поле - поиск по title и description
  - вместо | Hotel | Fishing | Tours | Weather | - сортировку по звездам (можно All | *** | **** | *****)
  - и чтобы они вместе работали 

- добавить компоненту favorites hotels 
      - данные в app-hotels, на том же уровне где и hotels, selectedHotel
      - отображает список
- в список к каждому элементу добавить кновпу +Add to favorites (можно под двемя картинками в списке) 
- при клике на +Add to favorites добавляется элемент в favorites hotels 
- удалить элемент из favorites, кликаем на [x] - удаляем hotel из списка favorites
- для advanced 
      - нотификации 
            - 'Добавлено в favorites!'
            - 'Удалено из favorites!'
            - Если элемент уже есть в списке favorites
                  - или попап что уже добавлен
                  - или считать колличетсво нажатий (voted - IFavoriteHotel расширить полем от IHotel)
- сделать загрузку hotels асинхронной (setTimeout, 3 sec) - 
- для advanced - можно сделать спискок this.hotels$ = of(mockedHotels).pipe(delay(3000)) 
- для advanced - кастомная директива, навешиваем на hotels list, пока гдузиться сделать оверлей над списком
- Loading... текст вместо директивы - попроще
- подсвечивать четные отели другим цветом (зебра)




### RXJS 
 
- Посмотреть офиц доку
- Курсы
- Видео

   
### Services

- Services
  - Создать Service
      - перенести все хардкод данные из родительского компонента в сервис
      - реализовать общение данных через сервис (убираем многовложеные Input, Output)
              - методы (getHotels, getFavorites, addToFavorites, deleteFavorite, ...)
          
      Advanced level
      - Сделать так, чтоб методы возвращали Observable (желательно все)
      - Сделать свойства компонентов Observable (hotels$, favorites$, ...) и использовать async pipe в шаблоне

### http client, api

- https://github.com/typicode/json-server - часто используется пока нет бека и потом лечго подменяется на существующий
- сделать и запустить фековый сервер из json (данные что и были), паралельно запущен и фронт и api
- изучить постман(кто не знает) и поиграться, поделать запросы, получить, обновить, удалить данные (crud)
- Реализовать через сервис 
    - GET /hotels?_page=myPage&_limit=MyLimit - получение списка отелей и расширить пагинацией
            (angular material paginator можно взять как компонентту - но все через запросы потом)
            используем angular params
            можно подобавлять больше отелей данных
    - POST /favorites 
    - Если уже есть отель в favorites то 
        PATCH /favorites/:id - обновить колличетво голосований
    - DELETE /favorites/:id - удалить
    - url выносим в environment файлы (пробуем запускать в dev и prod моде)
        
  В итоге мы убираем все захардкодженые данные - они выносятся на фейковый сервер  иделаем запросы через сервис
  Сортировка и пайпы пока остануться работать только с данными что загрузились - можно оставить или подумать как переделать
        
- Advanced
  - добавить админа (в локалстородж ложим token)
  - добавить кнопку Удалить отель
  - скрываем для тех пользователей у который нет токена в локалсторадже (структурная директива)
  - через сервис дергаем DELETE /hotels/:id но перед этим вытаскиваем токен и отправляем в http headers 'Authorization' (angular headers) 
  - добавить Angular Interseptor и перехватываем каждый запрос и к каждому запросу накивем Authorization headers с токеном
  - Запровайдить url с Injector Token и инджектив в сервис
    
      
### angular router and navigation

 - главное меню (hotels, About this project, users, Contacts us )
      - страница списка отелей и фаворитс
      - при клике на елемент (из hotel list) - переходи на стр hotel-detail и берез id param из url
      - hotel-detail - загрузить инфо об отеле и 2е вложеные навигации
            - comments
            - contacts
      - страница  'About this project' с любой инфой
      - users (добавить AuthGuard) 
            - есть 'token' в локалстторадж - то отображаем пункт меню и даем возможность перехода
            - нет 'token' в локалстторадж - скрываем директивой и guard (если руками вбиваем в url)
      - страница Contacts us 
            - флажок editMode и если editMode true - то не давать уходить с этой страницы и показать попап
            - если editMode false  - то даем возможность покинуть стр
            через canDeactivate
      - сделать hotels, Contacts us, users модулями и реализовать ленивую загрузку 
      - при клике на пагинацию обновлять query params в url (поделиться ссылкой)
      
Advanced 
      - расширить данные (fake json server json)
      - добавить comments и свзятьать по id с hotels 
      - на стр hotel detail - comments - загружать коменты конкретного отеля
      



### Формы (Reactive forms)

Предлагаю форму регистрации на отдельной странице
- name
- surname 
- email
- password 
- confirm Password 
- Дата рождения - select options (невозможность выбора 30 февраля и тд)
- radio button (мужчина, женщина)


- Классические валидации
- Валидации на password, confirm Password на совпадение и на классические правила 8 символов и тд
- Глазик фича, показать/скрыть пароль
- Стилизация и сообщения с ошибками (динамическая, по покиданию поля, конкретные ошибки по каждому правилу)

Форма опросник через formArray
- добавить/удалить варианты ответа 

Advanced: 
- Добавить вопрос 
  - добавить вариант ответа 
  - удалить вариант ответа 

      
      
### Redux, Ngrx
- Переделать на ngrx
    - загрузка отелей
    - добавление/удаление отелей в favorites
Или добавить Ngrx не трогая предыдущий функционал:
- Bookmarks - как и favorites - но с ngrx флоу (как с Cart на занятии - синхронно)
- Или Добавить Users модуль - C Effects async, флоу загрузки
      
            
Advanced ngrx
    - Добавить ngrx Router store