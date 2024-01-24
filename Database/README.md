# Домашнее задание к занятию «База данных» - `Ушкевич Всеволод`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.

Желаем успехов в выполнении домашнего задания!

### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

1. Таблица "Сотрудники":

- id (идентификатор, первичный ключ, serial)
- Фамилия (varchar(50))
- Имя (varchar(50))
- Отчество (varchar(50))
- id Должности (внешний ключ, integer, REFERENCES Должности(id))
- id Структурного подразделения (внешний ключ, integer, REFERENCES Структурные подразделения(id))
- Дата найма (date)
- id Зарплаты (внешний ключ, integer, REFERENCES Зарплаты(id))

2. Таблица "Структурные подразделения":

- id (идентификатор, первичный ключ, serial)
- id Тип подразделения (внешний ключ, integer, REFERENCES Тип подразделения(id))
- id Филиалы (внешний ключ, integer, REFERENCES Филиалы(id))
- Структурное подразделение (varchar(100))

3. Таблица "Филиалы":

- id (идентификатор, первичный ключ, serial)
- Адрес филиала (varchar(100))

4. Таблица "Проекты":

- id (идентификатор, первичный ключ, serial)
- Название проекта (varchar(100))

5. Таблица "Назначения проектов":

- id Сотрудника (внешний ключ, integer, REFERENCES Сотрудники(id))
- id Проекта (внешний ключ, integer, REFERENCES Проекты(id))

6. Таблица "Должности":

- id (идентификатор, первичный ключ, serial)
- Название должности (varchar(50))

7. Таблица "Зарплаты":

- id (идентификатор, первичный ключ, serial)
- Сумма (numeric(10, 2))

8. "Тип подразделения":

- id (идентификатор, первичный ключ, serial)
- Тип подразделения (varchar(50))