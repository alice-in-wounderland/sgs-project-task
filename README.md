[Employee_Shifts MS SQL.txt](https://github.com/alice-in-wounderland/sgs-project-task/files/13038419/Employee_Shifts.MS.SQL.txt)# sgs-project-task
## Форма на vue.js

![изображение](https://github.com/alice-in-wounderland/sgs-project-task/assets/47723267/5f5d38a3-b371-447f-bd87-43d3bb0accbe)
![изображение](https://github.com/alice-in-wounderland/sgs-project-task/assets/47723267/7e10f6b5-2539-4767-9f11-b3c7b2b29b18)

Поле "Цех" зависит от поля "Город":
![изображение](https://github.com/alice-in-wounderland/sgs-project-task/assets/47723267/9aeeed98-d7ea-4121-b407-a187d8e25f0f)

Поле "Сотрудник" зависит от поля "Цех":
![изображение](https://github.com/alice-in-wounderland/sgs-project-task/assets/47723267/727b38a2-a4cd-4160-95a6-ace3bb28e1f7)
![изображение](https://github.com/alice-in-wounderland/sgs-project-task/assets/47723267/84b5825d-d74a-4077-8d5d-0199fa36bc71)

При обновлении поля "Город" значения полей "Цех" и "Сотрудник" обнуляются.

## Скрипт по созданию таблицы на MS SQL: 

[Employee_Shifts MS SQL.txt](https://github.com/alice-in-wounderland/sgs-project-task/files/13038425/Employee_Shifts.MS.SQL.txt)

Вынесла в отдельную таблицу сотрудников для приведения к нормальной форме. Таблицы связываются по id сотрудника.
