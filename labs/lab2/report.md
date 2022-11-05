University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2022/2023

Group: K4111c

Author: Avdeeva Margarita Leonidovna

Lab: Lab2

Date of create: 25.10.2022

Date of finished: 05.11.2022

# Выполнение лабораторной работы

## Code trace

Запустим кластер и создадим новый deployment
```bash
minikube start  
minikube kubectl -- apply -f lab2.yaml 
```
Результат можно проверить, перейдя по ip ноды и порту 30200

![result1](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab2/lab2_1.png)

Обновим переменные и применим изменения.
```bash
minikube kubectl -- apply -f lab2.yaml 
```
Проверим, что обновления были применены и убедимся, что значения переменных поменялись

![result2](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab2/lab2_2.png)

Выведем логи

```bash
minikube kubectl -- logs lab2-deployment74645dd58c-p4s7h
```

![logs](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab2/lab2_4.png)


## Схема 

![scheme](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/labs/lab2/lab2_scheme.png)
