# darthnitrox_microservices
darthnitrox microservices repository  

# Docker-1
Познакомился с базовыми командами docker. Научился запускать контейнера. После сравнения вывода комманд docker inspect <id_image> docker inspect <id_container> понял разницу между коннтейнером и image. Image - шаблон из которого создается конейнер.

# Docker-2
Был создан docker-host. Был подготовлен монолитный образ приложения. Создан контейнер на docker-host и на локальной машине, предварительно image dartnitrox/otus-reddit:1.0 был залит на docker hub
docker inspect conrainer
Присутсвует идентифкатор образа на основе которого был создан контейнер  
Какие порты октрыты слушает приложение внутри контейнера  
Настройки выделяемы русурсов под контейнер  
Сетевые настройки контейнера  
Время старта и завершнение выполнения контейнера  
Дирректории доступные для чтения  

В image пристуствует используемый драйвер фаловой системы overlay2  
Наличие базового конфига для запуска контейнера "ContainerConfig"  где пристусвует описание  переменных окружения доступных после запуска контейнера

# Docker-3
Разделили приложение на несколько контейнеров отдельно контейнер с volume MongoDB создали сеть для взаимодейтсвия контейнеров между собой и возможности обращения через network-alias. 
Уменьшили размер собираемых контейнеров через оптимизацю выполнения комманд установки и используемого образа для сборки. Протестировал создание контейнеров на локальной машине и на docker-host машине.

# Docker-4
Можно изменить префикс создавамых сущностей через docker-compose двумя способами  
1. Изменить переменную COMPOSE_PROJECT_NAME= < your project >
2. Выполнить docker-compose с флагом -p < your project > up -d

# Gitlab-ci-1
Развернул gitlab, настроил runner, познакомился с описанием этапов тестирования приложения reddit .gitlab-ci.yml

# Gitlab-ci-2
Усовершенствовал текущий pipline:  
- Добавил динамические окружения
- Добавил окружения для препродуктового тестирования приложения (stage)
- Продуктовое коружение (production)

# Monitoring-1
В процесе было выполнено развертывание prometheus и его настройка, node exporter. Подключены endpoint ui, comment, post-py. Добавлено описание разверытвания сервисов prometheus и node exporter в docker-compose.yml

# Monitoring-2
Была установлена GRAFANA для визуализации метрик из prometheus. Был установлен и настроен alert в случае отказа основных сервисов приложения. Был настроен Exporter для сбора метрик по работе docker контейнеров.

# Logging-1
Добавил новый сервис для сбора логов elasticsearch, систему визуализации логов kibana, систему обработки логов fluentd, систему распределенного трейса zipkin. Распрасил логи сервисов post и ui.
