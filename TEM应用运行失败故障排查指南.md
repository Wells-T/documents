当TEM应用处于运行失败状态时，说明至少有一个实例不处于Running状态，本文将列举几个常见的实例错误状态，并指导如何进行对应的故障排查

## 实例错误状态

### CrashLoopBackOff

#### 状态说明
实例中应用程序的运行有问题，容器启动/运行失败。

#### 解决方案
查看实例的日志，通过日志内容排查问题。

![](https://qcloudimg.tencent-cloud.cn/raw/34a8a91db77244e0262d162a9040f36e.png)

### Error

#### 状态说明
与CrashLoopBackOff类似，说明实例中应用程序的运行有问题，容器启动/运行失败。

#### 解决方案
查看实例的日志，通过日志内容排查问题。

![](https://qcloudimg.tencent-cloud.cn/raw/6bd7c78394aa9e5062dceb1607691689.png)

### Running Unhealthy：Readiness probe failed

#### 状态说明
应用配置的就绪健康检查失败。

#### 解决方案
请在应用部署页面>健康检查中，检查应用的就绪检查配置是否正确。

![enter image description here](/download/attachments/1556177689/image-1647486713173.png?version=1&modificationDate=1647486713487&api=v2)
![](https://qcloudimg.tencent-cloud.cn/raw/018bdf59af4b99ffabe6401025e50eb8.png)
### Running Unhealthy：Liveness probe failed

#### 状态说明
应用配置的存活健康检查失败。

#### 解决方案
请在应用部署页面>健康检查中，检查应用的存活检查配置是否正确。

![](https://qcloudimg.tencent-cloud.cn/raw/a81b55dd4011438d0d62b23af724cadb.png)

### Running Unhealthy：Readiness check failed according to l4 listener: xxx of CLB xxx. Service: xxx

#### 状态说明
应用配置的访问配置无法连通。

#### 解决方案
请在应用详情页面>基本信息>访问配置中，检查应用配置的访问配置的端口和协议是否正确。

![](https://qcloudimg.tencent-cloud.cn/raw/f252214d3165f95a681a4fec0005d0d3.jpg)

### PostStartHookError

#### 状态说明
为应用配置的PostStart运行失败。

#### 解决方案
请在应用部署页面>启停管理中，检查应用配置的PostStart是否能正常运行。

![](https://qcloudimg.tencent-cloud.cn/raw/58c5da29010db07ba7e5ed2d499bd454.png)

### ContainerCreating

#### 状态说明
实例容器创建失败。

#### 解决方案
请在应用部署页面>持久化存储中，检查应用是否挂载了不存在的数据卷。

![](https://qcloudimg.tencent-cloud.cn/raw/8e86cf9d723b93cb8413e690de75430a.png)

### CreateContainerConfigError

#### 状态说明
实例容器配置失败。

#### 解决方案
请在应用部署页面>环境变量中，检查应用是否引用了不存在的配置。

![](https://qcloudimg.tencent-cloud.cn/raw/7c41d941a559509f4f895e121434ea3d.png)

#### 状态说明
实例镜像拉取失败。

#### 解决方案
前往 [TCR控制台](https://console.cloud.tencent.com/tcr/repository?rid=1) 检查应用使用的镜像是否存在或被误删除。
