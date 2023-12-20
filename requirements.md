# inoske-backend
## Требования к функционалу
### Технологии
* Поддерживая версия Java, не меньше 17 
* Обсечена работа с базой данных ClickHouse  
  * Наличие драйвера необходимого для подключения к ClickHouse
* Api работает с протоколом HTTP/1.2

### Функции
* Api для вывода метрик c возможностью фильтрации по полям:
  * Диапазон даты (дата начала и дата конца)
    * Если указана только дата начала, датой конца будет считаться сегодняшний день
    * Если указана только дата конца, то датой начала будет считаться сегодняшний день
  * Название магазинов с возможностью ввода нескольких названий через запятую
  * При запросе без фильтров выводить все записи за текущий день
* Генератор фейковых данных метрик:
  * API для генерации данных 
  * Возможность указания количества сгенерированных данных в базе
  * Для каждой записи должны генерироваться следующие поля:
    * Название магазина (Должно браться из списка существующих)
    * Количество добавленных продуктов за день
    * Количество обновленных категорий за день
    * Количество посещений за день
    * Количество покупок за день
    * Количество регистраций за день
    * Дата сбора метрики
* API для сохранения метрик
  * Должен принимать на вход список метрик и сохранять данные в ClickHouse