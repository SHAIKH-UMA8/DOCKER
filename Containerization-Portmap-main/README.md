# CONTAINERIZATION OF TODO, SEASON & TRAFFIC
## Step 1: Create Instance and connect it

![image](https://github.com/user-attachments/assets/813e00c4-5fe2-47ba-982e-6e9df1eb8f85)

## Step 2: Install Docker

## Step 3: Upload files of todo,season & traffic

![image](https://github.com/user-attachments/assets/d897d1f1-31e1-4837-9812-b19c7171721f)

## Step 4: Docker file for todo

```
FROM ubuntu:latest

LABEL TODO="file"

RUN apt update

RUN apt install apache2 -y

RUN rm -rf /var/www/html/*

WORKDIR /var/www/html/

RUN mkdir /var/www/html/todo

COPY ./ /var/www/html/todo/

EXPOSE 80
    
CMD ["apachectl", "-D", "FOREGROUND"]
```

## Step 5: Docker file for season

```
FROM ubuntu:latest

LABEL TODO="file"

RUN apt update

RUN apt install apache2 -y

RUN rm -rf /var/www/html/*

WORKDIR /var/www/html/

RUN mkdir /var/www/html/season

COPY ./ /var/www/html/season/

EXPOSE 80
    
CMD ["apachectl", "-D", "FOREGROUND"]
```

## Step 6: Docker file for traffic

```
FROM ubuntu:latest

LABEL TODO="file"

RUN apt update

RUN apt install apache2 -y

RUN rm -rf /var/www/html/*

WORKDIR /var/www/html/

RUN mkdir /var/www/html/traffic

COPY ./ /var/www/html/traffic/

EXPOSE 80
    
CMD ["apachectl", "-D", "FOREGROUND"]
```

## Step 7: Cloning remote repository in Instance

```
git clone https://github.com/Aamantamboli/Containerization.git
```

## Step 8: Change directory to season folder, build docker image & run container from that image 

```
cd containerzation/todo/
docker build -t todo .
docker run -d -p 80:80 todo
```

## Step 9: Hit Instance IP 13.201.37.252/todo/ 

![image](https://github.com/user-attachments/assets/27f8efe1-f398-46b0-8d69-78fb2d03f038)

## Step 10: Change directory to todo folder, build docker image & run container from that image

```
cd containerzation/season/
docker build -t season .
docker run -d -p 81:80 season
```

## Step 11: Hit Instance IP 13.201.37.252:81/seaosn/ 

![image](https://github.com/user-attachments/assets/7909c102-3232-4758-910f-4536bb99577c)

## Step 12: Change directory to traffic folder, build docker image & run container from that image 

```
cd containerzation/traffic/
docker build -t traffic .
docker run -d -p 82:80 traffic
```

## Step 13: Hit Instance IP 13.201.37.252:82/traffic/ 

![image](https://github.com/user-attachments/assets/b7817e3b-1a54-4aa3-bd3b-57cd9c11166c)
