### 一. 大模型部署
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705281184614-28217bc8-fd0c-4bce-b1f5-4abc2c9e809d.png#averageHue=%23d1daee&clientId=u81782f88-4168-4&from=paste&height=1026&id=u90cdffde&originHeight=1539&originWidth=1720&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=2143849&status=done&style=none&taskId=ua8334a4b-47df-476d-bb60-843a252176f&title=&width=1146.6666666666667)
### 二. LMDeploy 简介
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705281204644-6ebccb7e-f7cd-4112-beab-c49412ef8d35.png#averageHue=%23c5d2e7&clientId=u81782f88-4168-4&from=paste&height=1030&id=ueae5970c&originHeight=1545&originWidth=1719&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=2210989&status=done&style=none&taskId=u2ad8f66a-f276-4a7c-aaa3-524f2de3db3&title=&width=1146)
### 三. 核心功能—量化
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705281230468-bdb5ccd7-04e0-438a-87fa-182dcc275f21.png#averageHue=%23bac9e5&clientId=u81782f88-4168-4&from=paste&height=1122&id=u50065f8d&originHeight=1683&originWidth=1717&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=2650716&status=done&style=none&taskId=u4c9a6582-f6ff-483f-8011-c09dc6b137a&title=&width=1144.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705281237511-df7a8bdf-1b39-42bf-83d6-6c7fee61f1d4.png#averageHue=%23cdddee&clientId=u81782f88-4168-4&from=paste&height=521&id=uaf5f03c2&originHeight=781&originWidth=1719&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=971815&status=done&style=none&taskId=u7884a25d-f91b-493a-aee9-45724320ffd&title=&width=1146)
### 四. 核心功能—推理引擎TurboMind
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705281260360-6d4fe055-c18e-4b90-84a2-5347aadf69b2.png#averageHue=%23d0daec&clientId=u81782f88-4168-4&from=paste&height=1027&id=u10958e0b&originHeight=1540&originWidth=1720&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1741261&status=done&style=none&taskId=ued4a032e-b5d1-493e-996f-d20d00ee9d6&title=&width=1146.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705281280815-7d73ff46-42f8-47ff-8975-49824c09df7f.png#averageHue=%23c7d6ec&clientId=u81782f88-4168-4&from=paste&height=985&id=u73b3a0c6&originHeight=1477&originWidth=1714&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=2343852&status=done&style=none&taskId=u0dcc6f9a-0452-44b5-8551-f0c2fbdc4ac&title=&width=1142.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705281282472-3bc0d076-d4da-43f0-8104-bc21f63fd6db.png#averageHue=%23d1dcf0&clientId=u81782f88-4168-4&from=paste&height=535&id=u737e67f2&originHeight=802&originWidth=1726&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1043278&status=done&style=none&taskId=ud842bc1b-2288-47c9-b702-f06d324a8a4&title=&width=1150.6666666666667)
### 五. 动手实践环节—安装、部署、量化
#### TurboMind 推理+命令行本地对话
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705281308147-568b40b5-18fd-4295-b220-7202ad2c5dca.png#averageHue=%23292827&clientId=u81782f88-4168-4&from=paste&height=896&id=ue4326cc8&originHeight=1344&originWidth=1704&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=692452&status=done&style=none&taskId=u0585a183-35b1-4626-bb8d-24c1a23f3cd&title=&width=1136)
#### TurboMind推理+API服务
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705281331691-3d898969-d13c-478d-95fd-ffa1ae48f2c6.png#averageHue=%23f8f8f7&clientId=u81782f88-4168-4&from=paste&height=1299&id=u371f7c57&originHeight=1948&originWidth=1732&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=359611&status=done&style=none&taskId=u0786b16c-c801-4517-824c-8accde54b86&title=&width=1154.6666666666667)![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705281346922-24c5e034-6b3b-464a-95b7-1cb0815e3922.png#averageHue=%237f8a5c&clientId=u81782f88-4168-4&from=paste&height=913&id=u2212ac8b&originHeight=1369&originWidth=1713&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=436846&status=done&style=none&taskId=uc6e36433-ee12-454b-93b6-1d38c22d0eb&title=&width=1142)
#### TurboMind 推理作为后端，Gradio 作为前端 Demo 演示
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705283804460-9ee0f0b1-462f-4206-9290-52f0389fa3ea.png#averageHue=%23fefefe&clientId=u4a111257-cf71-4&from=paste&height=633&id=ubf3d79d0&originHeight=949&originWidth=1438&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=48745&status=done&style=none&taskId=ua6682310-62a1-446a-bbba-3b24fc04677&title=&width=958.6666666666666)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705284731150-57abe65d-89db-43cf-8376-34d6f20cb1f3.png#averageHue=%23e0f4f6&clientId=u4a111257-cf71-4&from=paste&height=519&id=u346a34a4&originHeight=973&originWidth=1507&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=177612&status=done&style=none&taskId=ud5361f13-3854-4a08-b938-28f75bb7c0f&title=&width=803.7333333333333)
#### TurboMind推理 + Python
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1705287169276-087c3548-57c7-484a-b2d2-a4ba7db77742.png#averageHue=%23222221&clientId=u4a111257-cf71-4&from=paste&height=1018&id=u26c5412f&originHeight=1908&originWidth=3840&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=534439&status=done&style=none&taskId=u0906e389-b499-45e2-8882-366118b1dd5&title=&width=2048)
#### 上述各种方法的使用场景：

