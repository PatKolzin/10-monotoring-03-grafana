# Домашнее задание к занятию 14 «Средство визуализации Grafana»

## Задание повышенной сложности



## Обязательные задания

### Задание 1

1. Используя директорию [help](./help) внутри этого домашнего задания, запустите связку prometheus-grafana.
1. Зайдите в веб-интерфейс grafana, используя авторизационные данные, указанные в манифесте docker-compose.
1. Подключите поднятый вами prometheus, как источник данных.
1. Решение домашнего задания — скриншот веб-интерфейса grafana со списком подключенных Datasource.
### Ответ:

![1_configure](https://github.com/PatKolzin/10-monotoring-03-grafana/assets/75835363/49164150-7ed6-4f5d-83ec-a1d852982d9f)

## Задание 2

Изучите самостоятельно ресурсы:

1. [PromQL tutorial for beginners and humans](https://valyala.medium.com/promql-tutorial-for-beginners-9ab455142085). - ССЫЛКА НЕ РАБОТАЕТ
1. [Understanding Machine CPU usage](https://www.robustperception.io/understanding-machine-cpu-usage).
1. [Introduction to PromQL, the Prometheus query language](https://grafana.com/blog/2020/02/04/introduction-to-promql-the-prometheus-query-language/).

Создайте Dashboard и в ней создайте Panels:

- утилизация CPU для nodeexporter (в процентах, 100-idle);
```
100 * (rate(node_cpu_seconds_total{mode="system"}[1m]))
```
- CPULA 1/5/15;
```
node_load1
node_load5
node_load15
```
- количество свободной оперативной памяти;
```
node_memory_MemFree_bytes
```
- количество места на файловой системе.
```
node_filesystem_avail_bytes/(1024*1024*1024)
```
Для решения этого задания приведите promql-запросы для выдачи этих метрик, а также скриншот получившейся Dashboard.
![2-1_cpu](https://github.com/PatKolzin/10-monotoring-03-grafana/assets/75835363/f273b222-08bd-476f-961a-366a745260e8)
![2-2_cpula](https://github.com/PatKolzin/10-monotoring-03-grafana/assets/75835363/b2cd362b-acca-48cf-8121-9aa060662078)
![2-3_mem_free](https://github.com/PatKolzin/10-monotoring-03-grafana/assets/75835363/617f8f6a-63f5-4782-ad68-394c83cdf4cf)
![2-4_hdd](https://github.com/PatKolzin/10-monotoring-03-grafana/assets/75835363/5d2f641c-092b-430c-8b79-32a91195ea6a)



## Задание 3

1. Создайте для каждой Dashboard подходящее правило alert — можно обратиться к первой лекции в блоке «Мониторинг».
1. В качестве решения задания приведите скриншот вашей итоговой Dashboard.
### Ответ:
![3_alert](https://github.com/PatKolzin/10-monotoring-03-grafana/assets/75835363/9a384027-8190-4389-81e0-45b84fc255b7)


## Задание 4

1. Сохраните ваш Dashboard.Для этого перейдите в настройки Dashboard, выберите в боковом меню «JSON MODEL». Далее скопируйте отображаемое json-содержимое в отдельный файл и сохраните его.
1. В качестве решения задания приведите листинг этого файла.
### Ответ:
[Json](https://github.com/PatKolzin/10-monotoring-03-grafana/blob/main/dash2.json)

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.
