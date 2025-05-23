# Описание проекта
Сравнение Москвы и Петербурга окружено мифами:
  * Москва — мегаполис, подчинённый жёсткому ритму рабочей недели;
  * Петербург — город своеобразной культуры, непохожий на Москву.

Некоторые мифы отражают действительность. Другие — пустые стереотипы. Бизнес должен отличать первые от вторых, чтобы принимать рациональные решения. На реальных данных Яндекс Музыки мы проверим гипотезы и сравним поведение пользователей двух столиц.

# Гипотизы 
1. Активность пользователей зависит от дня недели. Причём в Москве и Петербурге это проявляется по-разному.
2. Утром в понедельник в Москве преобладают одни жанры музыки, а в Петербурге — другие. Это верно и для вечера пятницы.
3. Москва и Петербург предпочитают разные жанры музыки. В Москве чаще слушают поп-музыку, в Петербурге — русский рэп.

# Данные

## Описание колонок 

 * `userID` — идентификатор пользователя;
 * `Track` — название трека;
 * `artist` — имя исполнителя;
 * `genre` — название жанра;
 * `City` — город пользователя;
 * `time`— время начала прослушивания;
 * `Day` — день недели.

# Ход исследования
Данные о поведении пользователей мы получите из файла `yandex_music_project.csv`. О качестве данных ничего не известно. Поэтому перед проверкой гипотез понадобится обзор данных.

Мы проверим данные на ошибки и оценим их влияние на исследование. Затем, на этапе предобработки мы поищим возможность исправить самые критичные ошибки данных.

Таким образом, исследование пройдёт в три этапа:
1. Обзор данных.
2. Предобработка данных.
3. Проверка гипотез.

# Вывод
Мы проверили три гипотезы и установили:

1. День недели по-разному влияет на активность пользователей в Москве и Петербурге.

Первая гипотеза полностью подтвердилась.

2. Музыкальные предпочтения не сильно меняются в течение недели — будь то Москва или Петербург. Небольшие различия заметны в начале недели, по понедельникам:
* в Москве слушают музыку жанра “world”,
* в Петербурге — джаз и классику.

Таким образом, вторая гипотеза подтвердилась лишь отчасти. Этот результат мог оказаться иным, если бы не пропуски в данных.

3. Во вкусах пользователей Москвы и Петербурга больше общего, чем различий. Вопреки ожиданиям, предпочтения жанров в Петербурге напоминают московские.

Третья гипотеза не подтвердилась. Если различия в предпочтениях и существуют, на основной массе пользователей они незаметны.

**На практике исследования содержат проверки статистических гипотез.**
Из части данных одного сервиса невозможно сделать какие-то выводы о всех пользователях сервиса без методов статистики.
Проверки статистических гипотез покажут, насколько они достоверны, исходя из имеющихся данных.
С методами проверок гипотез вы ещё познакомитесь в следующих темах.