- 想对外提供类似 OpenAI 那样的 HTTP 接口服务
   - 推荐使用 TurboMind推理 + API 服务。
- 想做一个演示 Demo，Gradio 无疑是比 Local Chat 更友好的。
   - 推荐使用 TurboMind 推理作为后端的Gradio进行演示。
- 想直接在自己的 Python 项目中使用大模型功能。
      - 推荐使用 TurboMind推理 + Python。
- 想在自己的其他非 Python 项目中使用大模型功能。
   - 推荐直接通过 HTTP 接口调用服务。也就是先启动一个 HTTP API 服务，然后在项目中直接调用接口。
-  C++ 项目可以直接用 TurboMind 的 C++ 接口。
#### 模型量化的最佳实践：
首先我们需要明白一点，服务部署和量化是没有直接关联的，量化的最主要目的是降低显存占用，主要包括两方面的显存：模型参数和中间过程计算结果。前者对应《3.2 W4A16 量化》，后者对应《3.1 KV Cache 量化》。
量化在降低显存的同时，一般还能带来性能的提升，因为更小精度的浮点数要比高精度的浮点数计算效率高，而整型要比浮点数高很多。
建议是：在各种配置下尝试，看效果能否满足需要。这一般需要在自己的数据集上进行测试。具体步骤如下。

- Step1：优先尝试正常（非量化）版本，评估效果。
   - 如果效果不行，需要尝试更大参数模型或者微调。
   - 如果效果可以，跳到下一步。
- Step2：尝试正常版本+KV Cache 量化，评估效果。
   - 如果效果不行，回到上一步。
   - 如果效果可以，跳到下一步。
- Step3：尝试量化版本，评估效果。
   - 如果效果不行，回到上一步。
   - 如果效果可以，跳到下一步。
- Step4：尝试量化版本+ KV Cache 量化，评估效果。
   - 如果效果不行，回到上一步。
   - 如果效果可以，使用方案。

简单流程如下图所示。
[![](https://github.com/InternLM/tutorial/raw/vansin-patch-4/lmdeploy/img/quant.drawio.png#from=url&id=GPVu6&originHeight=981&originWidth=331&originalType=binary&ratio=1.5&rotation=0&showTitle=false&status=done&style=none&title=)](https://github.com/InternLM/tutorial/blob/vansin-patch-4/lmdeploy/img/quant.drawio.png)
另外需要补充说明的是，使用哪种量化版本、开启哪些功能，除了上述流程外，**还需要考虑框架、显卡的支持情况**，比如有些框架可能不支持 W4A16 的推理，那即便转换好了也用不了。
根据实践经验，一般情况下：

- 精度越高，显存占用越多，推理效率越低，但一般效果较好。
- Server 端推理一般用非量化版本或半精度、BF16、Int8 等精度的量化版本，比较少使用更低精度的量化版本。
- 端侧推理一般都使用量化版本，且大多是低精度的量化版本。这主要是因为计算资源所限。

以上是针对项目开发情况，如果是自己尝试（玩儿）的话：

- 如果资源足够（有GPU卡很重要），那就用非量化的正常版本。
- 如果没有 GPU 卡，只有 CPU（不管什么芯片），那还是尝试量化版本。
- 如果生成文本长度很长，显存不够，就开启 KV Cache。

建议大家根据实际情况灵活选择方案。
## 参考资料

- [InternLM/lmdeploy: LMDeploy is a toolkit for compressing, deploying, and serving LLMs.](https://github.com/InternLM/lmdeploy/)
- [仅需一块 3090 显卡，高效部署 InternLM-20B 模型 - 知乎](https://zhuanlan.zhihu.com/p/665725861)
