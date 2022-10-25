University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2022/2023

Group: K4111c

Author: Avdeeva Margarita Leonidovna

Lab: Lab1

Date of create: 10.10.2022

Date of finished: --.--.2022

minikube start запуск кластера minikube

minikube kubectl -- apply -f lab1.yaml создание ресурсов kuberntes из манифеста

minikube kubectl -- expose pod vault --type=NodePort --port=8200 команда необходимая для того, Чтобы получить доступ к поде извне, создание объекта сервис (Service):

minikube kubectl -- port-forward service/vault 8200:8200  команда, которая прокидывает порт компьютера в контейнер 

minikube stop  остановка кластера

Где взять токен? 

- токен можно найти, используя команду minikube kubectl -- logs vault

Схема:

![схема](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab1/lab1_.png)

Расположение токена:

![расположение токена](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab1/lab1_3.png)

Результат работы:

![результат работы](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab1/lab1_2.png)
