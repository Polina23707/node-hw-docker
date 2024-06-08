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
ec562eabd705: Pull complete
Digest: sha256:9ae97d36d26566ff84e8893c64a6dc4fe8ca6d1144bf5b87b2b85a32def253c7
Status: Downloaded newer image for busybox:latest
docker.io/library/busybox:latest

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview busybox


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker run -i -t busybox ping netology.ru -c 7
PING netology.ru (172.67.21.207): 56 data bytes
64 bytes from 172.67.21.207: seq=0 ttl=63 time=83.328 ms
64 bytes from 172.67.21.207: seq=1 ttl=63 time=38.463 ms
64 bytes from 172.67.21.207: seq=2 ttl=63 time=37.077 ms
64 bytes from 172.67.21.207: seq=3 ttl=63 time=38.187 ms
64 bytes from 172.67.21.207: seq=4 ttl=63 time=46.850 ms
64 bytes from 172.67.21.207: seq=6 ttl=63 time=45.775 ms

--- netology.ru ping statistics ---
7 packets transmitted, 6 packets received, 14% packet loss
round-trip min/avg/max = 37.077/48.280/83.328 ms


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
beb50130b96a   busybox   "ping netology.ru -c…"   2 minutes ago    Exited (0) 2 minutes ago              distracted_shirley
298fa7f73d4f   busybox   "ping netology.ru"       2 minutes ago    Exited (0) 2 minutes ago              fervent_buck
88e248064f60   alpine    "ping netology.ru"       7 minutes ago    Exited (0) 6 minutes ago              awesome_easley
d7b1961c26c7   alpine    "ping netology.ru"       15 minutes ago   Exited (0) 14 minutes ago             pinger
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> 


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker logs -f -t pinger
2024-06-08T10:13:06.922600757Z PING netology.ru (172.67.21.207): 56 data bytes
2024-06-08T10:13:06.964615395Z 64 bytes from 172.67.21.207: seq=0 ttl=63 time=43.862 ms
2024-06-08T10:13:07.965463458Z 64 bytes from 172.67.21.207: seq=1 ttl=63 time=44.344 ms
2024-06-08T10:13:08.971792864Z 64 bytes from 172.67.21.207: seq=2 ttl=63 time=49.721 ms
2024-06-08T10:13:09.971903222Z 64 bytes from 172.67.21.207: seq=3 ttl=63 time=49.238 ms
2024-06-08T10:13:11.030562433Z 64 bytes from 172.67.21.207: seq=4 ttl=63 time=107.479 ms
2024-06-08T10:13:11.969809687Z 64 bytes from 172.67.21.207: seq=5 ttl=63 time=46.225 ms
2024-06-08T10:13:12.965461431Z 64 bytes from 172.67.21.207: seq=6 ttl=63 time=41.106 ms
2024-06-08T10:13:13.964654380Z 64 bytes from 172.67.21.207: seq=7 ttl=63 time=39.859 ms
2024-06-08T10:13:14.966389801Z 64 bytes from 172.67.21.207: seq=8 ttl=63 time=41.107 ms
2024-06-08T10:13:15.966139466Z 64 bytes from 172.67.21.207: seq=9 ttl=63 time=40.391 ms
2024-06-08T10:13:16.966704513Z 64 bytes from 172.67.21.207: seq=10 ttl=63 time=40.922 ms
2024-06-08T10:13:17.967169875Z 64 bytes from 172.67.21.207: seq=11 ttl=63 time=40.849 ms
2024-06-08T10:13:18.966189232Z 64 bytes from 172.67.21.207: seq=12 ttl=63 time=39.607 ms
2024-06-08T10:13:19.984470955Z 64 bytes from 172.67.21.207: seq=13 ttl=63 time=57.170 ms
2024-06-08T10:13:20.966150177Z 64 bytes from 172.67.21.207: seq=14 ttl=63 time=38.616 ms
2024-06-08T10:13:21.965390030Z 64 bytes from 172.67.21.207: seq=15 ttl=63 time=37.441 ms
2024-06-08T10:13:22.981964068Z 64 bytes from 172.67.21.207: seq=16 ttl=63 time=53.467 ms
2024-06-08T10:13:23.395918880Z ^C
2024-06-08T10:13:23.395976563Z --- netology.ru ping statistics ---
2024-06-08T10:13:23.395984228Z 17 packets transmitted, 17 packets received, 0% packet loss
2024-06-08T10:13:23.395990019Z round-trip min/avg/max = 37.441/47.729/107.479 ms
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> 


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker run -i -t busybox ping netology.ru -c 7
PING netology.ru (104.22.41.171): 56 data bytes
64 bytes from 104.22.41.171: seq=0 ttl=63 time=34.693 ms
64 bytes from 104.22.41.171: seq=1 ttl=63 time=48.614 ms
64 bytes from 104.22.41.171: seq=2 ttl=63 time=84.034 ms
64 bytes from 104.22.41.171: seq=3 ttl=63 time=45.792 ms
64 bytes from 104.22.41.171: seq=4 ttl=63 time=56.625 ms
64 bytes from 104.22.41.171: seq=5 ttl=63 time=52.601 ms
64 bytes from 104.22.41.171: seq=6 ttl=63 time=45.172 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 34.693/52.504/84.034 ms


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                          PORTS     NAMES
f7ad946fc5b5   busybox   "ping netology.ru -c…"   About a minute ago   Exited (0) About a minute ago             romantic_bhaskara
beb50130b96a   busybox   "ping netology.ru -c…"   7 minutes ago        Exited (0) 7 minutes ago                  distracted_shirley
298fa7f73d4f   busybox   "ping netology.ru"       7 minutes ago        Exited (0) 7 minutes ago                  fervent_buck
88e248064f60   alpine    "ping netology.ru"       12 minutes ago       Exited (0) 11 minutes ago                 awesome_easley
d7b1961c26c7   alpine    "ping netology.ru"       20 minutes ago       Exited (0) 19 minutes ago                 pinger


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker logs -f -t pinger
2024-06-08T10:13:06.922600757Z PING netology.ru (172.67.21.207): 56 data bytes
2024-06-08T10:13:06.964615395Z 64 bytes from 172.67.21.207: seq=0 ttl=63 time=43.862 ms
2024-06-08T10:13:07.965463458Z 64 bytes from 172.67.21.207: seq=1 ttl=63 time=44.344 ms
2024-06-08T10:13:08.971792864Z 64 bytes from 172.67.21.207: seq=2 ttl=63 time=49.721 ms
2024-06-08T10:13:09.971903222Z 64 bytes from 172.67.21.207: seq=3 ttl=63 time=49.238 ms
2024-06-08T10:13:11.030562433Z 64 bytes from 172.67.21.207: seq=4 ttl=63 time=107.479 ms
2024-06-08T10:13:11.969809687Z 64 bytes from 172.67.21.207: seq=5 ttl=63 time=46.225 ms
2024-06-08T10:13:12.965461431Z 64 bytes from 172.67.21.207: seq=6 ttl=63 time=41.106 ms
2024-06-08T10:13:13.964654380Z 64 bytes from 172.67.21.207: seq=7 ttl=63 time=39.859 ms
2024-06-08T10:13:14.966389801Z 64 bytes from 172.67.21.207: seq=8 ttl=63 time=41.107 ms
2024-06-08T10:13:15.966139466Z 64 bytes from 172.67.21.207: seq=9 ttl=63 time=40.391 ms
2024-06-08T10:13:16.966704513Z 64 bytes from 172.67.21.207: seq=10 ttl=63 time=40.922 ms
2024-06-08T10:13:17.967169875Z 64 bytes from 172.67.21.207: seq=11 ttl=63 time=40.849 ms
2024-06-08T10:13:18.966189232Z 64 bytes from 172.67.21.207: seq=12 ttl=63 time=39.607 ms
2024-06-08T10:13:19.984470955Z 64 bytes from 172.67.21.207: seq=13 ttl=63 time=57.170 ms
2024-06-08T10:13:20.966150177Z 64 bytes from 172.67.21.207: seq=14 ttl=63 time=38.616 ms
2024-06-08T10:13:21.965390030Z 64 bytes from 172.67.21.207: seq=15 ttl=63 time=37.441 ms
2024-06-08T10:13:22.981964068Z 64 bytes from 172.67.21.207: seq=16 ttl=63 time=53.467 ms
2024-06-08T10:13:23.395918880Z ^C
2024-06-08T10:13:23.395976563Z --- netology.ru ping statistics ---
2024-06-08T10:13:23.395984228Z 17 packets transmitted, 17 packets received, 0% packet loss
2024-06-08T10:13:23.395990019Z round-trip min/avg/max = 37.441/47.729/107.479 ms


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rm pinger
pinger
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rmi busybox
Error response from daemon: conflict: unable to remove repository reference "busybox" (must force) - container 298fa7f73d4f is using its referenced image 65ad0d468eb1