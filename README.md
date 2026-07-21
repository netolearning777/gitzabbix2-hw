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

---
### Задание 5

`Создайте UserParameter на bash и прикрепите его к созданному вами ранее шаблону. Он должен вызывать скрипт, который:`

* при получении 1 будет возвращать ваши ФИО,
* при получении 2 будет возвращать текущую дату.
```bash
#!/bin/bash
if [ "$1" = "1" ]; then
    echo "Гусев Алексей"
elif [ "$1" = "2" ]; then
    date "+%Y-%m-%d %H:%M:%S"
else
    echo "Ошибка: используйте параметр 1 или 2"
    exit 1
fi
```
![Название скриншота 12](https://github.com/netolearning777/gitzabbix2-hw/blob/main/img/2026-07-21_13-10-30.png)
---

### Задание 5

`Доработайте Python-скрипт из лекции, создайте для него UserParameter и прикрепите его к созданному вами ранее шаблону. Скрипт должен:`
* при получении 1 возвращать ваши ФИО,
* при получении 2 возвращать текущую дату,
* делать всё, что делал скрипт из лекции.

`Python-скрипт`
```python
import datetime
import os
import re
import sys
if (sys.argv[1] == "1"): # Если аргумент равен 1
  print("Гусев Алексей") # Выводим ФИО в консоль
elif (sys.argv[1] == "2"): # Если аргумент равен 2
  current_date = datetime.now().strftime("%Y-%m-%d") # Определяем текущую дату
  print(current_date) # Выводим текущую дату в консоль
elif (sys.argv[1] == '-ping'): # Если -ping
  result=os.popen("ping -c 1 " + sys.argv[2]).read() # Делаем пинг по заданному адресу
  time_result=re.search(r"time=(.*?) ms", result) # Выдёргиваем из результата время
  if time_result:
    print(time_result.group(1)) # Выводим результат в консоль
  else:
    print("Хост недоступен") # Выводим результат в консоль
elif (sys.argv[1] == '-simple_print'): # Если simple_print
  print(sys.argv[2]) # Выводим в консоль содержимое sys.argv[2]
else: # Во всех остальных случаях
  print(f"unknown input: {sys.argv[1]}") # Выводим непонятый запрос в консоль
```
![Название скриншота 13]()


