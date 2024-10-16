## Part 1. Установка ОС

- ``Смотрим версию Ubuntu после установки ``<br>
![Alt text](src/1.png "Optional Title")<br>


---

## Part 2. Создание пользователя
- ``Создаём пользователя и назначаем ему группу adm``<br>
![Alt text](src/2.png "Optional Title")<br>


- ``Вывод списка пользователей (новый юзер в конце списка)``<br>
![Alt text](src/2.1.png "Optional Title")<br>


---

## Part 3. Настройка сети ОС

- ``Установили новое имя машины и вывели его в терминал``<br>
![Alt text](src/3.png "Optional Title")<br>

- ``Установили новую временную зону и вывели информацию в терминал``<br>
![Alt text](src/3.1.png "Optional Title")<br>

- ``Установили набор сетевых инструментов``<br>
![Alt text](src/3.2.png "Optional Title")<br>
``Вывели информацию о сетевых интерфейсах``<br>
![Alt text](src/3.3.png "Optional Title")<br>
**lo (loopback device)** – виртуальный интерфейс, присутствующий по умолчанию в любом Linux. Он используется для отладки сетевых программ и запуска серверных приложений на локальной машине. С этим интерфейсом всегда связан адрес 127.0.0.1. У него естьLinux komandalariLinux komandalariLinux komandalariLinux komandalariLinux komandalariLinux komandalariLinux komandalariLinux komandalari dns-имя – localhost.

- ``Удалили старый и получили новый ip от dhcp сервера``<br>
![Alt text](src/3.4.png "Optional Title")<br>
**DHCP - Dynamic Host Configuration Protocol**

- ``Узнали внешний IP-адрес``<br>
![Alt text](src/3.5.png "Optional Title")<br>

- ``Узнали внутренний IP-адрес шлюза, он же ip-адрес по умолчанию``<br>
![Alt text](src/3.6.png "Optional Title")<br>

