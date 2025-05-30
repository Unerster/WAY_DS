# Интернет - магазин "Клик в одну точку"
# Описание проекта
Интернет-магазин «В один клик» продаёт разные товары: для детей, для дома, мелкую бытовую технику, косметику и даже продукты. Отчёт магазина за прошлый период показал, что активность покупателей начала снижаться. Привлекать новых клиентов уже не так эффективно: о магазине и так знает большая часть целевой аудитории. Возможный выход — удерживать активность постоянных клиентов. Сделать это можно с помощью персонализированных предложений.
У компании есть небольшой отдел цифровых технологий, и нам предстоит побыть в роли стажёра в этом отделе. 
Итак, нашему отделу поручили разработать решение, которое позволит персонализировать предложения постоянным клиентам, чтобы увеличить их покупательскую активность.

`market_file.csv` - таблица, которая содержит данные о поведении покупателя на сайте, о коммуникациях с покупателем и его продуктовом поведении.

- `id` - номер покупателя в корпоративной базе данных
- `Покупательская активность` - рассчитанный класс покупательской активности (целевой признак): «снизилась» или «прежний уровень».
- `Тип сервиса` - уровень сервиса, например «премиум» и «стандарт».
- `Разрешить сообщать` - информация о том, можно ли присылать покупателю дополнительные предложения о товаре. Согласие на это даёт покупатель.
- `Маркет_актив_6_мес` - среднемесячное значение маркетинговых коммуникаций компании, которое приходилось на покупателя за последние 6 месяцев. Это значение показывает, какое число рассылок, звонков, показов рекламы и прочего приходилось на клиента.
- `Маркет_актив_тек_мес` - количество маркетинговых коммуникаций в текущем месяце.
- `Длительность` - значение, которое показывает, сколько дней прошло с момента регистрации покупателя на сайте.
- `Акционные_покупки` - среднемесячная доля покупок по акции от общего числа покупок за последние 6 месяцев.
- `Популярная_категория` - самая популярная категория товаров у покупателя за последние 6 месяцев.
- `Средний_просмотр_категорий_за_визит` - показывает, сколько в среднем категорий покупатель просмотрел за визит в течение последнего месяца.
- `Неоплаченные_продукты_штук_квартал` - общее число неоплаченных товаров в корзине за последние 3 месяца.
- `Ошибка_сервиса` - число сбоев, которые коснулись покупателя во время посещения сайта.
- `Страниц_за_визит` - среднее количество страниц, которые просмотрел покупатель за один визит на сайт за последние 3 месяца.

`market_money.csv` - таблица с данными о выручке, которую получает магазин с покупателя, то есть сколько покупатель всего потратил за период взаимодействия с сайтом.

- `id` - номер покупателя в корпоративной базе данных.
- `Период` - название периода, во время которого зафиксирована выручка. Например, 'текущий_месяц' или 'предыдущий_месяц'.
- `Выручка` - сумма выручки за период.

`market_time.csv` - таблица с данными о времени (в минутах), которое покупатель провёл на сайте в течение периода.

- `id ` - номер покупателя в корпоративной базе данных.
- `Период` - название периода, во время которого зафиксировано общее время.
- `минут` - значение времени, проведённого на сайте, в минутах.

`money.csv` - таблица с данными о среднемесячной прибыли покупателя за последние 3 месяца: какую прибыль получает магазин от продаж каждому покупателю

- `id` - номер покупателя в корпоративной базе данных.
- `Прибыль` - значение прибыли.



# Цель проекта
Разработать решение для увеличения покупательской активности.

# Задачи
1) Построим модель, которая предскажет вероятность снижения покупательской активности клиента в следующие три месяца.
2) Добавим дополнительные данные финансового департамента о прибыльности клиента: какой доход каждый покупатель приносил компании за последние три месяца.
3) Выделим сегменты покупателей и разработаем для них персонализированные предложения.я

# План работы
1) Загрузка данных.
2) Предобработка данных
3) Исследовательский анализ.
4) Объединим таблицы.
5) Корреляционный анализ.
6) Применим пайплайны.
7) Проведем анализ важности признаков.
8) Проанализируем сегментацию покупателей.
9) Подведём итоги.

# Вывод
Для нас были поставлены задачи:
1) Разработать модель, которая предскажет вероятность снижения покупательской активности.
2) Выделить сегмент покупателей, проанализировать их и предложить, как увеличить их покупательскую активность.

Исходные данные: 
 - Таблица, которая содержит данные о поведении покупателя на сайте, о коммуникациях с покупателем и его продуктовом поведении.
 - Таблица с данными о выручке, которую получает магазин с покупателя, то есть сколько покупатель всего потратил за период взаимодействия с сайтом.
 - Таблица с данными о времени (в минутах), которое покупатель провёл на сайте в течение периода.
 - Таблица с данными о среднемесячной прибыли продавца за последние 3 месяца: какую прибыль получает магазин от продаж каждому покупателю.

Что для этого было сделано:

