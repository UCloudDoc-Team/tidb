

# Dashboard/监控访问

TiDB服务提供 PingCAP 原生 Dashboard/Grafana 等组件访问

TiDB提供代理入口节点，用户需自行配置外网代理服务访问监控组件，配置外网代理时需注意不要开放不必要的端口，避免网络安全事故。

## 代理节点

TiDB服务集群提供两个Proxy节点，用以代理Dashboard/Grafana服务

您可以通过‘详情’页中的节点列表中选择‘PROXY’查询到当前节点代理地址

![](https://tidb-doc.cn-bj.ufileos.com/utidb/proxy_list.png)

## 配置访问代理

您首先需要创建一台与TiDB集群同VPC下的，带外网配置的云主机，然后按以下步骤配置代理服务

提示：***不要开不必要的端口， 建议云主机防火墙设置只开放特定来源IP可以访问***

1. 安装 nginx 服务
```
yum install nginx
```

2. 修改nginx.conf

vi /etc/nginx/nginx.conf
```
    # prometheus proxy
    upstream prometheus_server {
        server 10.9.163.206:9090; # 使用详情中PROXY prometheus 地址
        server 10.9.174.142:9090; # 使用详情中PROXY prometheus 地址
    }
    server {
        listen 9090; # 端口自定，注意防火墙开放端口
        location / {
            proxy_pass http://prometheus_server/;
        }
    }

    # grafana proxy
    upstream grafana_server {
        server 10.9.163.206:3000; # 使用详情中PROXY grafana 地址
        server 10.9.174.142:3000; # 使用详情中PROXY grafana 地址
    }
    server {
        listen 3000; # 端口自定，注意防火墙开放端口
        location / {
            proxy_set_header Host $http_host;
            proxy_pass http://grafana_server/;
        }
    }

    # dashboard proxy
    upstream dashboard_server {
        server 10.9.163.206:2379; # 使用详情中PROXY dashboard 地址
        server 10.9.174.142:2379; # 使用详情中PROXY dashboard 地址
    }
    server {
        listen 2379; # 端口自定，注意防火墙开放端口
        location / {
            proxy_pass http://dashboard_server/;
        }
    }
```

3. 启动nginx服务
```
systemctl start nginx
```

## 访问
根据您配置的代理端口，在浏览器中访问对应服务

访问 Dashboard和Grafana时需要root账户登录认证

dashboard
![](https://tidb-doc.cn-bj.ufileos.com/utidb/dashboard-login.png)

grafana  
![](https://tidb-doc.cn-bj.ufileos.com/utidb/grafana-login.png)