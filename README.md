Выполнил все шаги по установке docker

В качестве подтвреждения установки  Docker  запускаю

		docker run hello-world

<image src = "/images/Снимок экрана от 2024-04-20 21-02-07.png">


Создал группу docker и добавил в нее пользователя, поэтому docker запускается без sudo

Затем установил docker-compose. И проверил установку командой:

		docker-compose —version

<image src = "/images/Снимок экрана от 2024-04-20 21-09-49.png">

Далее создаю файлы для создания образа.

Три программы на python  которые выводят  :

	время
	дату
	приветствие

Программы в файлах:

		~/docker_linux / time.py
		~/docker_linux / date.py
		~/docker_linux / greet.py


Содержимое файлов на скриншотах



<image src = "/images/Снимок экрана от 2024-04-20 21-18-08.png">

<image src = "/images/Снимок экрана от 2024-04-20 21-19-11.png">

<image src = "/images/Снимок экрана от 2024-04-20 21-19-57.png">



Cоздаю 3 Dockerfile    файла   для каждой из программ:

		~/docker_linux / Dockerfile-time 
		~/docker_linux / Dockerfile-date
		~/docker_linux / Dockerfile-greeting

<image src = "/images/Снимок экрана от 2024-04-20 21-25-09.png">

<image src = "/images/Снимок экрана от 2024-04-20 21-26-00.png">

<image src = "/images/Снимок экрана от 2024-04-20 21-27-01.png">

Создаю docker-compose.yml  файл  в  той же папке:
<image src = "/images/Снимок экрана от 2024-04-20 21-29-57.png">

Содержимое каталога    ~/docker_linux :

<image src = "/images/Снимок экрана от 2024-04-20 21-31-45.png">

Чтоб созать образ  контейнера  программы для вывода аремя на экран
создаю Dockerfile

<image src = "/images/Снимок экрана от 2024-04-20 21-40-15.png">

Проверяю какие есть орбразы

		docker images
<image src = "/images/Снимок экрана от 2024-04-20 21-45-07.png">


Затем создаю образ 
		docker build .
Проверяю что появился
		docker images
Показывает новый образ

		REPOSITORY         TAG         IMAGE ID       CREATED          SIZE
		<none>             <none>      c6242e8a70cf   26 seconds ago   1.04GB

Запускаю новый образ используя id

		docker run  c6242e8a70cf

вижу что программа работает, появилось сообщение с текущим временем
<image src = "/images/Снимок экрана от 2024-04-20 21-48-23.png">

Запускаю команду

		docker ps -a

Вижу что новый контейнер существует,но не работает
Запускаю 
		docker container prune

что б закрыть все контейнеры

Запускаю 
		docker ps -a
и вижу нет работающих контейнеров

<image src = "/images/Снимок экрана от 2024-04-20 21-57-53.png"> 

Затем с помощью docker-compose.yml   создаю несколько образов и запускаю их 

Ввожу команду 
		docker-compose up

и вижу как создаются образы и запускаются контейнеры. И на экран выводятся приветствие, дата и время: 


<image src = "/images/Снимок экрана от 2024-04-20 22-06-15.png">
	Запускаю 
		docker ps -a

вижу 3 работающих контейнера. Ввожу

		docker container prune

чтоб закрыть контейнеры. И воожу 
		docker images

и вижу 3 новых образа.

<image src = "/images/Снимок экрана от 2024-04-20 22-13-02.png">

Для завершения ввожу 
		docker-compose down


