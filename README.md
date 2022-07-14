# Scaffold-gin

[![GitHub](https://img.shields.io/github/license/mjiee/gr-gin)](https://github.com/mjiee/gr-gin/blob/master/LICENSE)
[![GitHub go.mod Go version](https://img.shields.io/github/go-mod/go-version/mjiee/gr-gin)](https://go.dev/)

Scaffold-gin是一个基于go语言gin框架的web案例，专注于前后端分离的业务场景。目的是为初学者提供一个清晰的web项目主线逻辑，对基础功能实现封装。

主要使用的技术栈：

* web框架: [gin](https://github.com/gin-gonic/gin)
* 命令行: [cobra](https://github.com/spf13/cobra)
* 配置管理: [viper](https://github.com/spf13/viper)
* 日志库: [zap](https://github.com/uber-go/zap)
* 依赖注入: [wire](https://github.com/google/wire)
* orm库: [gorm](https://github.com/go-gorm/gorm)
* redis库: [go-redis](https://github.com/go-redis/redis)
* jwt库: [golang-jwt](https://github.com/golang-jwt/jwt)
* 文档: [swag](https://github.com/swaggo/swag)

## Deployment

环境依赖: mysql > 8.0, redis > 6.0。

快速部署项目:

```bash
# 获取项目
git clone https://github.com/mjiee/scaffold-gin.git

# 编译项目
go build

# 修改配置文件
vi ./conf/default.yaml

# 初始化项目
./scaffold-gin check -c ./conf/default.yaml
./scaffold-gin init -c ./conf/default.yaml

# 运行项目
./scaffold-gin run -c ./conf/default.yaml
```

## Documentation

其他服务:

```bash
# swagger文档生成
swag init --parseDependency --output ./app/docs
go build -tags "dev"
# api访问地址: /api/v1/swagger/index.html

# 依赖代码生成
wire
```

自定义错误码:

```bash
10001  # 参数验证相关错误    
20001  # token认证相关错误   
30001  # 业务逻辑相关错误
```
