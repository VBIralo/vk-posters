# vk-posters
Публикация постеров через API VK


# ВСЕ ДЕЙСТВИЯ ВЫ ВЫПОЛНЯЕТЕ НА СВОЙ СТРАХ И РИСК!!


## Порядок действий:
### 1. Получаем токен офф приложения.
```
https://oauth.vk.com/token?grant_type=password&client_id=2274003&client_secret=hHbZxrka2uZ6jB1inYsH&username={username}&password={password}&scope=all&v=5.93&2fa_supported={2fa}&lang=ru&device_id={device_id}&libverify_support=1
```

*Параметры:*
+ {username} -- Логин VK
+ {password} -- Пароль VK
+ {device_id} -- Грубо говоря, рандомная строка
+ {2fa} -- Если используем 2fa, то ставим 1. Не используем - 0

### 2. Выполняем POST-запрос API.
```
POST /method/execute.wallPost HTTP/1.1
Cache-Control: no-cache
X-Get-Processing-Time: 1
User-Agent: VKAndroidApp/5.21-2896 (Android 8.0.0; SM-G965F Build/R16NW; ru; 2960x1440)
X-VK-Android-Client: new
Content-Type: application/x-www-form-urlencoded
Host: api.vk.com
Connection: Keep-Alive
Accept-Encoding: gzip
Cookie: remixlang=114

v=5.93&https=1&ref=newsfeed&owner_id={your_id}&mark_as_ads={mark_as_ads}&lang=ru&close_comments={close_comments}&poster_bkg_id={bkg_id}&access_token={access_token}&message={text}
```

*Параметры:*
+ {your_id} -- Ваш ид (12345678)
+ {mark_as_ads} -- Отметить как рекламный пост (0)
+ {close_comments} -- Выключить комментрарии (0)
+ {bkg_id} -- ID фонового изображения (17) см. ниже
+ {access_token} -- Токен см. 1 пункт
+ {text} -- Текст постера

## Фоны (bkg_id)
- Градиенты
> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
- Иллюстрации
> 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 31, 32
- Патерны Emoji
> 21, 22, 23, 24, 25, 26, 27, 28, 29, 30
