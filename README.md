# Проект для анализа и визуализации данных об акциях

## Общий обзор

Этот проект предназначен для загрузки исторических данных об акциях и их визуализации. Он использует библиотеку yfinance для получения данных и matplotlib для создания графиков. Пользователи могут выбирать различные тикеры и временные периоды для анализа, а также просматривать движение цен и скользящие средние на графике.



### Структура и модули проекта
<br>
1. data_download.py:

- Отвечает за загрузку данных об акциях.

- Содержит функции для извлечения данных об акциях из интернета и расчёта скользящего среднего.


<br>
2. main.py:

- Является точкой входа в программу.

- Запрашивает у пользователя тикер акции и временной период, загружает данные, обрабатывает их и выводит результаты в виде графика.


<br>
3. data_plotting.py:

- Отвечает за визуализацию данных.

- Содержит функции для создания и сохранения графиков цен закрытия и скользящих средних.



### Описание функций


<br>
1. data_download.py:

- fetch_stock_data(ticker, period): Получает исторические данные об акциях для указанного тикера и временного периода. Возвращает DataFrame с данными.

- add_moving_average(data, window_size): Добавляет в DataFrame колонку со скользящим средним, рассчитанным на основе цен закрытия.

- calculate_and_display_average_price(data): Вычисляет и выводит среднюю цену закрытия акций за заданный период.
<img src="https://github.com/KatKabaev/Project_1/blob/main/assets/1.png">

- notify_if_strong_fluctuations(data, threshold): Анализирует данные и уведомляет пользователя, если цена акций колебалась более чем на заданный процент за период.
<img src="https://github.com/KatKabaev/Project_1/blob/main/assets/2.png">

- export_data_to_csv(data, filename): Позволяет сохранять загруженные данные об акциях в CSV файл.
<img src="https://github.com/KatKabaev/Project_1/blob/main/assets/3.png">

- calculate_rsi(data): Добавляет на графике дополнительные технические индикаторы (RSI)
<img src="https://github.com/KatKabaev/Project_1/blob/main/%D0%9F%D1%80%D0%BE%D0%B5%D0%BA%D1%82%201/AAPL_1mo_stock_price_chart.png">

<br>
2. main.py:

- main(): Основная функция, управляющая процессом загрузки, обработки данных и их визуализации. Запрашивает у пользователя ввод данных, вызывает функции загрузки и обработки данных, а затем передаёт результаты на визуализацию.


<br>
3. data_plotting.py:

- create_and_save_plot(data, ticker, period, filename): Создаёт график, отображающий цены закрытия и скользящие средние. Предоставляет возможность сохранения графика в файл. Параметр filename опционален; если он не указан, имя файла генерируется автоматически.



### Пошаговое использование

1. Запустите main.py.

2. Введите интересующий вас тикер акции (например, 'AAPL' для Apple Inc).

3. Введите желаемый временной период для анализа (например, '1mo' для данных за один месяц).

4. Программа обработает введённые данные, загрузит соответствующие данные об акциях, рассчитает скользящее среднее и отобразит график.

