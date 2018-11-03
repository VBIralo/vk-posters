Публикация постеров через API VK

# ВСЕ ДЕЙСТВИЯ ВЫ ВЫПОЛНЯЕТЕ НА СВОЙ СТРАХ И РИСК!!

## Порядок действий:
### 1. Получаем токен офф приложения.
```
https://oauth.vk.com/token?grant_type=password&client_id=2274003&client_secret=hHbZxrka2uZ6jB1inYsH&username={username}&password={password}&scope=all&2fa_supported=1
```

*Параметры:*
+ `{username}` -- Логин VK
+ `{password}` -- Пароль VK

Если есть двухфакторная авторизация, то придется сделать запрос повторно, добавив в запрос  &code={пришедший код}

### 2. Выполняем POST-запрос API.
```
https://api.vk.com/method/execute.wallPost?message={text}&poster_bkg_id={bkg_id}&access_token={access_token}&v=5.93
```

*Параметры:*
+ `{bkg_id}` -- ID фонового изображения (17) см. ниже
+ `{access_token}` -- Токен, полученный в 1 пункте
+ `{text}` -- Текст постера

## Фоны (bkg_id)

#### На картинки можно глянуть тут: https://danyadev.github.io/posters/

- Градиенты
> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
- Иллюстрации
> 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 31, 32
- Патерны Emoji
> 21, 22, 23, 24, 25, 26, 27, 28, 29, 30
