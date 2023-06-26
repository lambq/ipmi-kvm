# ipmi-kvm

#### 介绍
IPMI-KVM-Server 是一个基于 python 的服务器，旨在通过浏览器集中提供,这意味着管理员计算机上不需要安装 Java。

#### 软件架构

1.  Python3
2.  pip
3.  ipmi
4.  docker
5.  novnc

#### 安装教程

> 下载代码仓库
```shell
git clone https://gitee.com/cbter/ipmi-kvm.git
```

```shell
cd ipmi-kvm
```

> 在 .env 中，按照docker环境变量进行设置。
```shell
vi .env
```

> 运行docker容器
```shell
docker-compose up -d
```

#### 使用说明

> 可以使用nginx 端口映射,解析域名就行。

### docker环境变量
    
| 名称                       | 说明                                                                                                                                                         | 示例                                   |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- |
| `LOGLEVEL`                 | 要使用的日志级别（`DEBUG`、`INFO`、`WARNING`（默认值）、`ERROR`、`CRITICAL`之一                                                                                | `INFO`                                    |
| `KVM_CONFIG_PATH`          | ipmi KVM的配置文件的绝对路径                                                                                                                                           | `/nojava-ipmi-kvmrc.yaml`            |
| `WEBAPP_BASE`              | 发布服务的最终地址                                                                                                                                                     | `https://ipmi-kvm.com` |
| `WEBAPP_PORT`              | 要侦听的端口                                                                                                                                                          | `8080`                                    |
| `EXTERNAL_WEB_DNS`         | 应设置为docker主机的外部地址                                                                                                                                            | `ipmi-kvm.com`         |
| `WEB_PORT_START`           | 第一个分配给docker集装箱的端口                                                                                                                                             | `8801`                                    |
| `WEB_PORT_END`             | docker分配最后一个端口                                                                                                                                                 | `8900`                                    |