- ``Изменили файл /etc/netplan/*.yaml, применили изменения в netplan, перезагрузились``<br>
![Alt text](src/3.7.png "Optional Title")<br>
![Alt text](src/3.8.png "Optional Title")<br>
- ``Проверяем, что адреса соотсветствуют заданным в предыдущем пункте``<br>
![Alt text](src/3.9.png "Optional Title")<br>
- ``Успешно пропинговали удаленные хосты 1.1.1.1 и ya.ru``<br>
![Alt text](src/3.10.png "Optional Title")<br>

---

## Part 4. Обновление ОС
- ``Успешно обновили системыне пакеты``<br>
![Alt text](src/4.png "Optional Title")<br>

---

## Part 5. Использование команды sudo
- **sudo** - позволяет временно поднимать привилегии и выполнять задачи администрирования системы с максимальными правами<br>
``Добавили пользователя в группу с привилегиями sudo, переключились на этого пользователя и поменяли hostname``<br>
![Alt text](src/5.png "Optional Title")<br>

---

## Part 6. Установка и настройка службы времени
- ``Вывод команды с корректным временем``<br>
![Alt text](src/6.png "Optional Title")<br>

---

## Part 7. Установка и использование текстовых редакторов
- ``**VIM** Для сохранения и выхода нажал ESC и прописал :wq и имя документа``<br>
![Alt text](src/7.png "Optional Title")<br>
- ``**NANO** Для сохранения нажал ^O, ввёл имя файла и подтвердил. Вышел через ^X``<br>
![Alt text](src/7.1.png "Optional Title")<br>
- ``**JOE** Для сохранения и выхода нажал ^KX, ввёл имя файла и подтвердил.``<br>
![Alt text](src/7.2.png "Optional Title")<br>

- ``**VIM** Для выхода без сохранения ESC -> :q! -> ENTER``<br>
![Alt text](src/7.3.png "Optional Title")<br>
- ``**NANO** Для выхода без сохранения ^X -> N``<br>
![Alt text](src/7.4.png "Optional Title")<br>
- ``**JOE** Для выхода без сохранения ^C -> y``<br>
![Alt text](src/7.5.png "Optional Title")<br>
- ``**VIM** Для поиска: /что_ищем``<br>
![Alt text](src/7.6.png "Optional Title")<br>
- ``**VIM** Для замены: :s/что_заменить/чем``<br>
![Alt text](src/7.7.png "Optional Title")<br>
- ``**NANO** Для поиска: ^W -> что ищем``<br>
![Alt text](src/7.8.png "Optional Title")<br>
- ``**NANO** Для замены: ^\ -> что заменить -> чем -> Y``<br>
![Alt text](src/7.9.png "Optional Title")<br>
- ``**JOE** Для поиска: ^K F -> что ищем -> I``<br>
![Alt text](src/7.10.png "Optional Title")<br>
- ``**JOE** Для замены: ^K F -> что заменить -> R -> чем -> Y``<br>
![Alt text](src/7.11.png "Optional Title")<br>

---

## Part 8. Установка и базовая настройка сервиса SSHD
- ``Установил openssh-server и настроил конфиг``<br>
- ``Выполнил sudo systemctl start sshd``<br>
- ``Выполнил sudo systemctl enable sshd``<br>
- ``Отобразил наличие процесса``<br>
**ps** - выводит сведения о процессах в статическом виде<br>
**-e** - позволяет выбрать все процессы<br>
**| grep sshd** - поиск по выводу через пайп<br>
![Alt text](src/8.png "Optional Title")<br>
- ``reboot``<br>
- ``netstat -tan``<br>
![Alt text](src/8.1.png "Optional Title")<br>
**-tan**: <br>
-a -	Показывать состояние всех сокетов; обычно сокеты, используемые серверными процессами, не показываются.<br>
-n - Показывать сетевые адреса как числа. netstat обычно показывает адреса как символы.<br>
-t - Отображать TCP подключения<br>
**Proto** - Содержит тип протокола<br>
**Recv-Q** - Счётчик байтов не скопированных программой пользователя из этого сокета.<br>
**Send-Q** - Счётчик байтов, не подтверждённых удалённым узлом.<br>
**Local Address** - Адрес и номер порта локального конца сокета.<br>
**Foreign Address** - Адрес и номер порта удалённого конца сокета.<br>
**State** - Состояние сокета.<br> 
LISTEN Сокет ожидает входящих подключений.<br> 
SYN_SENT Сокет, находящийся в режиме активной попытки установки подключения.<br>
0.0.0.0 -  это немаршрутизируемый адрес IPv4, который используется в качестве адреса по умолчанию или адреса-заполнителя.

---

## Part 9. Установка и использование утилит top, htop
- Uptime: 9 min<br>
- 1 user<br>
- Load average: 0.00, 0.01, 0.00<br>
- Tasks: 125 total<br>
- %Cpu(s): 0.1 us, 0.0 sy, 0.0 ni, 99.9 id, 0.0 wa, 0.0 hi, 0.0 si, 0.0 st<br>
- MiB Mem: 7957.3 total, 7099.0 free, 230.4 used, 627.9 buff/cache<br>
- PID 1411<br>
- PID 1411<br>

- ``htop сортировка по PID``<br>
![Alt text](src/9.png "Optional Title")<br>
- ``htop сортировка по PERCENT_CPU``<br>
![Alt text](src/9.1.png "Optional Title")<br>
- ``htop сортировка по PERCENT_MEM``<br>
![Alt text](src/9.2.png "Optional Title")<br>
- ``htop сортировка по TIME``<br>
![Alt text](src/9.3.png "Optional Title")<br>
- ``htop фильтр по процессу sshd``<br>
![Alt text](src/9.4.png "Optional Title")<br>
- ``htop поиск процесса syslog``<br>
![Alt text](src/9.5.png "Optional Title")<br>
- ``htop с добавленным выводом hostname, clock и uptime``<br>
![Alt text](src/9.6.png "Optional Title")<br>

---

## Part 10. Использование утилиты fdisk
- Disk /dev/sda, size: 25 GiB, 26843545600 bytes, 52428800 sectors<br>
![Alt text](src/10.png "Optional Title")<br>

---

## Part 11. Использование утилиты df
- ![Alt text](src/11.png "Optional Title")<br>
bytes
- ![Alt text](src/11.1.png "Optional Title")<br>
ext4

---

## Part 12. Использование утилиты du
- ``du command:``<br>
![Alt text](src/12.png "Optional Title")<br>
- ``/home:``<br>
![Alt text](src/12.1.png "Optional Title")<br>
- ``/var:``<br>
![Alt text](src/12.2.png "Optional Title")<br>
- ``/var/log/*:``<br>
![Alt text](src/12.3.png "Optional Title")<br>

---

## Part 13. Установка и использование утилиты ncdu
- ``Установка``<br>
![Alt text](src/13.png "Optional Title")<br>
- ``/home``<br>
![Alt text](src/13.1.png "Optional Title")<br>
- ``/var``<br>
![Alt text](src/13.2.png "Optional Title")<br>
- ``/var/log``<br>
![Alt text](src/13.3.png "Optional Title")<br>

---

## Part 14. Работа с системными журналами
- ``Последняя авторизация``<br>
![Alt text](src/14.png "Optional Title")<br>
- ``Перезапуск OpenSSH Server``<br>
![Alt text](src/14.1.png "Optional Title")<br>

---

## Part 15. Использование планировщика заданий CRON
- ``Создание задачи в cron``<br>
![Alt text](src/15.png "Optional Title")<br>
- ``uptime каждые 2 минуты``<br>
![Alt text](src/15.1.png "Optional Title")<br>
- ``Вывели список задач``<br>
![Alt text](src/15.2.png "Optional Title")<br>
- ``Удалили все задачи вывели список``<br>
![Alt text](src/15.3.png "Optional Title")<br>