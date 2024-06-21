## Задание 2 - Environment Variables

Используя Docker CLI выполните следующие действия:
1. Загрузите образ node версии 15.14
1. Запустите контейнер node в интерактивном режиме подключения терминала, поименуйте его `mynode`, передайте две переменные среды `NAME=<ваше имя>` и `SURNAME=<ваша фамилия>`
1. В интерактивной среде выполнения node выполните скрипт, который выведет на экран приветсвтие: `Привет, <ваше имя> <ваша фамилия>!`, эти данные должны быть получены из переменных среды
1. Остановите контейнер
1. Удалите образ node версии 15.14

### Команды и ответы
S D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker pull node:15.14
15.14: Pulling from library/node
Digest: sha256:608bba799613b1ebf754034ae008849ba51e88b23271412427b76d60ae0d0627
Status: Image is up to date for node:15.14
docker.io/library/node:15.14

What's Next?
  1. Sign in to your Docker account → docker login
  2. View a summary of image vulnerabilities and recommendations → docker scout quickview node:15.14
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker ps -a                                                       
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker run -it --env "NAME=Polina" --env "SURNAME=Gorelik" --name mynode node      
Unable to find image 'node:latest' locally
latest: Pulling from library/node
fea1432adf09: Pull complete
5651b5803b18: Pull complete
3873416e6a33: Pull complete
8a142b8b0e69: Pull complete
23885ecc6bd0: Pull complete
fc1dd23b13f8: Pull complete
dfa6f8aa1b8e: Pull complete
cdf8d5cb156d: Pull complete
Digest: sha256:0f0d378942e6bb43a40d63a2463437bd9db8888394793d98aa96c0ac68016797
Status: Downloaded newer image for node:latest
Welcome to Node.js v22.3.0.
Type ".help" for more information.

> console.log('Привет, ' +  process.env.NAME + ' ' + process.env.SURNAME + '!')
Привет, Polina Gorelik!
undefined

Uncaught SyntaxError: Unexpected identifier 'stop'
>
(To exit, press Ctrl+C again or Ctrl+D or type .exit)
>
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker stop mynode                                                 
mynode
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker ps -a                                                       
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
e13ce6950f5e   node      "docker-entrypoint.s…"   21 minutes ago   Exited (0) 24 seconds ago             mynode

PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rm mynode
mynode
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker ps -a        
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
PS D:\03_Учеба\13_Full Stack JS\09_Введение в Nodejs Express\git\node-hw-docker> docker rmi node                                                    
Untagged: node:latest
Untagged: node@sha256:0f0d378942e6bb43a40d63a2463437bd9db8888394793d98aa96c0ac68016797
Deleted: sha256:16d00b0a86e62c1a88248a3bdd7b4a2ae852147a2b351a12df20764760c3d829
Deleted: sha256:95ec63cea31d7d651bcd592b1cc84346e758b47cd07139ab26be922a71fef12b
Deleted: sha256:b548979de189ac0ed55676b11cd54998ef120a08439c778414dc9261e15bfa1d
Deleted: sha256:ce9bc352f196abbe4f13dfaa97ccafeab005c6d7ac9acd7dafe4a5d3e3f5bbd5
Deleted: sha256:462c0ee142a533e3d539f13e402d5761a4de34751675b8123eb14db5d9b52f92
Deleted: sha256:c29e7232ce8dfa0144241df3d535fe2e17fdf9877540ba3a85a7d1ee75707fa5
Deleted: sha256:8468a74e50b90b87dd6135a957c2ce4cdf1479a25bd09a7d8331bb3500362c70
Deleted: sha256:19e9966de433cb7d5a6ef7efe747bd145811912d86211599a9c6ceae0f36d1be
Deleted: sha256:5d64de483bf527bb00d0d2749f8b2b2b21c101e32e6a6be715b7f6c8eae5496b
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