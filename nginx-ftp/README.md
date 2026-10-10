# nginx-ftp

基于 Alpine 的 Nginx + FTP + SSH 文件服务容器。

## 构建

```bash
docker build --build-arg ADMIN_PASSWORD=你的密码 -t nginx-ftp .
```

## 运行

```bash
docker run -d \
  --name nginx-ftp \
  -p 80:80 \
  -p 21:21 \
  -p 22:22 \
  -p 10000-10010:10000-10010 \
  -p 21100-21110:21100-21110 \
  -v /your/data:/data \
  nginx-ftp
```

## 环境变量

| 变量           | 说明                       | 默认值 |
| -------------- | -------------------------- | ------ |
| ADMIN_USER     | FTP/SSH 用户名             | admin  |
| ADMIN_PASSWORD | FTP/SSH 密码（构建时指定） | 无     |

docker run -d --name nginx-ftp -p 80:80 -p 21:21 -p 10000-10010:10000-10010 -p 21100-21110:21100-21110  -v /home/testadmin/data/docs:/data docs
