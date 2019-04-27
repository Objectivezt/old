# ECS  配置二级域名

## 阿里云配置

    1、进入阿里云上的地址 `https://dns.console.aliyun.com/#/dns/domainList` 云解析DNS下。
    2、选择域名如列表 objectivezt.com，操作有一个【解析设置】
    3、添加记录、设置主机记录的二级域名如   `aaa`

## nginx conf

    确保你的nginx.conf里面是
    include /www/server/panel/vhost/nginx/*.conf;

    端口开放一个如8000；

    设置 include加两个文件：

    ```aaa_base.conf
    server {
        listen 8000;
        server_name aaa.objectivezt.com;
        root  /your/path/;
        index index.html;
    }
    ```

    ```aaa.conf
    server {
        listen 80;
        server_name aaa.objectivezt.com;
        location / {
                proxy_redirect off;
                proxy_set_header Host $host;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
                proxy_pass http://127.0.0.1:8000;//改为你的ip
        }
    }
    ```