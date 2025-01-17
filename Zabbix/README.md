# Домашнее задание к занятию «Система мониторинга Zabbix» - `Ушкевич Всеволод`


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

![img1](12/1q.png)
Текст использованных команд:
1. apt install postgresql
2. apt update
3. wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu22.04_all.deb
4. dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
5. apt update
6. apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts
7. sudo -u postgres createuser --pwprompt zabbix
8. sudo -u postgres createdb -O zabbix zabbix
9. zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
10. sed -i 's/# DBPassword=/DBPassword=123456789/g' /etc/zabbix/zabbix_server.conf
11. systemctl restart zabbix-server zabbix-agent apache2
12. systemctl enable zabbix-server zabbix-agent apache2


### Задание 2

![img2](12/2q.png)
![img3](12/3q.png)
![img4](12/4q.png)
Текст использованных команд:
1. wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu22.04_all.deb
2. dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
3. apt update
4. apt install zabbix-agent
5. systemctl restart zabbix-agent
6. systemctl enable zabbix-agent
7. find / -name zabbix_agentd.conf
8. nano /etc/zabbix/zabbix_agentd.conf
9. tail -f /var/log/zabbix/zabbix_agentd.log
10. systemctl restart zabbix-agent.service
11. systemctl status zabbix-agent.service


