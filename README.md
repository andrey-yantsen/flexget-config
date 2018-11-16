Данный конфиг для [FlexGet](https://flexget.com/) позволяет вам не беспокоиться о выходе
пиратских копий новых фильмов — все они будут автоматически скачиваться к вам,
практически одновременно с появлением их на трекерах. В качестве торрент-клиента в
конфиге используется Deluge, все фильмы скачиваются в папку
`/Volumes/External/Downloads/`, а по окончанию загрузки — перемещаются в
`/Volumes/External/Movies/{{ movie_name }} ({{ movie_year }})` (т.е.
для фильма "Atomic Blonde" 2017 года папка в итоге будет называться `/Volumes/External/Movies/Atomic Blonde (2017)`).

В связи со спецификой FlexGet для анализа torrent-файла его нужно предварительно скачать, для этого в конфиге используется директория `/root/.flexget/torrents/`. Не забывайте удалять из неё старые файлы, например вот такой командой: `find /root/.flexget/torrents/ -mtime +7 -delete`.

При добавлении в очередь загрузки нового фильма вам будет приходить письмо на почту.

Наличие новых фильмов проверяется каждые 10 минут, запуск скачивания происходит каждые 30 минут.

Для корректной работы всего этого нужно заменить все явки-пароли (значения указанные в
треугольных скобках, например `<DELUGE_HOST>`) на корректные.

Раздачи собираются из следующих источников:
- rutracker: Зарубежное кино (HD Video)
- rutracker: Зарубежное кино / Фильмы 2006-2010
- rutracker: Зарубежное кино / Фильмы 2011-2015
- rutracker: Зарубежное кино / Фильмы 2016-2017
- rutracker: Наше кино (HD Video)
- rutor: Зарубежные фильмы
- rutor: Мультипликация
- rutor: Наши фильмы

Вот критерии выбора раздач:
- Раздача содержит хотя бы один файл с расширением `avi`, `mkv`, `mp4`, `webm`, `m4p`, `m4v`, `mpg` или `mpeg`
- В заголовке нет пометки iPhone / iPad. Так же игнорируются различные расширенные версии
- Разрешены только дубляж, лицензии и релизы iTunes (определяется по названию раздачи)
- Минимальное допустимое качества рипа — r5
- Размер раздачи от 1.3 до 16гб
- Любой жанр кроме документальных, музыкальных, исторических, биографических и военных фильмов
- Релиз был не более 35 лет назад
- В течении 24 часов идёт ожидание более качественного релиза и в итоге будет скачана либо версия 1080p, либо самое лучше качество, что попалось за это время
- Рейтинг IMDB от 6.3, не менее 1000 голосов.
