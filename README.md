# umi_database_size_optimize

umi-nsk.ru

Вариант 1:

0_clear_db.php - чистит базу данных от пустых корзин, оставшихся в базе данных по причине некорректно отрабатывающей самоочистки.

Недостатки: работает достаточно долго. создаёт промежуточный кэш файл со списком зарегистрированных пользователей и всеми оформленными заказами.

Преимущества: надёжно, базу не портит, проверен временем, чистил базы и 2гб,и 20 гб размером.

Пример использования: 

http://site.ru/0_clear_db.php?debug=2&limit=500

http://site.ru/0_clear_db.php?debug=2&refresh=1&limit=500

http://site.ru/0_clear_db.php?cron=1&limit=1000

refresh - будет автоматом чистить до конца

cron - для использования скрипта по расписанию

Вариант 2:

0_clear_db_nocache.php - вариант чистилки без создания кэша. В принципе рабочий вариант и быстрый, но на паре баз данных сбоил  и портил базу, потому пригоден только если есть бэкап базы 100%-ый.

http://site.ru/0_clear_db_nocache.php?cron=1&refresh=0&limit=40

http://site.ru/0_clear_db_nocache.php?cron=1&refresh=1&limit=5000



