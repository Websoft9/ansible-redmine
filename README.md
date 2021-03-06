# Redmine 自动化安装与部署

本项目是由 [Websoft9](https://www.websoft9.com) 研发的 [Redmine](https://www.redmine.org/) 自动化安装程序，开发语言是 Ansible。使用本项目，只需要用户在 Linux 上运行一条命令，即可自动化安装 Redmine，让原本复杂的安装过程变得没有任何技术门槛。  

本项目是开源项目，采用 LGPL3.0 开源协议。

## 配置要求

安装本项目，确保符合如下的条件：

| 条件       | 详情       | 备注  |
| ------------ | ------------ | ----- |
| 操作系统       | Ubuntu18.x, CentOS7.x       |  必选  |
| 公有云| AWS, Azure, 阿里云, 华为云, 腾讯云 | 可选 |
| 私有云|  KVM, VMware, VirtualBox, OpenStack | 可选 |
| 服务器配置 | 最低1核2G，安装时所需的带宽不低于10M |  建议采用按量100M带宽 |

更多技术要求参考官方文档：[《Requirements》](https://www.redmine.org/projects/redmine/wiki/RedmineInstall#Requirements)

## 组件

包含的核心组件为：Redmine,Ruby,Nginx,MySQL等

更多请见：[参数表](/docs/zh/stack-components.md)

## 本项目安装的是 Redmine 最新版吗？

本项目采用官方提供的源码下载安装，通过修改[`redmine_download_url`](/roles/redmine/defaults/main.yaml)字段来维护所下载的地址。  

如何获取下载地址？官方[下载页面](https://www.redmine.org/projects/redmine/wiki/Download)  

我们会定期检查安装脚本 URL 地址的准确性，以保证用户可以顺利安装。

## 安装指南


以 root 用户登录 Linux，运行下面的**一键自动化安装命令**即可启动自动化部署。若没有 root 用户，请以其他用户登录 Linux 后运行 `sudo su -` 命令提升为 root 权限，然后再运行下面的脚本。

```
wget -N https://raw.githubusercontent.com/Websoft9/ansible-linux/main/scripts/install.sh; bash install.sh -r redmine
```

脚本后启动，就开始了自动化安装，必要时需要用户做出交互式选择，然后耐心等待直至安装成功。

**安装中的注意事项：**  

1. 操作不慎或网络发生变化，可能会导致SSH连接被中断，安装就会失败，此时请重新安装
2. 安装缓慢、停滞不前或无故中断，主要是网络不通（或网速太慢）导致的下载问题，此时请重新安装

多种原因导致无法顺利安装，请使用我们在公有云上发布的 [Redmine 镜像](https://apps.websoft9.com/redmine) 的部署方式

## License

[LGPL-3.0](/License.md), Additional Terms: It is not allowed to publish free or paid image based on this repository in any Cloud platform's Marketplace.
Copyright (c) 2016-present, Websoft9

## 文档

文档链接：https://support.websoft9.com/docs/redmine/zh

## FAQ

- 命令脚本部署与镜像部署有什么区别？请参考[镜像部署-vs-脚本部署](https://support.websoft9.com/docs/faq/zh/bz-product.html#镜像部署-vs-脚本部署)
- 本项目支持在 Ansible Tower 上运行吗？支持

## To do

* 默认预装redmine重要组件
