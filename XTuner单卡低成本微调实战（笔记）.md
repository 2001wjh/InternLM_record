---

# 目录：
### 1.Finetune简介
### 2.XTuner介绍
### 3.8GB显卡玩转LLM
### 4.动手实战环节

---

# 第一部分：Finetune简介

---

![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704956456455-22cdc7e1-4bb6-48a1-97c2-d74ce8ae8948.png#averageHue=%23dde2f4&clientId=uca623f3f-751f-4&from=paste&height=797&id=ucec8cec1&originHeight=1195&originWidth=2556&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1907385&status=done&style=none&taskId=u492d0d7c-f761-410c-b8a5-4eb8203872d&title=&width=1704)
## 增量预训练和指令跟随
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704956608900-b321d41d-069c-495a-9fe5-9dd93cd58c9c.png#averageHue=%23f9f8fc&clientId=uca623f3f-751f-4&from=paste&height=595&id=u8f8b0e21&originHeight=892&originWidth=2497&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=545844&status=done&style=none&taskId=u350461dc-8cc7-4400-97fe-cb46c6fc685&title=&width=1664.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704956797011-1fada14f-ddac-4f18-b800-1103a814d76e.png#averageHue=%23c1c8d8&clientId=uca623f3f-751f-4&from=paste&height=961&id=uc1dbc227&originHeight=1441&originWidth=2224&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1807595&status=done&style=none&taskId=ud12d0f66-a732-4419-b621-06f7b8f92e2&title=&width=1482.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704956891255-58e72275-0039-4543-9744-d9466cb6b9af.png#averageHue=%23d3e1f4&clientId=uca623f3f-751f-4&from=paste&height=816&id=u9d9f8690&originHeight=1224&originWidth=2545&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=2093477&status=done&style=none&taskId=u4ef44c6a-e4f6-44e8-824d-27ba684d9ea&title=&width=1696.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957105771-218557c7-3bb6-452f-a65e-99f92e3fd955.png#averageHue=%23dce4f8&clientId=uca623f3f-751f-4&from=paste&height=767&id=ub45e929b&originHeight=1150&originWidth=2548&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1609023&status=done&style=none&taskId=u1c3184b9-0d85-4c61-b9a7-3bc705e35ed&title=&width=1698.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957224238-a06b7360-e99b-4055-beea-b6055e11b59a.png#averageHue=%23cfdaf0&clientId=uca623f3f-751f-4&from=paste&height=899&id=u1c4eee35&originHeight=1348&originWidth=2530&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1995020&status=done&style=none&taskId=u4756ca34-9033-4380-9111-0384a5a5368&title=&width=1686.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957304780-001e8b5b-1673-4757-a284-39aadc6e3956.png#averageHue=%23ededf3&clientId=uca623f3f-751f-4&from=paste&height=920&id=u3bd0bb29&originHeight=1380&originWidth=2311&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1588833&status=done&style=none&taskId=u6869179b-a5a8-414b-8e74-c9bac341509&title=&width=1540.6666666666667)

# 第二部分：XTuner微调框架

---

 ![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957502177-641975bd-5cb9-459d-a192-0af8b06f54ca.png#averageHue=%23d6dff3&clientId=uca623f3f-751f-4&from=paste&height=938&id=uedcda60b&originHeight=1407&originWidth=2551&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=3270870&status=done&style=none&taskId=u921f2fca-6b0d-4a05-aa8e-853549b3f08&title=&width=1700.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957712492-5f6bf6f6-aaf3-42b5-81cb-2cf97013a847.png#averageHue=%23d9e3f7&clientId=uca623f3f-751f-4&from=paste&height=886&id=u91b92fd4&originHeight=1329&originWidth=2502&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1993743&status=done&style=none&taskId=uc6feef3d-2582-4ec3-8f58-2831be3ea22&title=&width=1668)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957723284-65f65eb9-1937-4b27-9604-c420394d1378.png#averageHue=%23d2d8ea&clientId=uca623f3f-751f-4&from=paste&height=789&id=u7726e75f&originHeight=1183&originWidth=2364&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1416220&status=done&style=none&taskId=u6c0bca80-d8c9-4f2d-b271-721b4a90b55&title=&width=1576)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957742318-45ff86ed-c4bf-4498-bfd5-f90270616fe3.png#averageHue=%23e9ebf9&clientId=uca623f3f-751f-4&from=paste&height=948&id=ubc25ca64&originHeight=1422&originWidth=2418&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1472058&status=done&style=none&taskId=u1aebcb10-1388-42ca-8606-e24882b55cc&title=&width=1612)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957762688-e5b8fd8c-9737-49fe-9951-768964c9060e.png#averageHue=%2382b6cc&clientId=uca623f3f-751f-4&from=paste&height=937&id=u2f303105&originHeight=1405&originWidth=2449&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1860497&status=done&style=none&taskId=ued528767-91a3-4925-83a3-1770d8f6632&title=&width=1632.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957668509-d7689c7f-fa9b-4e7d-8665-c043626145d5.png#averageHue=%23dce3f6&clientId=uca623f3f-751f-4&from=paste&height=771&id=uae846478&originHeight=1156&originWidth=2358&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1366095&status=done&style=none&taskId=ua3a8fe57-ba36-496d-9eb3-c054b979133&title=&width=1572)
# 第三部分：8GB显存玩转LLM

---

![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957826951-d45b3707-7c31-49b2-bbd3-d4208b6b01f2.png#averageHue=%23d4ddf1&clientId=uca623f3f-751f-4&from=paste&height=902&id=ue0c385ac&originHeight=1353&originWidth=2533&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=2283401&status=done&style=none&taskId=ue29aba95-05d2-435e-bd7f-bb9cb09f136&title=&width=1688.6666666666667)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704957908414-92f3ce61-1794-480a-903b-055092d099fe.png#averageHue=%23dfe5f7&clientId=uca623f3f-751f-4&from=paste&height=849&id=ud495301e&originHeight=1273&originWidth=2271&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=1545045&status=done&style=none&taskId=u58959ac9-07ce-4758-be3e-6716db8094c&title=&width=1514)
# 第四部分：动手实战环节

---

xtuner支持的模型架构、对应的微调方法和数据集
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704959442107-e72e142f-708c-4375-ab39-158c77b477fc.png#averageHue=%23181818&clientId=uca623f3f-751f-4&from=paste&height=567&id=u255429e0&originHeight=850&originWidth=1654&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=146447&status=done&style=none&taskId=ue351045e-2833-48fc-b36e-710f538f68c&title=&width=1102.6666666666667)
拷贝一个配置文件到当前目录： # xtuner copy-cfg ${CONFIG_NAME} ${SAVE_PATH}
在本案例中即：（注意最后有个英文句号，代表复制到当前路径）
```
cd ~/ft-oasst1
xtuner copy-cfg internlm_chat_7b_qlora_oasst1_e3 .
```
配置文件名的解释：
xtuner copy-cfg internlm_chat_7b_qlora_oasst1_e3 .

| 模型名 | internlm_chat_7b |
| --- | --- |
| 使用算法 | qlora |
| 数据集 | oasst1 |
| 把数据集跑几次 | 跑3次：e3 (epoch 3 ) |

*无 chat比如 internlm-7b 代表是基座(base)模型
# 备注：
## 1.常用超参
| 参数名 | 解释 |
| --- | --- |
| **data_path** | 数据路径或 HuggingFace 仓库名 |
| max_length | 单条数据最大 Token 数，超过则截断 |
| pack_to_max_length | 是否将多条短数据拼接到 max_length，提高 GPU 利用率 |
| accumulative_counts | 梯度累积，每多少次 backward 更新一次参数 |
| evaluation_inputs | 训练过程中，会根据给定的问题进行推理，便于观测训练状态 |
| evaluation_freq | Evaluation 的评测间隔 iter 数 |
| ...... | ...... |

如果想把显卡的显存吃满，充分利用显卡资源，可以将 max_length 和 batch_size 这两个参数调大。
## 2.tmux工具
	`tmux` 是一款非常有用的终端复用软件，它可以帮助你**在单一的SSH连接中打开多个终端窗口，并且可以轻松地在他们之间切换**。更重要的是，`tmux` 可以**在SSH连接断开时保持你的程序运行，这在远程编程或者管理服务器时非常实用。**
以下是`tmux`的一些主要特性和功能：
1. 会话管理：可以创建、删除、列出和切换多个会话。你可以把会话看作是一个完全独立的工作空间，里面运行着你的程序，你可以随时切换到其他会话，或者在一次SSH连接中打开多个会话。
2. 窗口和面板：在每个`tmux`会话中，你可以创建多个窗口，就像你的桌面环境里的窗口一样。而且，每个窗口内又可以划分为多个面板，每个面板都是一个独立的命令行界面。
3. 程序持久化：最重要的一点是，即使SSH连接断开，`tmux`会话仍然会在服务器上运行，你可以再次连接SSH并且附着到已经存在的`tmux`会话，就像你从未离开过一样。这对于运行很长时间的任务（比如大数据处理或者模型训练）非常有用。
以下是一些常用的`tmux`命令：
- `tmux new -s mysession`：创建一个新的tmux会话
- `tmux a -t mysession`：附着到一个已经存在的tmux会话
- `tmux ls`：列出当前的tmux会话
- 在`tmux`会话中，你可以按 `Ctrl+b` 然后再按 `"` 或 `%` 来分割窗口
- 用`Ctrl+b` 然后箭头键可以在面板间切换

#### 将微调得到的 PTH 模型转换为 HuggingFace 模型，**即：生成 Adapter 文件夹**
 xtuner convert pth_to_hf ${CONFIG_NAME_OR_PATH} ${PTH_file_dir} ${SAVE_PATH}
在本示例中，为：
```
mkdir hf
 export MKL_SERVICE_FORCE_INTEL=1
 
 xtuner convert pth_to_hf ./internlm_chat_7b_qlora_medqa2019_e3.py ./work_dirs/internlm_chat_7b_qlora_medqa2019_e3/epoch_1.pth ./hf
```
**此时，hf 文件夹即为我们平时所理解的所谓 “LoRA 模型文件”**
可以简单理解：LoRA 模型文件 = Adapter
## 3.部署与测试
#### 将 HuggingFace adapter 合并到大语言模型：
```
xtuner convert merge ./internlm-chat-7b ./hf ./merged --max-shard-size 2GB
 # xtuner convert merge \
 #     ${NAME_OR_PATH_TO_LLM} \
 #     ${NAME_OR_PATH_TO_ADAPTER} \
 #     ${SAVE_PATH} \
 #     --max-shard-size 2GB
```
#### 与合并后的模型对话：
```
# 加载 Adapter 模型对话（Float 16）
 xtuner chat ./merged --prompt-template internlm_chat
 
 # 4 bit 量化加载
 # xtuner chat ./merged --bits 4 --prompt-template internlm_chat
```
#### Demo

- 修改 cli_demo.py 中的模型路径
```
- model_name_or_path = "/root/model/Shanghai_AI_Laboratory/internlm-chat-7b"
 + model_name_or_path = "merged"
```

- 运行 cli_demo.py 以目测微调效果

**效果：**

| 微调前 | 微调后 |
| --- | --- |
| [![](https://github.com/InternLM/tutorial/raw/main/xtuner/imgs/beforeFT.png#from=url&id=sBZCv&originHeight=400&originWidth=807&originalType=binary&ratio=1.5&rotation=0&showTitle=false&status=done&style=none&title=)](https://github.com/InternLM/tutorial/blob/main/xtuner/imgs/beforeFT.png) | [![](https://github.com/InternLM/tutorial/raw/main/xtuner/imgs/afterFT.png#from=url&id=sLl9P&originHeight=400&originWidth=806&originalType=binary&ratio=1.5&rotation=0&showTitle=false&status=done&style=none&title=)](https://github.com/InternLM/tutorial/blob/main/xtuner/imgs/afterFT.png) |

**xtuner chat** **的启动参数**

| 启动参数 | 干哈滴 |
| --- | --- |
| **--prompt-template** | 指定对话模板 |
| --system | 指定SYSTEM文本 |
| --system-template | 指定SYSTEM模板 |
| -**-bits** | LLM位数 |
| --bot-name | bot名称 |
| --with-plugins | 指定要使用的插件 |
| **--no-streamer** | 是否启用流式传输 |
| **--lagent** | 是否使用lagent |
| --command-stop-word | 命令停止词 |
| --answer-stop-word | 回答停止词 |
| --offload-folder | 存放模型权重的文件夹（或者已经卸载模型权重的文件夹） |
| --max-new-tokens | 生成文本中允许的最大 token 数量 |
| **--temperature** | 温度值 |
| --top-k | 保留用于顶k筛选的最高概率词汇标记数 |
| --top-p | 如果设置为小于1的浮点数，仅保留概率相加高于 top_p 的最小一组最有可能的标记 |
| --seed | 用于可重现文本生成的随机种子 |