1) Загрузили данны и необходимые библиотеки.
2) Сделали предобработку данных:
   
    - название столбцов привели к строчному прописанию.
    - пропусков не обнаружено.
    - Изменили в столбцах `маркет_актив_6_мес`, `акционные_покупки`, `выручка` тип данных  с str на float.
    - Заменили предыдцщий_месяц на предыдущий_месяц
    - Заменили стандартт на стандарт
    - Явные и неявные дубликаты не обнаружены

3) Провели исследовательский анализ данных:

    - Было удалено 4 пользователя: 1 с аномальной выручкой и остальные с слишком низкой выручкой.
    - Отобраны пользователи с покупательсокой активностью не менее 3 месяцев.

4) Объединили таблицы `market_file.csv`, `market_money.csv`, `market_time.csv`. Получили итоговую таблицу с новыми столбцами: `выручка_препред`, `выручка_пред`, `выручка_тек`, `минут_пред`, `минут_тек`.
5) Корреляционный анализ показал, что между входными признаками не большие зависимости, кроме `выручка_тек` и `выручка_пред`. Для уменьшения влияние мультиколлиниарности не учитывали столбец `выручка_тек` при обучении модели.
6) Использовали пайплайн для поиска лучшей модели:

    - Обучили четыре модели: KNeighborsClassifier(), DecisionTreeClassifier(), LogisticRegression() и SVC(). Для каждой из них подбрали разный набор гиперпараметров.
    - Использовали метрику ROC-AUC как основную, дополнительно оценили метрику F1-score
    - Получили лучшую модель LogisticRegression() с параметрами (C=1, penalty='l1', random_state=42, solver='liblinear')
    - Значение метрик ROC-AUC = 0.90 на тренировочной и ROC-AUC = 0.91, F1-score = 0.86 на тестовой выборке. 

7) Проанализировали важность признаков:

    - Чем больше значения признаков `неоплаченные_продукты_штук_квартал`, `акционные_покупки`, `длительность` тем вероятней актиновсть покупателя `Снизилась`.
    - Признаки: `тип_сервиса_стандарт`, `разрешить_сообщать_нет`, `маркет_актив_тек_мес`, `выручка_пред` меньше всех повлияли на активность покупателя.
    - Чем больше значения всех остальных признаков, тем вероятней, что покупательская активность осталась на прежнем уровне.
    - Для бизнеса нужно обратить на таких клиентов, которые мало проводят вермени на сайте, просматривают немного категорий, предпочитают покупать по акциям, у них много неопалченных товаров в корзине и оценить сколько на них действует маркетинговых кооммуникаций, возможно их стоит сделать больше. Для повышения покупательской активности таких клиентов, нужно подготовить какие-либо специальные предложения, акции, промокоды.
8) Выделили сегмент покупателей, провели анализ. Наиболее важные выводы для бизнеса:

    - Нужно обратить внимание на клиентов на которых мало задейстовано маркентинга(меньше 3), они в основом и имеют низкую активность.
    - Покупательская активность снизилась у группы клиентов, которые покупают товары в основом по акциям, для них нужно больше спец.предложений
    - Средемесячна прибыль с одного клиента равна примерно от 1300 до 4600(это 75% клиентов), остальная часть(25%) готова платить до 6900 рублей. Нет смысла предлагать клиентам особо дорогие товары, нужно ориентироваться на сумму 1300 - 4600 рублей. Те кто платит больше скорей всего покупают товары с длинным сроком жизни(техника).
    - Категории `Товары для детей`, `Техника для красоты и здоровья`, `Домашний текстиль` пользуется большим спросом среди остальных. Данные категории наводят на мысль что покупатели в основном женщины, которые любят делать покупки для детей, для своего здоровья и домашнего уюта.
    - Скорей всего для класса `Снизилась` нужно продумать более точечный маркетинг нацеленный на женщин и на определенные товары. Так как в группе `Снизилась` преобладает категории `Товары для детей` и `Техника для красоты и здоровья`, то можно сделать фокус именно на них, предлагая заманчивые предложения, акции, промокоды

9) Выделили дополнительный сегмент покупателей: группа клиентов с максимальной долей покупок по акции и высокой вероятностью снижения покупательской активности. Рекомендации для бизнеса:

    - маркетинг для клиентов есть, но для кого-то больше для кого-то меньше, и непонятно на что именно он направлен, возможно нужно больше привлекать внимания на категории `Товары для детей` и `Домашний текстиль`.
    - в среднем просматривается немного категорий 2-3, скорей всего это и есть `Товары для детей` и `Домашний текстиль`
    - в корзине в среднем на одного человека по 4 неоплаченных заказа, возможно на них стоит сделать спец предложения
    - в среднем клиент тратит 10 минут на сайте за месяц, не так много, нужно как то привлечь внимание, задеражать на сайте
    - среднемесячная прибыль от одного клиента примерно от 1600 до 4500(75% клиентов), остальные готовы заплатить примерно до 5600. Не стоит предлагать таким клиентам слшишком дорогие товары, желательно в диапазоне от 1600 - 4500 рублей.
