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
![result1](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab3/lab3_1.png)

```bash
kubectl apply -f ReplicaSet_lab3.yaml
```

Проверим, что переменные добавлены

![result2](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab3/lab3_2.png)

Включим minikube addons enable ingress и проверим,что ingress включен

```bash
minikube addons enable ingress
minikube addons list
```
![result3](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab3/lab3_3.png)


сгенерируем TLS сертификат, испольюзуя openssl


```bash
openssl genrsa -out ca.key 2048
openssl req -x509 -new -nodes -days 365 -key ca.key ca.crt
```
Создадим secret и добавим в него сертификат

```bash
kubectl create secret tls lab3-secret \
--key ca.key \
--cert ca.crt
```

![result4](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab3/lab3_4.png)

Пропишем DNS:

![result6](labs/lab3/lab3_6.PNG)

Проверим сертификат

![result5](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab3/lab3_5.png)

## Схема

![result7](labs/lab3/lab3_sheme.png)


