## PyTorch语义分割开源库semseg

原创： CV君 [我爱计算机视觉](javascript:void(0);) *昨天*

点击我爱计算机视觉标星，更快获取CVML新技术

------



今天跟大家介绍一款新出的基于PyTorch的语义分割开源库semseg：

https://github.com/hszhao/semseg



其开发者为香港中文大学的博士生Hengshuang Zhao。

https://hszhao.github.io/



**介绍**



semseg用PyTorch实现的语义分割/场景解析开源库。 它可以方便帮助开发者用于各种语义分割数据集的训练和测试。

该库主要使用ResNet50 / 101/152作为主干网，也可以很容易地改成其他分类网络结构。

目前已经实现了包括PSPNet和PSANet在内的网络，其在2016年ImageNet场景解析挑战赛@ ECCV16，LSUN语义分割挑战赛2017 @ CVPR17和WAD可驾驶区域分割挑战赛2018 @ CVPR18中排名第一。 示例实验数据集包括主流的ADE20K，PASCAL VOC 2012和Cityscapes。



ps. 该库开发者即PSPNet和PSANet算法的一作。





![img](https://mmbiz.qpic.cn/mmbiz_png/BJbRvwibeSTvzlRXbUpmcpFlGV88WjGPfTr1RvuoYmE7SmgfHEcd4n5loQEiaORKGxbbsmaEcqzlMP8tpLGpCo1A/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



**亮点**



\1. 同时支持多线程训练与多进程训练，并且后者非常快（该库比较重视训练）。

\2. 重新实现的算法取得更好的结果，而且代码结构清晰（说明代码质量高）。

\3. 所有初始化模型、训练得到的模型和预测的结果都能够下载（https://drive.google.com/open?id=15wx9vOM0euyizq-M1uINgN0_wjVRf9J3），方便开发者直接使用或者研究比较。



作者推荐的软硬件环境：

![img](https://mmbiz.qpic.cn/mmbiz_png/BJbRvwibeSTvzlRXbUpmcpFlGV88WjGPfLqPFQsPp6SsVQ6vTSWPtkiagHM0Qamic82BtLE1G3roD1YZGnFQEZaBA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

（要4到8块显卡，看来没有多卡，语义分割是玩不起了～）



**训练简单**



该库的训练非常简单，简单配置后只需要一条命令

- 

```
sh tool/train.sh ade20k pspnet50
```



**测试简单**



简单配置数据集和模型路径后，也只需要一条命令：

- 

```
sh tool/test.sh ade20k pspnet50
```




在单幅图像上测试也很简单，示例：

- 

```
PYTHONPATH=./ python tool/demo.py --config=config/ade20k/ade20k_pspnet50.yaml --image=figure/demo/ADE_val_00001515.jpg TEST.scales '[1.0]'
```



### Performance

在三个数据集上的结果如下：



![img](https://mmbiz.qpic.cn/mmbiz_png/BJbRvwibeSTvzlRXbUpmcpFlGV88WjGPfGG5WtFT4LAzDfgWticAxfnhBpI30tbiboGtGY4LiaXaKxyokyp7kOoZLQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



![img](https://mmbiz.qpic.cn/mmbiz_png/BJbRvwibeSTvzlRXbUpmcpFlGV88WjGPfuWdibsIOgRWOO5krH2ZBFYhKTcWactnswA9jVBZhZuUtfs4Hcksx0GQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



![img](https://mmbiz.qpic.cn/mmbiz_png/BJbRvwibeSTvzlRXbUpmcpFlGV88WjGPfThdboPkJKctIna94mLHIDFoGEtZF8CjH0AMmZ2Ev9IJ3416D19zFQw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



注意，作者列出的时间是在8个GeForce RTX 2080 Ti上训练得到的。



感谢作者的分享～



再发一遍地址：

https://github.com/hszhao/semseg



**图像分割专业交流群**



关注最新语义分割、实例分割等技术，欢迎加入52CV-图像分割专业交流群，扫码添加CV君拉你入群（如果你已经加CV君为好友，请直接私信就好了，**不必重复添加**），



**（请务必注明:分割）：**

**![img](https://mmbiz.qpic.cn/mmbiz_png/BJbRvwibeSTs1Ke4WXicIqN7QibMXL527MCvicgajlnePVw1mnomoLqFqL0WLf7UUpSkVGj2E1GGe83e8ZmY0G42jw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)**

喜欢在QQ交流的童鞋可以加52CV官方QQ群：702781905。

（不会时时在线，如果没能及时通过还请见谅）



------





![img](https://mmbiz.qpic.cn/mmbiz_png/BJbRvwibeSTvVOnJBvePcP1qFUSWpyvrjpYAWNIZTZzUA7Zq4VPlReicJWcIeozxic5VhHlwNQNAFXmKQBtKf5xAQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

长按关注我爱计算机视觉









微信扫一扫
关注该公众号