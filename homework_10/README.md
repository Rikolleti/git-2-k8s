# Домашнее задание к занятию «Как работает сеть в K8s»

### Цель задания

Настроить сетевую политику доступа к подам.

### Чеклист готовности к домашнему заданию

1. Кластер K8s с установленным сетевым плагином Calico.

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. [Документация Calico](https://www.tigera.io/project-calico/).
2. [Network Policy](https://kubernetes.io/docs/concepts/services-networking/network-policies/).
3. [About Network Policy](https://docs.projectcalico.org/about/about-network-policy).

-----

### Задание 1. Создать сетевую политику или несколько политик для обеспечения доступа

1. Создать deployment'ы приложений frontend, backend и cache и соответсвующие сервисы.
2. В качестве образа использовать network-multitool.
3. Разместить поды в namespace App.
4. Создать политики, чтобы обеспечить доступ frontend -> backend -> cache. Другие виды подключений должны быть запрещены.
5. Продемонстрировать, что трафик разрешён и запрещён.

Ответ:

<img width="729" height="170" alt="1" src="https://github.com/user-attachments/assets/2a1687d4-4546-4e3f-b510-86316dd43f8d" />

<img width="719" height="84" alt="2" src="https://github.com/user-attachments/assets/888f45eb-eab6-4d14-9e17-16052bb140d2" />

Без политик доступ есть:
<img width="1007" height="103" alt="3" src="https://github.com/user-attachments/assets/738436cc-cd3f-40c7-a370-143737357edd" />

Навесил политики:
<img width="930" height="224" alt="4" src="https://github.com/user-attachments/assets/11a893ed-aa14-4bc7-858f-0518021f733f" />

Доступ frontend -> backend -> cache есть:
<img width="1015" height="72" alt="5" src="https://github.com/user-attachments/assets/3995603a-177a-4e69-a3aa-0e8ce67b08e2" />

Доступа frontend -> cache нет / backend -> frontend нет:
<img width="1066" height="101" alt="6" src="https://github.com/user-attachments/assets/a0f51922-58c5-46bc-b66d-d21f2d34db87" />


### Правила приёма работы

1. Домашняя работа оформляется в своём Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд, а также скриншоты результатов.
3. Репозиторий должен содержать тексты манифестов или ссылки на них в файле README.md.
