---
title: jupyter through nginx
categories:
  - pytorch
tags:
  - pytorch
---


# Install jupyter

```sh
conda install jupyter

jupyter notebook --ip=0.0.0.0
```

## Nginx conifg
```nginx

server {                                                                                  
    listen 80;
    server_name xxx.com;  # 替换为你的域名或IP地址
    location / {
        proxy_pass http://1.1.1.1:8888;  # 
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_redirect off;
    }
}
```