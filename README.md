# «Базы данных» Акиньшин С.Г.

### Взял за основу PostgreSQL.

## Задание 1

### Отношение "сотрудники":

id - (serial, primary key)
ФИО - (varchar(50), not null, UNIQUE)
Оклад - (numerinc, not null)
Дата найма - (not null, DATE)
id_должности - (smallint, not null, ссылается на атрибут "id" отношения "должности")
id_адрес_филиала - (smallint, not null, ссылается на атрибут "id" отношения "адрес_филиалы")

### Отношение " должности":

id - (serial, primary key)
Наименование - (varchar(50), not null)

### Отношение "тип_подразделения":

id - (serial, primary key)
Наименование - (varchar(20), not null)

### Отношение "структурное_подразделение":

id - (serial, primary key)
Наименование - (varchar (100), not null)

### Отношение "cотрудники_тип_подразделения_cтруктурное_подразделение":

id_сотрудника - (smallint, not null, FOREIGN KEY) ссылается на арибут "id" отношения "сотрудники"
id_тип подразделения (smallint, not null, FOREIGN KEY) ссылается на атрибут "id" отношения "тип подразделения"
id_структурного подразделения - (smallint, not null, ссылается на атрибут "id" отношения "структурное подразделение")

### Отношение "адрес_филиала"

id - (serial, primary key)
Адрес - (varchar(200), not null)

### Отношение "проект"

id - (serial, primary key)
Наименование - (varchar(100), not null)

### Отношение "cотрудник_проект" - может быть многие ко многим

id_сотрудника - (smallint, not null, FOREIGN KEY) ссылается на атрибут "id" отношения "сотрудники",
id_проекта (smallint, not null, FOREIGN KEY) ссылается на атрибут "id" отношения "проект".