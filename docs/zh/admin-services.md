# 服务启停

使用由Websoft9提供的Redmine部署方案，可能需要用到的服务如下：

### Redmine

```shell
sudo systemctl start redmine 
sudo systemctl stop redmine
sudo systemctl restart redmine 
sudo systemctl status redmine
```

### Nginx

```shell
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl status nginx
```

### MySQL

```shell
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
sudo systemctl status mysql
```

### Docker

```shell
sudo systemctl start docker
sudo systemctl restart docker
sudo systemctl stop docker
sudo systemctl status docker
```