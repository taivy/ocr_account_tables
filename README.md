# Сервис для распознавания таблиц с бухгалтерских отчетностей

Распознает таблицы с бухгалтерских отчетностей (например https://github.com/taivy/ocr_account_tables/blob/master/ocr_buhuchet_app/data_to_load/tmk_rsbu317.pdf ) и выдаёт в формате JSON.

# Технологии

Язык - Python. Использовался фреймворк Flask чтобы создать простой веб-интерфейс. Распознавание делается за счет API Yandex Vision.

# Процесс работы 

В веб-интерфейсе загружается файл с отчетностью в формате pdf. Сервис достаёт из него страницы как отдельные картинки (с помощью библиотеки pdf2image). Потом делается запрос к API Yandex Vision. API отдаёт блоки текста на картинке - их содержание и координаты. На основе координат определяется, к какой ячейке, столбцу и строке относится значение. 

# Запуск

`docker-compose up -d`

и перейти на localhost:5000

