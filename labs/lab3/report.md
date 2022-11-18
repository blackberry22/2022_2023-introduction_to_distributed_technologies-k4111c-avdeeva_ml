University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2022/2023

Group: K4111c

Author: Avdeeva Margarita Leonidovna

Lab: Lab3

Date of create: 11.11.2022

Date of finished: --.--.2022


# Выполнение лабораторной работы

## Code trace

Создадим ConfigMap с переменными: REACT_APP_USERNAME, REACT_APP_COMPANY_NAME.

```bash
kubectl apply -f config-map_lab3.yaml
```

создадим replicaSet с 2 репликами контейнера ifilyaninitmo/itdt-contained-frontend:master и используя ранее созданный configMap передадим переменные REACT_APP_USERNAME, REACT_APP_COMPANY_NAME .


```bash
kubectl apply -f ReplicaSet_lab3.yaml
```

Проверим, что переменные добавлены

[]скрин2

Включим minikube addons enable ingress и проверим,что ingress включен

```bash
minikube addons enable ingress
minikube addons list
```
[] скрин 1


сгенерируем TLS сертификат, испольюзуя openssl

[] скрины

Проверим, сертификат

[]скрин

схема
[]


