# **Reverse Proxy configuration for LMS Application**

![image](https://github.com/arjunedify/Arjun/assets/130965749/ac1edcb5-8742-481f-b346-7a65821072a5)

## **Frontend Backend Integration -**

In nginx add private ip of server/vm

```
sudo vi /etc/nginx/sites-enabled/default
```
```
location /api {

proxy\_pass http://172.31.39.233:8080;

}
```
```
cd lms/webapp
```

In .env file add public ip (but don't add 8080 in security group, as proxy takes care of routing)
```
 vi .env
```
#VITE\_API\_URL=http://13.233.238.12/api

VITE\_API\_URL=http://frontend-public-ip/api
