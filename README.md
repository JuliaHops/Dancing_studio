# Проектирование базы данных Танцевальной студии

## Предметная область
Танцевальная студия  
Создаётся база данных для автоматизации работы студии:  
- учёт сотрудников, учеников, инвентаря;  
- расписание занятий и мероприятий;  
- организация соревнований и выступлений.  

---

## 1. Моделирование


### 1.1 Модель IDEF0
Основной процесс — «Работа танцевальной студии».  

<img width="1004" height="527" alt="image" src="https://github.com/user-attachments/assets/a3a29041-a0cf-4e14-a47d-960b6782378e" />

Входные данные:
- ФИО, телефон, возраст учеников  
- списки сотрудников, залов, инвентаря, видов танцев  
- информация о соревнованиях и посещаемости
- и т.д.

Выходные данные:
- расписания  
- отчёты о мероприятиях  
- списки сотрудников и учеников  
- информация об отменах
- и т.д.
- 
Управляющей информацией системы являются:
- время
- правила танцевальной студии
- свободные залы

Механизмами системы являются:
- АО
- ПО
- сотрудники на регистрации
- и т.д.

Декомпозируем общий блок «Танцевальная студия» на связанные между собой элементы. Получим 3 основных этапа .
1.	Учет.
2.	Расписание.
3.	Мероприятия.

<img width="849" height="438" alt="image" src="https://github.com/user-attachments/assets/6c75a1bc-e495-4430-8a43-de70d6f546a3" />

Блок «Учет» декомпозируем ещё на 3 этапа.
1.	Учет сотрудников.
2.	Учет инвентаря.
3.	Учет учеников.

<img width="837" height="448" alt="image" src="https://github.com/user-attachments/assets/fa176a45-1768-4776-b414-388ba5b3a4f6" />

Блок «Расписание» декомпозируем на 3 этапа.
1.	Учет занятости залов.
2.	Учет разных видов.
3.	Учет посещаемости.

<img width="846" height="454" alt="image" src="https://github.com/user-attachments/assets/8a1b39e0-8eab-48c8-ae66-4761d48bacaf" />

Блок «Мероприятия» декомпозируем на 4 этапа.
1.	Организация соревнований.
2.	Организация показательных выступлений.
3.	Выездные соревнования.

<img width="814" height="432" alt="image" src="https://github.com/user-attachments/assets/582f7142-a0bd-42e8-85d8-66411557f0f5" />

---

### 1.2 Модель DFD
Внешние сущности: клиент, сотрудник, организаторы, руководство.  

Стрелки (потоки данных) описывают движение объектов из одной части системы в другую.

Основные хранилища:
- ученики  
- сотрудники  
- залы  
- инвентарь  
- виды танцев  
- соревнования  
- мероприятия  

Диаграммы показывают движение информации между подсистемами учёта, расписания и мероприятий. 


Контекстная диаграмма «Танцевальная студия» в нотации DFD

<img width="884" height="410" alt="image" src="https://github.com/user-attachments/assets/77ee9975-a7f6-4a8c-b901-ff4584b229ef" />

Декомпозиция контекстной диаграммы «Танцевальная студия» в методологии DFD

<img width="785" height="441" alt="image" src="https://github.com/user-attachments/assets/8dbcfa4f-e2cb-4fa9-bac2-8c3fa603046a" />

Декомпозиция блока «Учет» в методологии DFD

<img width="937" height="522" alt="image" src="https://github.com/user-attachments/assets/4a6efd6f-ca44-4427-8c4b-57c6bcb117ad" />

Декомпозиция блока «Расписание» в методологии DFD

<img width="867" height="474" alt="image" src="https://github.com/user-attachments/assets/62dfbc10-fe81-4792-a42e-6ff2ac37377a" />

Декомпозиция блока «Мероприятия» в методологии DFD

<img width="873" height="475" alt="image" src="https://github.com/user-attachments/assets/e4720b35-e594-4279-9e61-8b468c6c16b6" />


---

### 1.3 UML-диаграммы
- Use Case — акторы: клиенты, сотрудники, руководство; сценарии: просмотр расписания, регистрация, организация мероприятий.

  <img width="1062" height="505" alt="image" src="https://github.com/user-attachments/assets/1f36bb1f-b29b-47b3-8908-4accfef027bc" />

- Диаграмма классов — классы: клиент, сотрудник, зал, инвентарь, мероприятие, а также управляющие и граничные классы.  

<img width="344" height="506" alt="image" src="https://github.com/user-attachments/assets/a629a999-ee7e-4542-88ba-1ef0d1024801" />

- Диаграмма классов анализа — абстрактные классы: сущности, граничные, управляющие.

<img width="745" height="185" alt="image" src="https://github.com/user-attachments/assets/214a7b62-376d-4c4e-884b-c71970de4717" />

- Диаграмма последовательности — шаги взаимодействия объектов при просмотре расписания.

<img width="825" height="337" alt="image" src="https://github.com/user-attachments/assets/d331e7de-57f7-4233-91a9-6005217cade7" />

- Диаграмма кооперации — обмен сообщениями между объектами.

<img width="844" height="304" alt="image" src="https://github.com/user-attachments/assets/9afa1af6-0bfd-40e0-b6a0-7a1cdc0b5cc3" />


---

