Выполнил все шаги по установке docker

В качестве подтвреждения установки  Docker  запускаю

	docker run hello-world

<imagesrc = "/images/Снимок экрана от 2024-04-20 21-02-07.png">

Создал группу docker и добавил в нее пользователя, поэтому docker запускается без sudo

Затем установил docker-compose. И проверил установку командой:

	docker-compose —version








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










	Создаю 3 Dockerfile    файла   для каждой из программ:

~/docker_linux / Dockerfile-time 
~/docker_linux / Dockerfile-date
~/docker_linux / Dockerfile-greeting







	Создаю docker-compose.yml  файл  в  той же папке:


	Содержимое каталога     ~/docker_linux :




	Чтоб созать образ  контейнера  программы для вывода аремя на экран
создаю Dockerfile

	























	Проверяю какие есть орбразы

docker images



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

 

	Запускаю команду

docker ps -a

Вижу что новый контейнер существует,но не работает
Запускаю 
docker container prune

что б закрыть все контейнеры

	Запускаю 
docker ps -a
и вижу нет работающих контейнеров








	Затем с помощью docker-compose.yml   создаю несколько образов и запускаю их 

Ввожу команду 
docker-compose up

и вижу как создаются образы и запускаются контейнеры. И на экран выводятся приветствие, дата и время: 





	



	Запускаю 
docker ps -a

вижу 3 работающих контейнера. Ввожу

docker container prune

чтоб закрыть контейнеры. И воожу 
docker images

и вижу 3 новых образа.



	Для завершения ввожу 
docker-compose down


