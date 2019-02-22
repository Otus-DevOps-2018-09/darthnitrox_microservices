# darthnitrox_microservices
darthnitrox microservices repository  

# Docker-1
Познакомился с базовыми командами docker. Научился запускать контейнера. После сравнения вывода комманд docker inspect <id_image> docker inspect <id_container> понял разницу между коннтейнером и image. Image - шаблон из которого создается конейнер.

# Docker-2
Был создан docker-host. Был подготовлен монолитный образ приложения. Создан контейнер на docker-host и на локальной машине, предварительно image dartnitrox/otus-reddit:1.0 был залит на docker hub

# Docker-3
Разделили приложение на несколько контейнеров отдельно контейнер с volume MongoDB создали сеть для взаимодейтсвия контейнеров между собой и возможности обращения через network-alias. 
Уменьшили размер собираемых контейнеров через оптимизацю выполнения комманд установки и используемого образа для сборки. Протестировал создание контейнеров на локальной машине и на docker-host машине.

# Docker-4
Можно изменить префикс создавамых сущностей через docker-compose двумя способами  
1. Изменить переменную COMPOSE_PROJECT_NAME= < your project >
2. Выполнить docker-compose с флагом -p < your project > up -d
