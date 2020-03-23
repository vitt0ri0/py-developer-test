# Тест для разработчика


Нужно скачать этот файл, заполнить соответствующие поля и прислать модифицированный md-файл по почте.


### 1. Напишите, какие бывают типы http запросов (Request methods)? 

~~~
# Напишите тут типы запросов.
из тех что часто приходилось использовать мне: 
GET, POST, PATCH, DELETE. 
из экзотики: 
OPTIONS, PUT, HEAD etc.

~~~


Нужно заполнить таблицу действий над ресурсами согласно REST-подходу.

*Поставьте «галочки» в нужных ячейках*.

|      | A                                  | /books | /books/17 |
| ---- | ---------------------------------- | ------ | --------- |
| 1    | Получить коллекцию                 |        |     +      |
| 2    | Создать новую запись о книге       |   +     |           |
| 3    | Изменить отдельную запись о книге  |        |    +       |
| 4    | Удалить всю коллекцию книг         |   +     |           |
| 5    | Удалить отдельную запись о книге   |        |    +       |
| 6    | Получить запись об отдельной книге |        |    +       |



### 2. Разница между процессом и потоком

*Поставьте «галочки» в нужных ячейках*.

|      | Свойство                                                   | Процессы | Потоки |
| ---- | ---------------------------------------------------------- | -------- | ------ |
| 1    | Взаимодействуют только через механизмы, предоставляемые ОС |    +      |        |
| 2    | Делят между собой память                                   |          |   +     |
| 3    | Владеют ресурсами                                          |   +       |        |
| 4    | Хранят больше информации о состоянии                       |          |   +     |
| 5    | "Легче" происходит переключение контекста                  |          |   +     |
| 6    | Имеют отдельное адресное пространство                      |   +       |        |
| 7    | Могут создавать объекты такого же типа                     |   +       |        |
| 8    | Могут владеть объектами того же типа                       |          |    +    |



### 3. Медиана трех чисел

Нужно написать функцию, которая возвращает среднее по значению число из трех чисел.

Для [5, 1, 2] результат будет 2.

~~~python
# можно писать длинные неравенства: 
def median3(a, b, c):
    if a <= b <= c or c <= b <= a:
        return b
    elif b <= a <= c or c <= a <= b:
        return a
    else:
        return c

# Либо же отсортировать массив и вернуть серединный элемент. По сложности едва ли будет заметная разница. 
def median3(a, b, c):
    arr = [a, b, c]
    return sorted(arr)[1]
~~~

### 4. Что делают "магические методы" в python


|      | Метод        | Короткое описание своими словами |
| ---- | ------------ | -------------------------------- |
| 1    | ```__call__```     | вызывается когда экземпляр класса вызван как функция     |
| 2    | ```__str__```      | строковое представление объекта. МОжет быть актуально в консоли или в дебаге (печатать только пару свойств класса, а не все 100500)     | 
| 3    | ```__repr__```     | еще одно строковое представление объекта. Считается "официальным" в отличии от __str__(). Дока предлагает его представлять в реплицируемом виде; чтобы по нему можно было воссоздать объект.      |
| 4    | ```__truediv__```  |  переопредление деления (a/b).     |
| 5    | ```__ipow__```     |   переопределние возведения в степень a **= b   |
| 6    | ```__hex__```      |   конвертация int'a в hex. Вызывается при вызове функции hex()   |
| 7    | ```__len__```      |   определение длины объекта при вызове функции len(). возвращает int >= 0.    |
| 8    | ```__contains__``` |   определение оператора in: a in b .   | 



### 5. В чем разница между copy и deepcopy

~~~
Впишите ответ тут
Разница будет только для составных объектов. 
- Copy копирует объект и затем в поля этого объекта вставляет ссылки из копируемого объекта. 
- Deepcopy же убедится, что в полях объекта будут копии объектов. То есть, каждый вложенный объект тоже будет копией. Тогда можно многократно вложенные объекты копировать безопасно. 
~~~


### 6. Заполните таблицу сложности алгоритмов

*Поставьте «галочки» в нужных ячейках*.

предполагаю что ln N значит log N 


