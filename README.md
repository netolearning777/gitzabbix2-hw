# Домашнее задание к занятию "`Система мониторинга Zabbix. Часть 2`" - `Гусев Алексей`

### Задание 1

`Создайте свой шаблон, в котором будут элементы данных, мониторящие загрузку CPU и RAM хоста`

1. `В веб-интерфейсе Zabbix Servera в разделе Templates создайте новый шаблон`
2. `Создайте Item который будет собирать информацию об загрузке CPU в процентах`
3. `Создайте Item который будет собирать информацию об загрузке RAM в процентах`

![Название скриншота 1](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_14-30-06.png)
![Название скриншота 2](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_14-30-56.png)
![Название скриншота 3](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_14-31-32.png)
![Название скриншота 4](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_14-32-32.png)

---
### Задание 2

`Добавьте в Zabbix два хоста и задайте им имена <фамилия и инициалы-1> и <фамилия и инициалы-2>. Например: ivanovii-1 и ivanovii-2.`

1. `Установите Zabbix Agent на 2 виртмашины, одной из них может быть ваш Zabbix Server`
2. `Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов`
3. `Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Server`
4. `Прикрепите за каждым хостом шаблон Linux by Zabbix Agent`
5. `Проверьте что в разделе Latest Data начали появляться данные с добавленных агентов`

---
### Задание 3

`Привяжите созданный шаблон к двум хостам. Также привяжите к обоим хостам шаблон Linux by Zabbix Agent.`

1. `Зайдите в настройки каждого хоста и в разделе Templates прикрепите к этому хосту ваш шаблон`
2. `Так же к каждому хосту привяжите шаблон Linux by Zabbix Agent`
3. `Проверьте что в раздел Latest Data начали поступать необходимые данные из вашего шаблона`


![Название скриншота 5](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_15-03-32.png)
![Название скриншота 6](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_15-05-16.png)
![Название скриншота 7](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_15-05-36.png)
![Название скриншота 8](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_15-06-03.png)
![Название скриншота 9](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_15-06-20.png)

---
### Задание 4

`Создайте свой кастомный дашборд.`

1. `В разделе Dashboards создайте новый дашборд`
2. `Разместите на нём несколько графиков на ваше усмотрение.`

![Название скриншота 10](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_15-31-11.png)
![Название скриншота 11](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-20_15-31-29.png)
