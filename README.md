# Arbitrazh Link Maker
Скрипт для автоматического создания ссылок

## Что делает
* Удаляет все содержимое папки домена на хостинге
* Регистрирует случайный (или с заданным именем) домен на выбранном поддерживаемом хостинге
  #### МОЖНО ОТКЛЮЧИТЬ ЧЕРЕЗ ОТДЕЛЬНЫЙ ПАРАМЕТР, ЧТОБЫ ВЫГРУЗИТЬ НА УЖЕ ЗАРЕГИСТРИРОВАННЫЙ ДОМЕН
* Генерирует вайтпейдж на [pl.ad-red.ru](https://pl.ad-red.ru/) по выбранному языку и тематике (можно указать через параметры к скрипту)
  #### МОЖНО ОТКЛЮЧИТЬ ЧЕРЕЗ ОТДЕЛЬНЫЙ ПАРАМЕТР, УКАЗЫВАЯ ПОЛНЫЙ ПУТЬ К АРХИВУ НА КОМПЬЮТЕРЕ
* Генерирует PHP файл клоаки [HideClick](https://hide.click), отключает режим отладки в нем и ставит УКР гео
  #### СВОЕ ГЕО НЕОБХОДИМО ПОДСТАВЛЯТЬ ОТДЕЛЬНО РЕДАКТИРУЯ ФАЙЛ НА ХОСТИНГЕ!
* Выгружает на домен по FTP файл клоаки, и разархивирует архивы white page и black page согласно следующей структуре:
    - domain.com/index.php - Файл клоаки
    - domain.com/\_\_page__ - Файлы black page
    - domain.com - Файлы white page
  #### ВАЖНО: Чтобы файл клоаки не перезаписался файлом index.php от white page - index файл от white page должен иметь название index.html 
  #### ДРУГИМИ СЛОВАМИ - ПРОСТО ПЕРЕИМЕНУЙТЕ index.php в white page архиве в index.html

## Поддерживаемые хостинги (на данный момент)
* Jino
* Beget

## Поддерживаемые клоаки (на данный момент)
* HideClick

## Как установить
* Устанавливаем [Nodejs](https://nodejs.org/) под свою платформу 
* Скачиваем архив с последней версией данного скрипта [(ссылка)](https://github.com/oneassasin/arbitrazh_link_maker/archive/master.zip) и куда-нибудь распаковываем на компьютере
* Переходим в папку с распакованным скриптом и выполняем команду ```npm install```
* Далее, переходим в папку src и в файле `config.ts` в поля `JINO_USER/JINO_PASSWORD`, `BEGET_USER/BEGET_PASSWORD`, `HIDE_CLICK_TOKEN` - заполняем свои данные от учетных записей
#### СКРИПТ НИКУДА НЕ СЛИВАЕТ ВАШИ ДАННЫЕ. ОНИ ХРАНЯТСЯ ТОЛЬКО НА КОМПЬЮТЕРЕ В ЭТОМ ТЕКСТОВОМ ФАЙЛЕ
#### Поскольку HIDE.CLICK единственная на данный момент клоака, что поддерживается скриптом — поле с токеном является обязательным. Остальные поля заполнять в зависимости от того, какой хостинг будет использоваться

## Как использовать
##### Отключение регистрации домена, выгрузка архивов white page и black page с компьютера на домен apqrtlyd.ru, хостинг jino
```npm start -- --register_domain=false --domain=apqrtlyd.ru --black_page_path=ПУТЬ_К_ZIP_АРХИВУ --white_page_path=ПУТЬ_К_ZIP_АРХИВУ```

##### Отключение регистрации домена, хостинг beget, выгрузка архивов white page и black page с компьютера на домен apqrtlyd.ru, хостинг jino
```npm start -- --register_domain=false --domain=apqrtlyd.ru --hosting=beget --black_page_path=ПУТЬ_К_ZIP_АРХИВУ --white_page_path=ПУТЬ_К_ZIP_АРХИВУ```

##### Регистрация случайного домена на jino, выгрузка white page и black page на этот домен
```npm start -- --black_page_path=ПУТЬ_К_ZIP_АРХИВУ --white_page_path=ПУТЬ_К_ZIP_АРХИВУ```

##### Регистрация случайного домена в зоне `.com` на jino, генерация white page на https://pl.ad-red.ru/, black page с zip архива на компьютере 
```npm start -- --black_page_path=ПУТЬ_К_ZIP_АРХИВУ```

##### Регистрация случайного домена в зоне `.com` на beget, генерация white page на https://pl.ad-red.ru/, black page с zip архива на компьютере
```npm start -- --black_page_path=ПУТЬ_К_ZIP_АРХИВУ --hosting=beget```

##### Помощь в использовании скрипта
```npm start help```

## Telegram автора 
https://t.me/b_b_ing

## Группа в телеграмм для бесплатных консультаций
https://t.me/arbitrazh_technic
