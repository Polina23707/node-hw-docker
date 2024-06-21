## Задание 3 - Volumes

Используя Docker CLI выполните следующие действия:
1. Загрузите образ node версии 15.14
1. Запустите контейнер с именем `first_node` из образа node версии 15.14 в фоновом режиме, подключив папку `data` из текущей директории в `/var/first/data` контейнера
1. Запустите контейнер с именем `second_node` из образа node версии 15.14 в фоновом режиме, подключив папку `data` из текущей директории в `/var/second/data` контейнера
1. Подключитесь к контейнеру `first_node` с помощью exec и создайте текстовый файл любого содержания в `/var/first/data`
1. Добавьте еще один файл в папку `data` на хостовой машине
1. Подключитесь к контейнеру `second_node` с помощью `exec` и получите список файлов в директории `/var/second/data`, выведете на экран содержимое файлов
1. Остановите оба контейнера
1. Удалите оба контейнера
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
  1. Sign in to your Docker account → docker login
  2. View a summary of image vulnerabilities and recommendations → docker scout quickview node:15.14


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker run --rm -d -v ./data:/var/first/data --name first_node node:15.14 sleep infinity

57c52e6738c62b2aeda0a173a97bb64867e8bc730ba14f6c927812288b444ec6
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 ls /
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 ls /var/first
data


What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker run --rm -d -v ./data:/var/second/data --name second_node node:15.14 sleep infinity
22e78eb9048e75c5d24ec99fd22ed9886a9ec4454b3e03f6c9b839364623b68d


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 ls /var/first/data                                        
 
What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 ls                 
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 ls /var/first/     
data

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 touch  /var/first/data/first_file.txt                   

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 cat /var/first/data/first_file.txt   

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 touch /var/first/data/first_file.txt

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 ls /var/first/data
first_file.txt

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 cat /var/first/data/first_file.txt  

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 cat /var/first/data/first_file.txt

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 57c52e6738c62 cat /var/first/data/first_file.txt

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 57c52e6738c62
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 22e78eb904 ls /var/second/data/                 
first_file.txt

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 22e78eb904
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 22e78eb904 touch /var/second/data/second_file.txt

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 22e78eb904
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 22e78eb904 ls /var/second/data/
first_file.txt  second_file.txt

What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 22e78eb904
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker exec -it 22e78eb904 cat /var/second/data/second_file.txt  


What's next?
  Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug 22e78eb904
  Learn more at https://docs.docker.com/go/debug-cli/


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker stop first_node                                                                  
first_node


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker stop second_node
second_node

PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rm second_node  
Error response from daemon: No such container: second_node


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rm first_node 
Error response from daemon: No such container: first_node


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker ps -a                                                                            
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES


PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rmi node:15.14
Untagged: node:15.14
Untagged: node@sha256:608bba799613b1ebf754034ae008849ba51e88b23271412427b76d60ae0d0627
Deleted: sha256:3d3f41722daf1a77c34d6eade6676bbffa2d6a2a21095de2ab0c427a5c942fc9
Deleted: sha256:601382991a159cfc5013ad973158f30b7b7a913e8d7e547b3456deab3ad98022
Deleted: sha256:d5db49eecae8c02c9ea3a79f89c43ded9162bac118a0302a7b514d0df82aa112
Deleted: sha256:a2c1973858d0aad3de0927294602b17c8ef9050c30e0f461e0868997a08552a4
Deleted: sha256:a0153172017a08a521a8be971ca4dcb5fbc4b7227642c12bbb2da6265bd66b50
Deleted: sha256:f1123940e954d335d91b52a40fab4f8144f38ff113ade7d65663071d0f06da6f
Deleted: sha256:f1f4fbb0e7e6e0ce2d9eae1e577f9f6df0a719dd874bff00b2d08895c75c297d
Deleted: sha256:1eb455ab6d45fdbbd90fccff791ffa228080c052acf464f8da1b1d78650bd706
Deleted: sha256:1dbe832a694971a925d7d216f49b700c95f402bd72288f9d37eceb1d59dcf72d
Deleted: sha256:2f4ee6a2e1b5dfb9236cd262e788f9d39109242ca27a4aacb583c8af66ec3ff7
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> 

