# 2022-summer-tutorial-backend
精弘网络2022暑期授课后端

课程表的后端实现

## 前提准备

### Go项目
1. go mod

```bash
go mod init class_schedule
go mod tidy
```

`GOPATH` 是 Golang 工作区目录的一个全局变量.

在Golang1.11版本之前, 没有可用的包管理器(即类似 python 的 pip, node.js 的 npm, yarn)

而在1.11之后出现了 go mod 用以管理, 不需要配置 GOPATH


2. 项目架构
  
**MVC架构**

Model-View-Controller

Model 数据库 MySQL Gorm

Controller Api Gin

View 表现层(前端)


### MySQL

SQL: Structured Query Language 结构化查询语言

MySQL: 使用 SQL 语言的一种 **关系性数据库**

**表**

`mycli` 一个 Python 写的 MySQL 命令行客户端
```bash
sudo mycli -uroot
```

```sql
create database class_schedule;
create user 'class_schedule_admin'@'localhost' identified by 'password';
grant all on class_schedule.* to 'class_schedule_admin'@'localhost';
```

创建数据库, 用户, 授权

## 初始化

### Viper 读入 Config

1. yaml 文件
2. viper 配置&绑定


### 数据库初始化
1. dsn链接数据库
2. Models设计
> **关系**
> 1. Belongs to 
> 2. Has one
> 3. Has many
> 4. Many to Many

### 路由初始化
cors 中间件
> **同源策略** Same Origin Policy
>
> 只能同源(scheme, domain, port相同) 请求
> 
> **CORS** Cross-Origin Resource Sharing 跨域资源共享
> 
> 前后端分离项目端口必然不同, 因此需要使用跨域资源共享.
