Привет, меня зовут **Алина** 👋

Учусь на курсе ![logo_sf](imgforreadme/logo_sf.png) 

**Fullstack разработчик на Python**
 

Блок **DevOps**
# Docker


[![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=F71104&random=false&width=435&lines=G4-Docker)](https://git.io/typing-svg)
___



**Задание:**

![task](imgforreadme/task.png)

**Проект:**

![VB logo](https://antowka.ru/wp-content/uploads/2023/04/VirtualBox-Logo-1536x960.png)

![docker logo](https://blog.skillfactory.ru/wp-content/uploads/2023/02/vertical-logo-monochromatic-2822952.png)

![nginx logo](https://webhostinggeeks.com/blog/wp-content/uploads/2023/05/Nginx_server-optimized.png)

![gunicorn logo](https://i.pinimg.com/236x/e8/15/3e/e8153e33fd91bb10862e914fbb904ad4.jpg?nii=t)

![django logo](https://static18.tgcnt.ru/posts/_0/43/43f7a6914a8de530ef1c3d027fb48508.jpg)

### **Быстрый старт:**
**Для запуска проекта необходимо:**

Скачать [образ Docker](https://hub.docker.com/repository/docker/nimalia3/django_app/general):

```bash 
docker pull nimalia3/django_app:latest
```
и запустить :
```bash 
docker run -p 8000:8000 -p 80:80 -p 5432:5432 nimalia/g4-sf-docker:latest
```

После завершения установки и запуска контейнеров, заходим в браузере по адресу:
 http://localhost:8000



**🛠️Технические нюансы🔩**

1. Установка Docker 

```bash 
curl -fsSL https://get.docker.com/ | sh 
 ```

2. Добавляем пользователя в группу ```docker```
```bash
sudo usermod -aG docker $(whoami)
```
3. Запустим службу и настроим автозапуск:
```bash
sudo systemctl start docker && sudo systemctl enable docker
```
4. Cоздать ```Dockerfile```
```bash
touch Dockerfile
vim Dockerfile
```
Для редактирования нажать 
```bash
i
```
для сохранения и выхода нажимаем 
```bash
esc 
: wq
```

```Dockerfile``` будет следующим:
![snapshot_dockerfile](imgforreadme/snapshot_dockerfile.png)

5. ```nginx.conf``` будет следующим:

![snapshot_nginx1](imgforreadme/nginx1.png)
![snapshot_nginx2](imgforreadme/nginx1.png)

6. Запуск двух сервисов (Nginx и Gunicorn) в одной команде CMD не рекомендуется. Вместо этого, можно создать Bash-скрипт, который будет запускать оба сервиса, и вызвать этот скрипт из Dockerfile.  
Скрипт ```start.sh``` будет следующим:
![snapshot_script](imgforreadme/script.png)

6. ```requirements.txt``` будет следующим:
```bash
Django==3.2.8
gunicorn==20.1.0
psycopg2-binary==2.9.1
```
7. Построить образ (в той же директории, что и Dockerfile), запустив команду:
```bash
docker build -t django_app .
```
8. И запустим контейнер:
```bash
docker run -d --name djangocont -p 80:80 -p 8000:8000 django_app
```

📝 для проверки:
```bash
docker logs djangocont
```
9. Разместить образ на [Dockerhub](https://hub.docker.com/repository/docker/nimalia3/django_app/general):
 ```bash
 docker images
docker login
docker push nimalia3/django_app:latest
```
📝 отличная [статья](https://dzen.ru/a/ZKKGZua1NxzJ_2ak) по размещению и скачиванию образа на Dockerhub


----
```` Спасибо за уделенное время! 🙏 ````

___

![](https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Nimalia&theme=solarized_dark)


![](https://komarev.com/ghpvc/?username=Nimalia)

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=anuraghazra)](https://github.com/anuraghazra/github-readme-stats)