### 1.4 ER-диаграмма
Сущности: Клиент, Сотрудник, Зал, Инвентарь, Мероприятие, Соревнование, Вид танца.  


<img width="977" height="445" alt="image" src="https://github.com/user-attachments/assets/048cec6a-fbc9-48be-b2c2-20a10c6be74f" />

---

### 1.5 Логическая и физическая модель
Структура таблиц и их взаимосвязи на уровне СУБД.  

Логическая модель
<img width="848" height="572" alt="image" src="https://github.com/user-attachments/assets/65c18327-fee3-4a19-91a8-e6605b405dc2" />

Физическая модель
<img width="861" height="511" alt="image" src="https://github.com/user-attachments/assets/84385d1b-5ec3-4168-91d0-1bbe3dabc66e" />

---


## 2. Реализация в MySQL

### 2.1. Логическая модель
Для реализации в MySQL построена упрощенная ER-диаграмма. 

<img width="774" height="500" alt="image" src="https://github.com/user-attachments/assets/3fccb77a-53f3-469b-8e49-c865bf737e3d" />


### 2.2. Физическая модель

Сущности:  
- Personality (ФИО, телефон, возраст)  
- Client (карта, связь с личностью)  
- Employee (должность, связь с личностью)  
- Post (справочник должностей)  
- Inventory (инвентарь)  
- Hall (залы, связь с инвентарём)  
- Type_of_dance (виды танцев)  
- Timetable (расписание: дата, зал, тип танца)  
- Связующие таблицы: Client_has_Timetable, Employee_has_Timetable

<img width="778" height="476" alt="image" src="https://github.com/user-attachments/assets/befcb313-4a4f-4755-9a6a-cf6b5f6e27aa" />

  
Все сущности реализованы в MySQL, добавлены ключи PK и FK, ограничения NOT NULL, UNIQUE, связи многие-ко-многим разделены через промежуточные таблицы.

Название сущности	Название атрибута	Тип данных	Особое состояние	Ключ
Timetable	Id_Timetable	int	Auto_increment	PK
	Date	datetime	Not null	-
	id_Type_of_dance	inr	Not null	FK
	Id_Hall	inr	Not null	FK
Type_of_dance	If_Type_of_dance	int	Auto_increment	PK
	Type_of_dancecol	varchar	Not null	-
Personality	Id_ Personality	int	Auto_increment	PK
	Second_name	varchar	Not null	-
	Name	varchar	Not null	-
	Surname	varchar	-	-
	Phone	varchar	Not null	-
	Age	inr	Not null	
Client_has_Timetable	id_Client	int	Not null	PK, FK
	Id_Timetable	int	Not null	PK, FK
Client	id_Client	int	Auto_increment	PK
	Id_Personality	int	Not null	FK
	Card	varchar		
Post	Id_Post	inr	Auto_increment	PK
	Postcol	varchar	Not null	-
Employee	id_Client	int	Auto_increment	PK
	Id_Personality	int	Not null	FK
	Id_Post	int	Not null	FK
Employee_has_Timetable	id_Employee	int	Not null	PK, FK
	Id_Timetable	int	Not null	PK, FK
Inventory	Id_Inventory	inr	Auto_increment	PK
	Name_inventory	varchar	Not null	-
Hall	Id_Hall	inr	Auto_increment	PK
	Number_hall	varchar	Not null	-
	Id_Inventory	int	Not null	FK


### 2.3. Заполнение БД
- Таблицы заполнены начальными данными (INSERT INTO).  
- Проверка структуры — DESCRIBE, SHOW TABLES.  

### 2.4. Запросы
- SELECT + WHERE — фильтрация по условиям.  
- ORDER BY — сортировка.  
- NULL / NOT NULL — проверка пустых значений.  
- BETWEEN / IN / LIKE — поиск по диапазонам и шаблонам.  
- ALTER TABLE — изменения в структуре.  
- JOIN — соединение таблиц.  
- GROUP BY / HAVING — группировка, агрегаты (COUNT, SUM, AVG, MIN, MAX).  
- Теоретико-множественные операции: объединение, пересечение, разность, деление.  

### 2.5. Хранимые процедуры, функции и триггеры
- Функции: возраст клиента по ID, количество посещений за неделю, поиск зала по типу танца и дате.  
- Процедуры: добавление сотрудника, обновление карты клиента, удаление человека по ID.  
- Триггеры:  
  - замена инвентаря при удалении;  
  - запрет добавления клиентов младше 18 лет;  
  - контроль изменения возраста.  

### 2.6. Оконные функции
- Агрегаты по окнам: AVG, SUM, COUNT, MIN, MAX.  
- PARTITION BY, ORDER BY — группировка и сортировка внутри окон.  
- Ранжирование: ROW_NUMBER, RANK, DENSE_RANK, NTILE.  
- Доступ к соседним строкам: LAG, LEAD.  
- Выбор крайних значений: FIRST_VALUE, LAST_VALUE.  


---

## Заключение
В рамках работы:  
- спроектирована БД (IDEF0, DFD, UML, ER, реляционная алгебра);  
- разработана и реализована БД в MySQL;  
- заполнена данными и протестирована;  
- выполнены запросы, агрегаты, оконные функции;  
- созданы хранимые процедуры, функции и триггеры.  

База данных охватывает все основные процессы танцевальной студии: учёт людей, залов и инвентаря, расписание занятий и организацию мероприятий.