|      | A                                                  | O(1) | O(ln(N)) | O(N) | O(N*ln(N)) | O(N^2) | Другой вариант |
| ---- | -------------------------------------------------- | ---- | -------- | ---- | ---------- | ------ | ------------ |
| 1    | Вставка в красно-черное дерево                     |      |   +       |      |            |        |              |
| 2    | Быстрая сортировка в среднем                       |      |          |      |     +       |        |              |
| 3    | Вставка в хеш-таблицу                              |   +   |          |      |            |        |              |
| 4    | Поиск в связном списке                             |      |          |   +   |            |        |              |
| 5    | Двоичный поиск в отсортированном массиве           |      |  +        |      |            |        |              |
| 6    | Обход красно-черного дерева от большего к меньшему |      |          |  +    |            |        |              |
| 7    | Вставка в хеш-таблицу в случае коллизии            |      |          |  O(M), где M - длина листа в коллизии   |            |        |            |
| 8    | "Пузырьковая" сортировка                           |      |          |      |            |    +    |              |
| 9    | Удаление из массива (со сдвигом)                   |      |          |  +    |            |        |              |
| 10   | Поиск в хеш-таблице                                |  +    |          |      |            |        |              |


### 7. Нужно отметить несколько верных утверждений о различных БД

*Поставьте «галочки» в нужных ячейках*.

|      | A                                                            | MongoDB | MySQL | Postgres |
| ---- | ------------------------------------------------------------ | ------- | ----- | -------- |
| 1    | Хранит документы                                             |    +     |       |          |
| 2    | Хранит строки данных                                         |         |   +    |   +       |
| 3    | Гарантирует атомарность изменения нескольких коллекций/таблиц |         |  +/-     |   +       |
| 4    | Позволяет эффективно сделать запрос к полю JSON              |   +      |       |          |
| 5    | Требует описания "схемы" данных, таблицы                     |         |   +    |   +       |
| 6    | Гарантирует атомарность на уровне документа/строки           |         |   +    |   +       |
| 7    | Удовлетворяет критериям ACID                                 |         |       |   +       |
| 8    | Поддерживает репликацию на несколько машин                   |    +     |  +     |   +       |


### 8. Что может происходить в браузере, когда пользователь вводит адрес (https://ya.ru) в адресной строке и нажимает Enter?

*Поставьте «галочки» в нужных ячейках*.

|      | A                                     |      |
| ---- | ------------------------------------- | ---- |
| 1    | Сжатие исходных JS кода               |  +    |
| 2    | Проверка сертификатов                 |  +    |
| 3    | Парсинг HTML                          |  +    |
| 4    | Запуск PHP скриптов сайта             |  +    |
| 5    | Исполнение Javascript                 |  +    |
| 6    | Парсинг CSS                           |  +    |
| 7    | Загрузка данных html страницы по HTTP |  +    |
| 8    | Деобфускация JS кода                  |      |
| 9    | TLS handshake                         |  +    |
| 10   | DNS запрос по UDP                     |  +    |
| 11   | Построение DOM-дерева                 |  +    |


### 9. В чем различие между протоколами TCP и UDP?

*Поставьте «галочки» в нужных ячейках*.

|      | A                                                    | TCP  | UDP  |
| ---- | ---------------------------------------------------- | ---- | ---- |
| 1    | Гарантирует доставку данных                          | +     |      |
| 2    | Лучше подходит для задач условно "реального времени" |      |   +   |
| 3    | Требует установки соединения                         |  +    |      |
| 4    | Обеспечивает более высокую скорость передачи данных  |      |   +   |
| 5    | Работает внутри IP сетей                             |  +    |  +    |
| 6    | Гарантирует последовательность доставки              |  +    |      |


### 10. Задача "выколотый массив"

```arr``` - массив чисел от 1 до N, в котором одно число выкинули, а остальной массив перемешали. Требуется написать функцию, которая принимает на вход массив ```arr``` и возвращает удаленное число. Решение должно быть линейным, не должно модифицировать исходный массив и использовать дополнительную память.


```python
# Сигнатура на python
# предполагаем что N принадлежит [1, N); N не включается в множество.  
def find_missing(arr):
    full_sum = sum(range(1, N))
    my_sum = sum(arr)

    return full_sum - my_sum
    
```

