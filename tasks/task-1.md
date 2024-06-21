## Задание 1 - Docker CLI
1. Загрузите образ `busybox` последней версии
1. Запустите новый контейнер `busybox` с командой `ping` сайта `netology.ru`, и количеством пингов 7, поименуйте контейнер `pinger`
1. Выведите на список всех контейнеров - запущенных и остановленных
1. Выведите на экран логи контейнера с именем `pinger`
1. Запустите второй раз контейнера с именем `pinger`
1. Выведите на список всех контейнеров - запущенных и остановленных
1. Выведите на экран логи контейнера с именем `pinger`
1. Определите по логам общее количество запусков команды `ping` и какое общее количество отправленых запросов
1. Удалите контейнер с именем `pinger`
1. Удалите образ `busybox`

### Команды и ответы
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker pull busybox
Using default tag: latest
latest: Pulling from library/busybox
Digest: sha256:9ae97d36d26566ff84e8893c64a6dc4fe8ca6d1144bf5b87b2b85a32def253c7
Status: Image is up to date for busybox:latest
docker.io/library/busybox:latest

What's Next?
  1. Sign in to your Docker account → docker login
  2. View a summary of image vulnerabilities and recommendations → docker scout quickview busybox


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker run --name pinger -i -t busybox ping netology.ru -c 7
PING netology.ru (172.67.21.207): 56 data bytes
64 bytes from 172.67.21.207: seq=0 ttl=63 time=25.974 ms
64 bytes from 172.67.21.207: seq=1 ttl=63 time=39.272 ms
64 bytes from 172.67.21.207: seq=2 ttl=63 time=26.302 ms
64 bytes from 172.67.21.207: seq=3 ttl=63 time=26.274 ms
64 bytes from 172.67.21.207: seq=4 ttl=63 time=65.986 ms
64 bytes from 172.67.21.207: seq=5 ttl=63 time=44.904 ms
64 bytes from 172.67.21.207: seq=6 ttl=63 time=36.147 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 25.974/37.837/65.986 ms


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
c4b80fe078d2   busybox   "ping netology.ru -c…"   39 seconds ago   Exited (0) 32 seconds ago             pinger


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker logs -f -t pinger
2024-06-21T11:36:00.832587484Z PING netology.ru (172.67.21.207): 56 data bytes
2024-06-21T11:36:00.858736692Z 64 bytes from 172.67.21.207: seq=0 ttl=63 time=25.974 ms
2024-06-21T11:36:01.872219106Z 64 bytes from 172.67.21.207: seq=1 ttl=63 time=39.272 ms
2024-06-21T11:36:02.859862861Z 64 bytes from 172.67.21.207: seq=2 ttl=63 time=26.302 ms
2024-06-21T11:36:03.860300739Z 64 bytes from 172.67.21.207: seq=3 ttl=63 time=26.274 ms
2024-06-21T11:36:04.900163535Z 64 bytes from 172.67.21.207: seq=4 ttl=63 time=65.986 ms
2024-06-21T11:36:05.879486005Z 64 bytes from 172.67.21.207: seq=5 ttl=63 time=44.904 ms
2024-06-21T11:36:06.871539453Z 64 bytes from 172.67.21.207: seq=6 ttl=63 time=36.147 ms
2024-06-21T11:36:06.871581826Z
2024-06-21T11:36:06.871588669Z --- netology.ru ping statistics ---
2024-06-21T11:36:06.871594751Z 7 packets transmitted, 7 packets received, 0% packet loss
2024-06-21T11:36:06.871601173Z round-trip min/avg/max = 25.974/37.837/65.986 ms


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                          PORTS     NAMES
c4b80fe078d2   busybox   "ping netology.ru -c…"   About a minute ago   Exited (0) About a minute ago             pinger


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rm pinger
pinger


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rmi busybox
Untagged: busybox:latest
Untagged: busybox@sha256:9ae97d36d26566ff84e8893c64a6dc4fe8ca6d1144bf5b87b2b85a32def253c7
Deleted: sha256:65ad0d468eb1c558bf7f4e64e790f586e9eda649ee9f130cd0e835b292bbc5ac
Deleted: sha256:d51af96cf93e225825efd484ea457f867cb2b967f7415b9a3b7e65a2f803838a