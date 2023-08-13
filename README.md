Предназначен для ввода общей информации о проекте. 

![image](https://github.com/klebedev07/doc/assets/88347147/e265dd26-69c1-47b9-99d0-b247384ee3e9)

Содержит следующие модули:
- Заголовок - содержит общую информацию о проекте. 
- Список продуктов - здесь описывается полный перечень услуг и/или выпускаемой продукции с указанием единиц измерения и даты начала продаж
- Текстовое описание - там какое то дерево, не понятно пока зачем оно и нужно ли. И будет ли в дальнейшем как то использовать в логике. Можем пропустить.
- Отображение данных - тут настройки которые будут использоваться при построение графиков в дальнейшем. Масштаб на графиках (по месяцам, по кварталам и т.д) , количество знаков после запятой, валюта
- Настройка расчетов - тут задается ставка дисконтирования, задается список таблиц  и расчетов которые попадут в итоговый документ. Так же ест раздел показатели эффективности. Тут что то про кредиты и проценты от прибыли которые можно пустить на погашения, если я правильно понял. Нужно более глубоко аналитить.
- Защита проекта - тут просто защита паролем и выдача прав. Нам это не нужно

Начинаем с создания Общей инофрмации о проекте. Реализуем разделы:
- Заголовок
- Список Продуктов
- Отображение данных
- Настройка расчета

## Front: 
1. Форма создания  нового проекта. Название проекта, автор, дата начала, длительность в годах и месяцах, краткое описание. ![image](https://github.com/klebedev07/doc/assets/88347147/2532e82b-88ae-43e0-b32b-9f67040d4180)

2. После создания видим проект и разделы описанные выше.
    - Щелкаем на заголовок видим общую информацию. Такую же как в пункте 1. Можно редактировать
    - Щелкаем на список продуктов видим перечень продуктов и услуг. Наименование, единица измерения, дата начала продаж. Есть возможность добавлять и удалять их ![image](https://github.com/klebedev07/doc/assets/88347147/6685de7e-8acd-4c57-afc6-c740d95f7cc5)

    - Щелкаем на отображение данных открываются настройки проекта, в котороых мы можем указать масштаб данных, количество знаков после запятой и валюту. Не делаем как в оригинале в разных вкладках, все на одной странице ![image](https://github.com/klebedev07/doc/assets/88347147/43e04231-8d01-4f63-9c1e-bc1a53dc2111)

- Настройку расчета обсудим вместе.

## Бэкенд

Заводим эндпоинты под функциональность сверху.
Предлагаю таблицу project с двумя полями

| id   | data |
|------ |------|
|  UUID | JSONB|

Вся инофрмация по проекту будет хранится в виде json в поле дата.
Продукты и услуги можно выделить в отдельные таблицы, но по тому же принципу. Всё в json
