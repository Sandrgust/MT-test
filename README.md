#  Инструкция по работе с тестовым проектом MT-test

# Описание
В репозитории проекта находятся две папкки (grafana и telegraph). В telegraph находится конфигурационный файл. Вне папок находятся .env файл(по хорошему его нужно спрятать), нужный для docker-compose.yml. А также json файл с уже настроенным дашбордом для проверки его нужно будет импортировать в grafana. 

# Подготовка машины к работе

Тесты происходили на `ubuntu 20.04`.  
Для начала необходимо установить `docker` и `docker-compose`:  

1) Для `Ubuntu` https://docs.docker.com/engine/install/ubuntu/  
2) Для `Centos` https://docs.docker.com/engine/install/centos/  
3) Для `остальных систем` https://docs.docker.com/engine/install/  

`Docker-compose:`
1) https://docs.docker.com/compose/install/linux/#install-using-the-repository

Если лень переходить по странным сслыкам, скопируйте следующие `строки` :

`DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}`    
`mkdir -p $DOCKER_CONFIG/cli-plugins`  
`curl -SL https://github.com/docker/compose/releases/download/v2.11.0/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose`  
`chmod +x $DOCKER_CONFIG/cli-plugins/docker-compose`  

Затем заходим в любую папку и клонируем репозиторий, новая директория будет с именем MT-test  
Далее необходимо архив `data_vol.tar` скопировать в папку томов докера   
У меня путь был `/var/snap/docker/common/var-lib-docker/volumes`   
Затем распаковать его и на новую папку mt-test_grafana_data(mt-test - название папки где будет проект) поставить права  `chmod -R a+w mt-test_grafana_data/`  
Далее заходим в папку нашего проекта и запусаем docker-compose up

Grafana использует порт 3000 по стандарту
Креды для входа админа admin admin
Креды для входа гостя с правами viewer guest guest

