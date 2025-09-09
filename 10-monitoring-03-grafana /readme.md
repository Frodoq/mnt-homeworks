# Домашнее задание к занятию 14 «Средство визуализации Grafana»

## Обязательные задания

### Задание 1

1. Используя директорию [help](./help) внутри этого домашнего задания, запустите связку prometheus-grafana.
1. Зайдите в веб-интерфейс grafana, используя авторизационные данные, указанные в манифесте docker-compose.
1. Подключите поднятый вами prometheus, как источник данных.
1. Решение домашнего задания — скриншот веб-интерфейса grafana со списком подключенных Datasource.
<img width="1555" height="674" alt="image" src="https://github.com/user-attachments/assets/b02b7524-5637-4517-8f39-56b0e56d227f" />
<img width="1916" height="907" alt="image" src="https://github.com/user-attachments/assets/7bb7d093-6de3-44d0-9230-46c0e938dfc3" />


## Задание 2

Изучите самостоятельно ресурсы:

1. [PromQL tutorial for beginners and humans](https://valyala.medium.com/promql-tutorial-for-beginners-9ab455142085).
1. [Understanding Machine CPU usage](https://www.robustperception.io/understanding-machine-cpu-usage).
1. [Introduction to PromQL, the Prometheus query language](https://grafana.com/blog/2020/02/04/introduction-to-promql-the-prometheus-query-language/).

Создайте Dashboard и в ней создайте Panels:

- утилизация CPU для nodeexporter (в процентах, 100-idle);
- CPULA 1/5/15;
- количество свободной оперативной памяти;
- количество места на файловой системе.

Для решения этого задания приведите promql-запросы для выдачи этих метрик, а также скриншот получившейся Dashboard.

<img width="1919" height="735" alt="image" src="https://github.com/user-attachments/assets/3283e475-5cb1-4b16-9f8d-7f755528db66" />
1) Утилизация CPU (100-idle):
100 - (avg by(instance)(irate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)
   
3) Load Average (1/5/15):
node_load1{}
node_load5{}
node_load15{}

5) Свободная оперативная память:
node_memory_MemFree_bytes{}

7) Свободное место на файловой системе:
node_filesystem_avail_bytes{mountpoint="/"}

## Задание 3

1. Создайте для каждой Dashboard подходящее правило alert — можно обратиться к первой лекции в блоке «Мониторинг».
1. В качестве решения задания приведите скриншот вашей итоговой Dashboard.
<img width="1099" height="775" alt="image" src="https://github.com/user-attachments/assets/64af3b06-70f3-42e8-acde-ade864db055a" />
<img width="1863" height="725" alt="image" src="https://github.com/user-attachments/assets/a2063739-f9f8-4661-bd4b-70d918a89297" />



## Задание 4

1. Сохраните ваш Dashboard.Для этого перейдите в настройки Dashboard, выберите в боковом меню «JSON MODEL». Далее скопируйте отображаемое json-содержимое в отдельный файл и сохраните его.
1. В качестве решения задания приведите листинг этого файла.
https://github.com/Frodoq/mnt-homeworks/blob/MNT-video/10-monitoring-03-grafana%20/grafana_borda.json
---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
