---
# Zabbix 和 Grafana 监控系统配置

## 项目描述
项目旨在为一个大型系统配置监控和报警功能，使用 **Zabbix** 作为监控工具，通过 **Grafana** 展示监控数据，提供可视化的监控和报警功能。

## 技术栈
- **监控工具**: Zabbix
- **数据可视化**: Grafana
- **服务器环境**: Linux（CentOS）
## 功能特性
- 实时监控系统性能指标（CPU、内存、磁盘、网络等）。
- 自定义报警规则，支持邮件、Slack 等通知方式。
- 通过 Grafana 实现监控数据的可视化展示。
- 支持多主机、多指标的集中监控。

---

## 安装与配置

### 1. 环境准备
- 确保有一台 Linux 服务器（推荐 Ubuntu 20.04 或 CentOS 7）。
- 安装 Docker 和 Docker Compose（可选，用于快速部署）。

### 2. 安装 Zabbix
1. 下载并安装 Zabbix Server：
   wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-1+ubuntu20.04_all.deb
   sudo dpkg -i zabbix-release_6.0-1+ubuntu20.04_all.deb
   sudo apt update
   sudo apt install zabbix-server-mysql zabbix-frontend-php zabbix-agent

2. 配置 Zabbix 数据库和 Web 界面。

### 3. 安装 Grafana
1. 下载并安装 Grafana：
   sudo apt-get install -y apt-transport-https
   sudo apt-get install -y software-properties-common wget
   wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
   echo "deb https://packages.grafana.com/oss/deb stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
   sudo apt-get update
   sudo apt-get install grafana

2. 启动 Grafana 服务：

   sudo systemctl start grafana-server
   sudo systemctl enable grafana-server


### 4. 配置 Zabbix 数据源
1. 登录 Grafana，进入 **Configuration > Data Sources**。
2. 添加 Zabbix 数据源，填写 Zabbix API 地址和认证信息。

### 5. 创建 Grafana 仪表盘
1. 在 Grafana 中创建新的仪表盘。
2. 添加面板，选择 Zabbix 数据源，配置监控指标。

---

## 使用方法
1. 登录 Zabbix，添加需要监控的主机和监控项。
2. 在 Grafana 中创建仪表盘，实时查看监控数据。
3. 配置报警规则，确保在系统异常时及时收到通知。

---


---


---

## 联系方式
如有问题或建议，请联系：
- 邮箱：1182297787@qq.com
