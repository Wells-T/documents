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

![enter image description here](/download/attachments/1556177689/image-1647486681390.png?version=1&modificationDate=1647486681720&api=v2)

### Running Unhealthy：Readiness probe failed

#### 状态说明
应用配置的就绪健康检查失败。

#### 解决方案
检查应用的就绪检查配置是否正确。

![enter image description here](/download/attachments/1556177689/image-1647486713173.png?version=1&modificationDate=1647486713487&api=v2)

### Running Unhealthy：Liveness probe failed

#### 状态说明
应用配置的存活健康检查失败。

#### 解决方案
检查应用的存活检查配置是否正确。

![enter image description here](/download/attachments/1556177689/image-1647486741640.png?version=1&modificationDate=1647486742010&api=v2)

### Running Unhealthy：Readiness check failed according to l4 listener: xxx of CLB xxx. Service: xxx

#### 状态说明
应用配置的访问配置无法连通。

#### 解决方案
检查应用配置的访问配置的端口和协议是否正确。

![enter image description here](/download/attachments/1556177689/image-1647486774678.png?version=1&modificationDate=1647486775808&api=v2)

### PostStartHookError

#### 状态说明
为应用配置的PostStart运行失败。

#### 解决方案
检查应用配置的PostStart是否能正常运行。

![enter image description here](/download/attachments/1556177689/image-1647486800668.png?version=1&modificationDate=1647486800983&api=v2)

### ContainerCreating

#### 状态说明
实例容器创建失败。

#### 解决方案
检查应用是否挂载了不存在的数据卷。

![enter image description here](/download/attachments/1556177689/image-1647486831292.png?version=1&modificationDate=1647486831671&api=v2)

### CreateContainerConfigError

#### 状态说明
实例容器配置失败。

#### 解决方案
检查应用是否引用了不存在的配置。

![enter image description here](/download/attachments/1556177689/image-1647486851430.png?version=1&modificationDate=1647486851748&api=v2)

### ImagePullBackOff

#### 状态说明
实例镜像拉取失败。

#### 解决方案
前往 [TCR](https://console.cloud.tencent.com/tcr/repository?rid=1) 检查应用使用的镜像是否存在或被误删除。
