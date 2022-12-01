University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2022/2023

Group: K4111c

Author: Avdeeva Margarita Leonidovna

Lab: Lab4

Date of create: 25.11.2022

Date of finished: --.--.2022

# Выполнение лабораторной работы

## Code trace

Создадим кластер minikube с 2 нодами, а также установим плагин CNI=calico 

```bash
minikube start --nodes 2 --cni calico --kubernetes-version=v1.24.3
minikube kubectl -- get nodes
```
Убедимся, что 2 ноды запущены

![result1](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab4/lab4_1.png)

Проверим, что необходимые ресурсы созданы

```bash
Minikube kubectl – get pods –A
```
![result2](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab4/lab4_2.png)

Статус нод можно узнать, используя следующую команду:

```bash
minikube status -p minikube
```
![result3](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab4/lab4_3.png)

Установим calicoctl pod, манифест скопирован с официального сайта calico:

```bash
kubectl apply -f calicoctl.yaml
```
![result4](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab4/lab4_4.PNG)

Зададим lables для нод по географическому признаку:

```bash
kubectl label nodes minikube zone=west
kubectl label nodes minikube-m02 zone=east
```

Создадим ip pool, удалим пул по умолчанию:

```bash
kubectl exec -i -n kube-system calicoctl -- /calicoctl create -f - < ip_pool.yaml
kubectl exec -i -n kube-system calicoctl -- /calicoctl  delete ippools default-ipv4-ippool
kubectl exec -i -n kube-system calicoctl -- /calicoctl  get ippools -o wide
```
![result5](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab4/lab4_5.png)

Создадим ресурсы: сервис, config map с требуемыми переменными, а также replicaset

```bash
kubectl apply -f resources.yaml
```
![result6](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab4/lab4_6.png)

Пробросим порт:

```bash
kubectl port-forward service/lab4-svc 3000:8000
```
Узнаем IP адреса, полученнные подами:

![result7](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab4/lab4_7.png)

и проверим, что приложение получило IP адрес из пула, заданного в конфигурационном файле:

![result8](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab4/lab4_8.png)

Проверим сетевую связность, используя утилиту ping:

```bash
kubectl exec -it lab4-app-j55mr  -- ping 192.168.2.1
```
![result9](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab4/lab4_9.png)

# Схема

![result10](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab4/lab_4shceme.png)


