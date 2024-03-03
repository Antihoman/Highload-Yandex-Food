# Highload-Yandex-Food

## Содержание:
* ### [1. Тема и аудитория](#1)
* ### [2. Расчет нагрузки](#2)
* ### [3. Глобальная балансировка](#3)

## 1. Тема и аудитория: <a name="1"></a>
### Тема
**Яндекс Еда** — сервис заказа быстрой доставки еды из ресторанов и продуктов из магазинов через мобильные приложения или веб-сайт.

### Аудитория
* [Мужчины и женщины от 18 до 55 лет из России.]([https://www.similarweb.com/ru/website/eda.yandex/#demographics](https://yandex.ru/project/eda/itogigoda))
* [MAU: в месяц 15 млн.]([https://www.similarweb.com/ru/website/eda.yandex/#ranking](https://yandex.ru/project/eda/itogigoda))
* [Среднее время нахождение на сайте пользователем 11 минут]([https://www.similarweb.com/ru/website/eda.yandex/#ranking](https://yandex.ru/project/eda/itogigoda))

### Продуктовый функционал
* Регистрация и авторизация
* Поиск (рестораны, категории, блюда)
* Отслеживание заказа (просмотр, отслеживание, оценивание)
* Добавление ресторана (создание, загрузка блюд)
* Возможность оплаты заказа онлайн
* Основная лента с продуктами и промокодами

### Ключевые особенности:
* Просмотр карты с ресторанами и их рейтинга
* Рейтинг самых популярных блюд

## 2. Расчет нагрузки <a name="2"></a>

### Продуктовые метрики

* Месячная аудитория 15 млн
* Дневная аудитория 3,5 млн
* 250 тысяч заказов в день

#### Усредненные метрики

1. Регистрация:

```
Аудитория Яндекс еды выросла на 42% за прошедший год
   
Аудитория в 2023 году - 15 млн, в 2022 на 42% меньше, ~8,7 млн
   
Прирост аудитории за год - 6,3 млн
   
RPS: 6,3*10^6 зап / (365 д * 24 ч * 60 м * 60 с) = 0,2 зап / с
```
2. Авторизация:

```
Дневная аудитория Яндекс Еды: 3,5 млн

Среднее количество авторизаций в год около 2, далее продолжают использовать этот же аккаунт, не выходя
      
RPS: 3,5*10^6 * 2 зап / (365 д * 24 ч * 60 м * 60 с) = 0,22 зап / с
```
3. Поиск блюд или ресторанов:

```
Поиск блюд или ресторанов (в том числе конкретные блюда или поск внутри уже найденного ресторана)
люди осуществляют 2 раза в неделю (104 раза в год).

RPS: 3,5*10^6 * 104 зап / (365 д * 24 ч * 60 м * 60 с) = 11,5 зап / с
```

4. Создание заказа:

```
Каждый человек в среднем заказывает 2 заказа в неделю (104 раза в год), а его отдельные товары в среднем собирают с 4 разных страниц

RPS: 3,5*10^6 * 104 * 4 зап / (365 д * 24 ч * 60 м * 60 с) = 46,1 зап / с
```

5. Отслеживание заказа:

```
В среднем каждый второй человек интересуется, в каком состоянии сейчас его заказ, чтоб понимать, как скоро встречать курьера. (остальные просят оставить у двери или просят курьеров звонить)
Каждый человек в среднем заказывает 2 заказа в неделю (104 раза в год), но просматривает каждлый по 4-5 раз
Тогда среднее количество просмотра статуса заказа в год это 104 / 2 * 4,5 = 234

RPS: 3,5*10^6 * 234 зап / (365 д * 24 ч * 60 м * 60 с) = 26 зап / с
```

6. Оценивание заказа:

```
Каждый человек в среднем заказывает 2 заказа в неделю (104 раза в год), предложение оценить заказ выскакивает после каждого заказа, но оценивает примерно 40% пользователей

104 * 0,4 = 41,6

RPS: 3,5*10^6 * 41,6 зап / (365 д * 24 ч * 60 м * 60 с) = 4,6 зап / с
```

7. Добавление ресторана:

```
На данный момент в Яндекс Еде насчитывается около 6 тыс ресторанов, около 2 тяс были добавлены за последний год, но это касается не всех пользователей, а только владельцев ресторанов, которые составляют около 1%
   
RPS: 3,5*10^6*10^-3 * 2000 зап / (365 д * 24 ч * 60 м * 60 с) = 0,2 зап / с
```

8. Добавление блюд ресторана:

```
На данный момент в Яндекс Еде насчитывается около 6 тыс ресторанов, каждый из них добавляет или удаляет по 5 блюд каждую неделю (261 раз в году), но это касается не всех пользователей, а только владельцев ресторанов, которые составляют около 1%
   
RPS: 3,5*10^6*10^-3 * 261 * 6000 зап / (365 д * 24 ч * 60 м * 60 с) = 173,8 зап / с
```

9. Возможность оплаты заказа онлайн:
   
```
Сейчас почти 80% заказов оплачиваются онлайн
   
RPS: 3,5*10^6 * 0,8 * 52 зап / (365 д * 24 ч * 60 м * 60 с) = 4,6 зап / с
```

10. Основная лента с продуктами и промокодами

```
Это начальная страница, на которой окажется каждый, кто воспользуется приложением, в среднем заходят 6 раз в неделю (312 раз в год)
   
RPS: 3,5*10^6 *312 зап / (365 д * 24 ч * 60 м * 60 с) = 34,6 зап / с
```

#### Сводная таблица RPS по типовым действиям

| №  | Действие                        |  Тип   |   RPS    | RPD (x86400) |
|:--:|---------------------------------|:------:|:--------:|:------------:|
| 1  | Регистрация                     | Запись |   0,2    |   17,2 тыс   |
| 2  | Авторизация                     | Чтение |   0,22   |     19 тыс   |
| 3  | Поиск блюд или ресторанов       | Чтение |   11,5   |      1 млн   |
| 4  | Создание заказа                 | Запись |   46,1   |    3,9 млн   |
| 5  | Отслеживание заказа             | Чтение |   26     |    2,2 млн   | 
| 6  | Оценивание заказа               | Запись |   4,6    |    390 тыс   |
| 7  | Добавление ресторана            | Запись |   0,2    |   17,2 тыс   |
| 8  | Добавление блюд ресторана       | Запись |   173,8  |     15 млн   |
| 9  | Возможность оплаты заказа онлайн| Чтение |   4,6    |    400 тыс   |
| 10 | Основная лента с продуктами     | Чтение |   34,6   |    2,9 млн   |

### Технические метрики

**Информация о продукте**

```
id: 16 байт (UUID);
Картинки: 25 Мб в среднем (3-4 фото + иногда короткое видео в сжатом виде)
Текст: Примем, что в среднем описании 3-4 поля содержат по 50 символов, но их размер несравним с картинками
id ресторана: 16 байт (UUID);

Итого: ~25 Мб
```

**Информация о комментарии**

```
id: 16 байт (UUID);
Текст: Примем, что в среднем 1 комментарий содержит 50 символов. 
       1 символ в Unicode кодируется 2 байтами.
Дата создания: 4 байта (timestamp)
id поста: 16 байт (UUID);

Итого: 16 + 50*2 + 4 + 16 = 136 б
```

**Информация о ресторане**

```
id: 16 байт (UUID);
Текст: Примем, что в среднем 1 описание содержит 200 символов. 
       1 символ в Unicode кодируется 2 байтами.
Вложение: 5 Мб в среднем (1 фото)
Комментарии: в среднем 150 штук по 136 б

Ресторан без фотографии: 16 + 150*2 + 4 + 4 = 324 б
Ресторан с фотографией: 5 Мб
```

С момента создания Яндекс еды прошло 8 лет. С того момента было зарегистрировано 100 млн аккаунтов.

1. Создание комментариев:

```
Дневная аудитория 3,5 млн.
В среднем оценивает заказ 40% пользователей, а делают их в среднем 2 раза в неделю
    
Общий объем памяти в день: 3,5*10^6*0,4 * 2 / 7 дней * 136 б = 6,4 Мб / д
Общий объем памяти за квартал: 6,4 Мб / д * 30 д * 3 = 0,5 Гб
Общий объем памяти за год: 6,4 Мб / д * 365 д = 2,3 Гб
Общий объем памяти за все время: 2,3 Гб * 8 г = 18,4 Гб
```

2. Создание блюд:

```
В среднем пользователь просматривает 2-3 ресторана за заказ и просматривает 30% всех блюд ресторана, а заказывает около 2 раз в неделю, тогда:

Общий объем памяти в день: 3,5*10^6 * 2 / 7 дней * 25Мб * 100 = 2475 Тб / д
Общий объем памяти за квартал: 2475 Тб / д * 30 д * 3 мес = 219,5 Пб
Общий объем памяти за год: 2475 Тб / д * 365 д = 78 Эб
Общий объем памяти за все время: 78 Эб * 8 л = 624 Эб

```

3. Профили пользователей:

```
Общий объем хранилица: 100*10^6 акк * 50 Кб = 5 Тб
Общий объем памяти за год: 5 Тб / 8 л = 0,15 Тб
Общий объем памяти за квартал: 78 Гб
```

#### Сводная таблица объема памяти по типовым действиям

| № | Действие                        | Объем памяти за все время | Объем памяти за квартал | Объем памяти за год |
|:-:|---------------------------------|:-------------------------:|:-----------------------:|:-------------------:|
| 1 | Создание комментариев           |           18,4 Гб         |         0,5 Гб          |       2,3 Гб        |
| 2 | Создание блюд                   |           624 Эб          |         219,5 Пб        |       78 Эб         |
| 3 | Профили пользователей           |           5 Тб            |         78 Гб           |       0,15 Тб       |

### Сетевой трафик

1. Регистрация:

```
0,2 * 50 Кб = 10 Кб/с
```

2. Авторизация:

```
0,22 * 50,4 Кб = 11 Кб/с
```

3. Добавление блюд:
   
```
173,8 * 25 Мб = 4,4 Гб/с
```

4. Создание заказов:
   
```
46,1 * 25 Мб = 1,1 Гб/с
```

5. Оценка заказов:
   
```
4,6 * 5Мб = 23 Мб/с
```

6. Поиск блюд:
   
```
11,5 * 25 Мб * 5 = 1,2 Гб/с
```

7. Оплата заказов:
    
```
4,6 * 1 Мб = 4,6 Мб/с
```

8. Просмотр основной ленты:
    
```
34,6 * 25 Мб * 10 = 8,7 Гб/с
```

[Пиковый трафик в 1,7 раз больше среднего](https://github.com/Antihoman/Highload-Yandex-Food/blob/main/img/timeline-cities.png)

| №  | Действие                        | Средний трафик | Пиковый трафик |
|:--:|---------------------------------|:--------------:|:--------------:|
| 1  | Регистрация                     |     10 Кб/с    |     17 Кб/с    |
| 2  | Авторизация                     |     11 Кб/с    |     19 Кб/с    |
| 3  | Добавление блюд                 |    4,4 Гб/с    |      8 Гб/с    |
| 4  | Создание заказов                |    1,1 Гб/с    |    1,8 Кб/с    |
| 5  | Оценка заказов                  |     23 Мб/с    |     40 Мб/с    |
| 6  | Поиск блюд                      |    1,2 Гб/с    |    1,9 Гб/с    |
| 7  | Оплата заказов                  |    4,6 Мб/с    |      8 Мб/с    |
| 8  | Просмотр основной ленты         |    8,7 Гб/с    |     15 Гб/с    |

---

## 3. Глобальная балансировка нагрузки <a name="3"></a>

### Расположение датацентров

Так как большая часть аудитории Яндекс Еды располагается в России, то все датацентры будут расположены на территории России.

Так как население России распределено неравномерно, нам потребуются расположить основную часть датацентров в европейской части страны,
но также будут установлены в южной части Сибири и Дальнего Востока.

Следовательно, были выбраны следующие города для установки датацентров:

* Москва
* Санкт-Петербург
* Казань
* Волгоград
* Екатеринбург
* Новосибирск
* Благовещанск

![Population_dencity](https://github.com/Antihoman/Highload-Yandex-Food/assets/91897029/28effa2c-4b65-4f91-a60e-913a96dc6daa)

### Глобальная балансировка 

С помощью GeoDNS будем определять физически ближайший к пользователю ЦОД. ЦОД-ы будут отвечать за следующие районы:

* Благовещанск -> Дальний Восток
* Новосибирск -> Сибирь
* Екатеринбург, Казань, Волгоград -> Европейская часть России
* Москва -> Москва, Московская область
* Санкт-Петербург -> Санкт-Петербург, Ленинградская область

Далее с помощью BGP Anycast определить для каждого района свой ЦОД, чтоб улучшить балансировку.

---

