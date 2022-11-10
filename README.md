# Проект парсера PEP

## Описание проекта
Учебный парсер, парсящий домены https://peps.python.org/ и https://docs.
python.org/3/ через requests cache и bs4

## Технологический стек
- ![workflow](https://github.com/dvkonstantinov/foodgram-project-react/actions/workflows/foodgram_workflow.yml/badge.svg)
- [Python](https://www.python.org/)
- [Beautiful Soup 4](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
- [Requests Cache](https://requests-cache.readthedocs.io/en/stable/)
- [Pretty Table](https://pypi.org/project/prettytable/)
- [tqdm](https://tqdm.github.io/)


## Подробное описание проекта
Всего в парсере реализовано 4 функици:
- whats_new - Парсит страницу https://docs.python.org/3/whatsnew/ и 
  рекурсивно переходит на страницы версий Python и ищет там нужную информацию.
- latest_versions - парсит страницы версий Python, рисует версию и статус 
  конкретной версии.
- download - Скачивает документацию на последнюю версию Python
- pep - Парсит Пепы на https://peps.python.org/ , рекурсивно открывает 
  страницы, сверяет статус Пепов на страницы листинга и страницах самих 
  Пепов, считает их количество и выводит в удобном виде.
  
Для каждой фукнции сделан вывод в консоль построчно, вывод в консоль в виде 
таблицы, вывод в csv-файл. Так же реализованы аргументы командной строки, 
работает справка.
Справка запускается с ключом -h или --help

## Аргументы
1. mode (Режим работы парсера) - позиционный аргумент, возможные варианты: 
   whats-new, latest-versions, download, pep.
2. '-c' ('--clear-cache) - именной аргумент очистки кеша, если его вызвать, то 
   данные повторно будут скачаны с сайта и размещены в БД sqlite
3. '-o' ('--output') - именной аргумент способа вывода данных. Принимает 
   параметры 'pretty', 'file'. Выводит данные в виде таблицы / в файл 
   соответственно. Без параметров выводит в консоль без оформления
   
## Разворачивание проекта локально (Windows)
1. Скопировать себе гит (git clone)
2. Установить виртуальное окружение
3. Установить зависимости
```
pip install -r requirements.txt
```
4. Перейти в каталог ./src
5. Запускать командой ```python main.py <аргументы>```

## Автор
dvkonstantinov
telegram: https://t.me/Dvkonstantinov

