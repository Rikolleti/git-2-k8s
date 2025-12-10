# Домашнее задание к занятию Troubleshooting

### Цель задания

Устранить неисправности при деплое приложения.

### Чеклист готовности к домашнему заданию

1. Кластер K8s.

### Задание. При деплое приложение web-consumer не может подключиться к auth-db. Необходимо это исправить

1. Установить приложение по команде:
```shell
kubectl apply -f https://raw.githubusercontent.com/netology-code/kuber-homeworks/main/3.5/files/task.yaml
```
2. Выявить проблему и описать.
3. Исправить проблему, описать, что сделано.
4. Продемонстрировать, что проблема решена.

Ответ:

Сервисы живут в отдельных namespace-х:

<img width="1326" height="139" alt="1" src="https://github.com/user-attachments/assets/88216e8b-a60e-414c-a47a-b0659af24c19" />

Поэтому при попытке сделать curl появляется ошибка из-за того, что в namespace web отсутвует auth-db:

<img width="1131" height="266" alt="2" src="https://github.com/user-attachments/assets/0cefbdd6-35cb-4138-b163-dbc7f18623e6" />

Заменил в task.yaml строку
```shell
while true; do curl auth-db; sleep 5; done
```

на
```shell
while true; do curl auth-db.data; sleep 5; done
```
То есть теперь запрос будет идти именно в namespace data

<img width="1168" height="521" alt="3" src="https://github.com/user-attachments/assets/cdd2da6e-0a71-4d21-b4a2-594f90e97967" />


### Правила приёма работы

1. Домашняя работа оформляется в своём Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд, а также скриншоты результатов.
3. Репозиторий должен содержать тексты манифестов или ссылки на них в файле README.md.
