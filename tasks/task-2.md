## Задание 2 - Environment Variables

Используя Docker CLI выполните следующие действия:
1. Загрузите образ node версии 15.14
1. Запустите контейнер node в интерактивном режиме подключения терминала, поименуйте его `mynode`, передайте две переменные среды `NAME=<ваше имя>` и `SURNAME=<ваша фамилия>`
1. В интерактивной среде выполнения node выполните скрипт, который выведет на экран приветсвтие: `Привет, <ваше имя> <ваша фамилия>!`, эти данные должны быть получены из переменных среды
1. Остановите контейнер
1. Удалите образ node версии 15.14

### Команды и ответы

PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker pull node:15.14 
15.14: Pulling from library/node
bfde2ec33fbc: Pull complete
787f5e2f1047: Pull complete
7b6173a10eb8: Pull complete
dc05be471d51: Pull complete
55fab5cadd3c: Pull complete
bd821d20ef8c: Pull complete
6041b69671c6: Pull complete
989c5d2d2313: Pull complete
4b57d41e8391: Pull complete
Digest: sha256:608bba799613b1ebf754034ae008849ba51e88b23271412427b76d60ae0d0627
Status: Downloaded newer image for node:15.14
docker.io/library/node:15.14

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview node:15.14


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker run -itd --env "NAME=Polina" --env "SURNAME=Gorelik" --name mynode node                                                             

Unable to find image 'node:latest' locally
docker: Error response from daemon: error creating temporary lease: read-only file system: unknown.
See 'docker run --help'.


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rm mynode
Error response from daemon: container 224da315bdebd4bd3f7604d4369c0cb639653858d8fc709d956b42b972df8549: driver "overlay2" failed to remove root filesystem: unlinkat /var/lib/docker/overlay2/1a3d179b198bce155e86e76f482454e07f1a063a035522906624210c646864ae: read-only file system


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rmi node:15.14
Error response from daemon: conflict: unable to remove repository reference "node:15.14" (must force) - container 224da315bdeb is using its referenced image 3d3f41722daf
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> 