# 公有云端USDP集群资源节点管理

通过本章节介绍，即可对USDP集群的所有公有云端集群资源实现节点资源管理操作，如添加/删除节点、快捷登陆节点、给节点绑定公网EIP、给节点绑定防火墙、关机/启动节点等。

- [添加节点资源](/USDP/operate/node/cloud_node?id=添加节点资源)
- [删除节点资源](/USDP/operate/node/cloud_node?id=删除节点资源)
- [绑定EIP、设置防火墙](/USDP/operate/node/cloud_node?id=绑定EIP、设置防火墙)
- [资源节点登录](/USDP/operate/node/cloud_node?id=资源节点登录)
- [节点基本操作](/USDP/operate/node/cloud_node?id=节点基本操作)

## 添加节点资源

点击 <kbd>添加节点</kbd> 按钮后弹窗如下，设置“节点角色”，“机型”、“节点个数”，此处支持批量创建同角色、同机型的多个节点；

待您输入新创建节点的初始密码后，点击 <kbd>确定</kbd> 按钮，等待节点创建。如下图所示：

![](../../images/operate/node/cloud_node/添加节点.png)

## 删除节点资源

在Core节点、Task节点条目右侧点击 <kbd>…</kbd> 按钮，在弹出的菜单中，点击 <kbd>删除</kbd> 按钮。

?>注意：</br>删除节点前，需要您先在“USDP管理控制台”中，对相应节点上的服务进行下线操作，待下线完成之后，才能在“节点管理”页面中完成删除节点。</br>目前暂不支持用户主动对主节点（master）、监控节点（monitor）的删除操作。

!>不允许对Master、Monitor节点执行删除操作，且Core节点至少保留3台。

## 绑定EIP、设置防火墙

1）首先需要在基础网络产品页面申请一个EIP，可参考[EIP操作指南](https://docs.ucloud.cn/unet/eip/guide)
![](../../images/operate/node/cloud_node/申请EIP.png)

2）回到到智能大数据平台USDP的节点管理进行绑定EIP操作。

![](../../images/operate/node/cloud_node/绑定EIP.png)

?>仅允许给Master节点、Monitor节点绑定EIP。

!>提示：</br>为避免受到来自互联网的入侵和攻击，事先配置好防火墙策略[防火墙操作指南](https://docs.ucloud.cn/unet/firewall/guide)，再执行给资源节点“绑定EIP”的操作。

## 资源节点登录

**方式一：** 通过控制台登录。

![](../../images/operate/node/cloud_node/控制台节点SSH登陆.png)

!>如果节点机型是物理机，可能由于不同服务器厂商的标准不同，造成暂不能通过控制台登录节点的情况，此时，可尝试其他登陆方式。

**方式二：** 给集群Master节点绑定外网EIP，您即可从本地通过外网ssh连接登录节点。

**方式三：** 通过云主机（UHost）内网ssh进行登录。例如您可在您的云主机上通过“ssh root@10.13.186.23 -p22”进行登录。 登录密码为集群创建时设置的密码。

?>当需要通过云主机ssh登陆大数据集群节点时，请留意云主机与大数据集群的内网是否可达，如在同一VPC中，或不同VPC设置了VPC互通。

## 节点基本操作

支持对指定的节点进行 <kbd>关机</kbd> 、<kbd>开机</kbd> 、<kbd>重启</kbd> 、<kbd>删除</kbd> 等操作。请点击节点列表右侧具体节点操作栏中相关按钮，及 <kbd>...</kbd> 按钮展开操作菜单。

!>删除节点之前需要到[USDP控制台“节点管理”页面](/USDP/operate/node/usdp_node)下线该节点上部署的服务，否则会删除失败。

