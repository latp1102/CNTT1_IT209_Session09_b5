# Bài 5: Docker Compose

## 1. Tạo Docker Compose

File `docker-compose.yml`:

```yaml
services:
  web:
    image: nginx:alpine
    ports:
      - "8082:80"
th_phong@DESKTOP-BAIK6RQ:/mnt/d/IT209_Devops_Funmentals/Session09/b5$ docker compose version
Docker Compose version v5.5.0
th_phong@DESKTOP-BAIK6RQ:/mnt/d/IT209_Devops_Funmentals/Session09/b5$ docker compose up -d
WARN[0000] Found orphan containers (redis-lab) for this project. If you removed or renamed this service in your compose file, you can run this command with the --remove-orphans flag to clean it up.
[+] up 1/1
 ✔ Container b5-web-1 Started                                                                      0.4s
th_phong@DESKTOP-BAIK6RQ:/mnt/d/IT209_Devops_Funmentals/Session09/b5$ docker compose ps
NAME        IMAGE            COMMAND                  SERVICE   CREATED         STATUS         PORTS
b5-web-1    nginx:alpine     "/docker-entrypoint.…"   web       5 seconds ago   Up 4 seconds   0.0.0.0:8082->80/tcp, [::]:8082->80/tcp
redis-lab   redis:7-alpine   "docker-entrypoint.s…"   redis     2 weeks ago     Up 8 minutes   0.0.0.0:6379->6379/tcp, [::]:6379->6379/tcp
th_phong@DESKTOP-BAIK6RQ:/mnt/d/IT209_Devops_Funmentals/Session09/b5$ curl http://localhost:8082
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, nginx is successfully installed and working.
Further configuration is required for the web server, reverse proxy,
API gateway, load balancer, content cache, or other features.</p>

<p>For online documentation and support please refer to
<a href="https://nginx.org/">nginx.org</a>.<br/>
To engage with the community please visit
<a href="https://community.nginx.org/">community.nginx.org</a>.<br/>
For enterprise grade support, professional services, additional
security features and capabilities please refer to
<a href="https://f5.com/nginx">f5.com/nginx</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
