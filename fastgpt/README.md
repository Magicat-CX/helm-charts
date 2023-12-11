# FastGPT-Chart

Helm 部署FastGPT和所需的依赖。

默认部署服务：

    - postgre(单节点)
    - mongo(单节点)
    - oneapi
    - m3e-large  `感谢 “睡大觉” 同学提供的镜像` 

# Values

| 参数 | 描述 | 默认值 |
| --- | --- | --- |
| storageClass | 存储类的名称 | local-path |
| postgres.image | Postgres数据库的镜像地址 | registry.cn-hangzhou.aliyuncs.com/fastgpt/pgvector:v0.5.0 |
| postgres.user | Postgres数据库的用户名 | postgres |
| postgres.password | Postgres数据库的密码 | postgres |
| postgres.db | Postgres数据库的名称 | postgres |
| postgres.storage | Postgres数据库的存储空间 | 20Gi |
| postgres.service.nodePort.enable | 是否启用Postgres数据库的NodePort服务 | false |
| mongo.image | Mongo数据库的镜像地址 | registry.cn-hangzhou.aliyuncs.com/fastgpt/mongo:5.0.18 |
| mongo.user | Mongo数据库的用户名 | mongo |
| mongo.password | Mongo数据库的密码 | password |
| mongo.db | Mongo数据库的名称 | fastgpt |
| mongo.storage | Mongo数据库的存储空间 | 20Gi |
| mongo.service.nodePort.enable | 是否启用Mongo数据库的NodePort服务 | false |
| oneapi.enable | 是否启用OneAPI服务 | true |
| oneapi.image | OneAPI服务的镜像地址 | docker.io/justsong/one-api:v0.5.8 |
| oneapi.tz | OneAPI服务的时区设置 | Asia/Shanghai |
| oneapi.storage | OneAPI服务的存储空间 | 20Gi |
| oneapi.service.nodePort.enable | 是否启用OneAPI服务的NodePort服务 | true |
| oneapi.ingress.enable | 是否启用OneAPI服务的Ingress服务 | false |
| oneapi.ingress.domain | OneAPI服务的Ingress域名 | oneapi.example.com |
| m3e.enable | 是否启用M3E服务 | true |
| m3e.image | M3E服务的镜像地址 | registry.cn-hangzhou.aliyuncs.com/fastgpt_docker/m3e-large-api:latest |
| m3e.sk | M3E服务的密钥 | sk-XZLDUNTxVqHTjvM6eqHsHgy9maqCLSR4xHacEuutgzNnUdHL |
| m3e.service.nodePort.enable | 是否启用M3E服务的NodePort服务 | false |
| fastgpt.image | FastGPT服务的镜像地址 | registry.cn-hangzhou.aliyuncs.com/fastgpt/fastgpt:v4.6.3 |
| fastgpt.rootPsw | FastGPT服务的控制台root登录密码 | P@ssw0rd |
| fastgpt.openaiBaseUrl | FastGPT服务的OpenAI API地址 | '' |
| fastgpt.chatApiKey | FastGPT服务的OneAPI生成的key | '' |
| fastgpt.dbMaxLink | FastGPT服务的数据库最大连接数 | '5' |
| fastgpt.tokenKey | FastGPT服务的token密钥 | 7krX4vnVUcVe6PuP |
| fastgpt.rootKey | FastGPT服务的root密钥 | MMShc8r6LY9Yn8Z7 |
| fastgpt.fileTokenKey | FastGPT服务的文件token密钥 | Nab5HpnY6R4DWcs6 |
| fastgpt.service.nodePort.enable | 是否启用FastGPT服务的NodePort服务 | true |
| fastgpt.ingress.enable | 是否启用FastGPT服务的Ingress服务 | false |
| fastgpt.ingress.domain | FastGPT服务的Ingress域名 | fastgpt.example.com |
| fastgpt.config | FastGPT服务的其他配置项 | [见官方文档](https://doc.fastgpt.in/docs/development/configuration/) |
