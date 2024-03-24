# Тестирование Django-приложения

## Описание

Есть бэкенд простого приложения с курсами и списком студентов. Вся логика для бэкенда уже есть в заготовке, но совершенно нет тестов.

## Реализация

Реализованы тесты для текущей логики приложения. Добавлены следующие тест-кейсы:

- проверка получения первого курса (retrieve-логика):
  - создаем курс через фабрику;
  - строим урл и делаем запрос через тестовый клиент;
  - проверяем, что вернулся именно тот курс, который запрашивали;
- проверка получения списка курсов (list-логика):
  - аналогично — сначала вызываем фабрики, затем делаем запрос и проверяем результат;
- проверка фильтрации списка курсов по `id`:
  - создаем курсы через фабрику, передать ID одного курса в фильтр, проверить результат запроса с фильтром;
- проверка фильтрации списка курсов по `name`;
- тест успешного создания курса:
  - готовим JSON-данные и создаём курс;
- тест успешного обновления курса:
  - сначала через фабрику создаём, потом обновляем JSON-данными;
- тест успешного удаления курса.


### Ограничение числа студентов на курсе

Добавлена валидация на максимальное число студентов на курсе — 20. Реализован тест для проверки этого ограничения, не создавая 20 сущностей в базе данных.

## Документация по проекту

Для запуска проекта необходимо

Установить зависимости:

```bash
pip install -r requirements-dev.txt
```

Выполнить команду:

```bash
pytest
```

Проверить процент покрытия кода тестами:
```bash
pytest --cov=.
```

Сами тесты находятся в фале [test_courses_api.py](tests/students/test_courses_api.py)

## Задачу выполнила
Евгения Псарева `epsareva77@gmail.com`
