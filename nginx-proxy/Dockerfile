# 基础镜像
FROM nginx:alpine

# Nginx目录
ENV NGINX_PATH=/etc/nginx

# 删除nginx目录原有配置文件
RUN rm -rf ${NGINX_PATH}/nginx.conf
RUN rm -rf ${NGINX_PATH}/conf.d

# 复制新的配置文件
COPY ./nginx.conf ${NGINX_PATH}/

# 复制证书
COPY ./cert/ ${NGINX_PATH}/cert/

# 暴露端口
EXPOSE 80
EXPOSE 443

# 可以通过 docker build -t journey-nginx:dev . 来创建本地镜像
# 通过 docker run -d -p 80:80 -p 443:443 --rm --name journey-nginx journey-nginx:dev 来运行此镜像
# 通过 docker exec -it fdba3 sh 进入容器内部
# 通过 docker logs 1655aa70924e 来查看nginx日志