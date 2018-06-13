# docker-php

## 1. php.index
```
<?php
/**
 * Created by IntelliJ IDEA.
 * User: chaolinding
 * Date: 2018/6/13
 * Time: 下午4:21
 */
echo "hello php in docker!";

?>
```

## 2. Dockerfile
```
# 从官方PHP镜像构建
FROM       php

# 将index.php复制到容器内的/var/www目录下
ADD        index.php /var/www/

# 对外暴露8080端口
EXPOSE     8080

# 设置容器默认工作目录为/var/www
WORKDIR    /var/www/

# 容器运行后默认执行的指令
ENTRYPOINT ["php", "-S", "0.0.0.0:8080"]
```

## 3. 生成镜像
- docker build -t phphelloworld .

## 4. 运行
-  docker run --name phptestcontainer -p 44444:8080 phphelloworld