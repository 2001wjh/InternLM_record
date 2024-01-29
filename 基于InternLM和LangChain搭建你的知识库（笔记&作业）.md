## 1.RAG
### 什么是RAG?
检索增强生成（Retrieval Augmented Generation），简称 RAG，已经成为当前最火热的LLM应用方案。经历今年年初那一波大模型潮，想必大家对大模型的能力有了一定的了解，但是当我们将大模型应用于实际业务场景时会发现，通用的基础大模型基本无法满足我们的实际业务需求，主要有以下几方面原因：

- **知识的局限性**：模型自身的知识完全源于它的训练数据，而现有的主流大模型（ChatGPT、文心一言、通义千问…）的训练集基本都是构建于网络公开的数据，对于一些实时性的、非公开的或离线的数据是无法获取到的，这部分知识也就无从具备。
- **幻觉问题**：所有的AI模型的底层原理都是基于数学概率，其模型输出实质上是一系列数值运算，大模型也不例外，所以它有时候会一本正经地胡说八道，尤其是在大模型自身不具备某一方面的知识或不擅长的场景。而这种幻觉问题的区分是比较困难的，因为它要求使用者自身具备相应领域的知识。
- **数据安全性**：对于企业来说，数据安全至关重要，没有企业愿意承担数据泄露的风险，将自身的私域数据上传第三方平台进行训练。这也导致完全依赖通用大模型自身能力的应用方案不得不在数据安全和效果方面进行取舍。

而RAG是解决上述问题的一套有效方案。
### RAG架构
RAG的架构如图中所示，简单来讲，RAG就是通过检索获取相关的知识并将其融入Prompt，让大模型能够参考相应的知识从而给出合理回答。因此，可以将RAG的核心理解为“检索+生成”，前者主要是利用向量数据库的高效存储和检索能力，召回目标知识；后者则是利用大模型和Prompt工程，将召回的知识合理利用，生成目标答案。
![](https://cdn.nlark.com/yuque/0/2024/webp/40974462/1706150650405-2b3bbf5a-8aac-4232-8c75-8fd32bd8aef7.webp#averageHue=%23728e7a&clientId=ud7686b1d-fe8e-4&from=paste&id=uc5640b5e&originHeight=839&originWidth=905&originalType=url&ratio=1.875&rotation=0&showTitle=false&status=done&style=none&taskId=u84eb872a-682f-46f6-ad94-a284150c7e3&title=)
RAG架构
完整的RAG应用流程主要包含两个阶段：

- 数据准备阶段：数据提取——>文本分割——>向量化（embedding）——>数据入库
- 应用阶段：用户提问——>数据检索（召回）——>注入Prompt——>LLM生成答案


**2.Langchain框架**
LangChain 框架是一个开源工具，通过为各种 LLM 提供通用接口来简化应用程序的开发流程，帮助开发者自由构建 LLM应用。
LangChain 的核心组成模块
●链 (Chains))：将组件组合实现端到端应用，通过一个对象封装实现一系列LLM 操作
●Eg.检索问答链，覆盖实现了 RAG (检索增强生成)的全部流程
![](https://cdn.nlark.com/yuque/0/2024/png/40974477/1704809244294-8e617f11-5551-40bd-909b-e1c6581d6239.png?x-oss-process=image%2Fresize%2Cw_816%2Climit_0#averageHue=%23e4eaf7&from=url&id=kgIh1&originHeight=496&originWidth=816&originalType=binary&ratio=1.875&rotation=0&showTitle=false&status=done&style=none&title=)

**3构建向量数据库**
![](https://cdn.nlark.com/yuque/0/2024/png/40974477/1704809442265-857708e5-63af-4cfe-a0bb-835ae783e6a4.png?x-oss-process=image%2Fresize%2Cw_870%2Climit_0#averageHue=%23d1dbef&from=url&id=X1Z0U&originHeight=489&originWidth=870&originalType=binary&ratio=1.875&rotation=0&showTitle=false&status=done&style=none&title=)

**4.搭建知识库助手**
![](https://cdn.nlark.com/yuque/0/2024/png/40974477/1704809690775-40c55ea5-05c0-4794-9973-3774f8aef3c0.png?x-oss-process=image%2Fresize%2Cw_762%2Climit_0#averageHue=%23dae1f1&from=url&id=B1rg7&originHeight=306&originWidth=762&originalType=binary&ratio=1.875&rotation=0&showTitle=false&status=done&style=none&title=)

![](https://cdn.nlark.com/yuque/0/2024/png/40974477/1704809912426-22622329-4867-4bc6-94c8-186d35e881f3.png?x-oss-process=image%2Fresize%2Cw_1026%2Climit_0#averageHue=%23d7e0f3&from=url&id=iUs6q&originHeight=615&originWidth=1026&originalType=binary&ratio=1.875&rotation=0&showTitle=false&status=done&style=none&title=)

![](https://cdn.nlark.com/yuque/0/2024/png/40974477/1704809937846-f2104e5f-794e-4a26-865a-8d56ad438a16.png?x-oss-process=image%2Fresize%2Cw_866%2Climit_0#averageHue=%23d9e2f4&from=url&id=qWxLK&originHeight=594&originWidth=866&originalType=binary&ratio=1.875&rotation=0&showTitle=false&status=done&style=none&title=)

若有收获，就点个赞吧

 
#### **基础作业**：复现课程知识库助手搭建过程
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704955776372-0744b463-86ef-4403-8f83-a602ce13ef49.png#averageHue=%23fefefd&clientId=ucaf139fd-a4f1-4&from=paste&height=575&id=u4a2938cd&originHeight=862&originWidth=1678&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=123525&status=done&style=none&taskId=u14c0a971-907f-4f78-8c98-53d5479c96d&title=&width=1118.6666666666667)
