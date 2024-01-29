### 服务器连接
- 本地使用ssh连接服务器的方式
```
ssh -o StrictHostKeyChecking=no -p 33406 root@ssh.intern-ai.org.cn

注释：
-o StrictHostKeyChecking=no：这是一个 SSH 选项，用于禁用主机密钥检查。在首次连接到远程主机时，SSH 会提示用户是否接受主机密钥，通过使用该选项，可以避免这个提示。
-p 33406：指定连接的远程服务器的 SSH 端口号。通常，默认的 SSH 端口号是 22，但这里使用了不同的端口号 33406。
root@ssh.intern-ai.org.cn：这是连接的目标主机地址和用户名。root 是连接的用户名，ssh.intern-ai.org.cn 是远程主机的地址。
运行这个命令，通过 SSH 连接到远程服务器，并使用用户名 root 进行身份验证。
```

- 本地端口的配置
```
1. 生成 SSH 密钥对
ssh-keygen -t rsa

2. 通过系统自带的 cat 工具查看文件内容
cat ~\.ssh\id_rsa.pub

3. 运行此命令，在本地计算机的端口 6006 上创建一个 SSH ，可以通过该SSH访问远程服务器上的服务
ssh -CNg -L 6006:127.0.0.1:6006 root@ssh.intern-ai.org.cn -p 33406
其中：
-C: 启用压缩。这可以提高在慢速网络连接上的性能。
-N: 表示不执行远程命令。这在你只想建立 SSH 隧道而不运行远程命令时很有用。
-g: 允许远程主机连接到通过此 SSH 隧道建立的本地端口。
-L 6006:127.0.0.1:6006: 将本地端口 6006 映射到远程服务器的 127.0.0.1:6006。
root@ssh.intern-ai.org.cn: 远程 SSH 用户名和主机地址。
-p 33406: 远程 SSH 服务器的端口号。
```

---

### 使用Hugging face进行模型下载
#### 安装依赖
```
pip install -U huggingface_hub
```
#### 使用huggingface_hub python包安装下载
```python
import os 
from huggingface_hub import hf_hub_download  # Load model directly 

hf_hub_download(repo_id="internlm/internlm-20b", filename="config.json")
```
> 可以使用find，具体是find ~ -name "config.json"命令找到文件下载的路径，默认安装在以下路径：/root/.cache/huggingface
> 若想改变安装路径可以参考：[Environment variables (huggingface.co)](https://huggingface.co/docs/huggingface_hub/main/en/package_reference/environment_variables)
> 在window下参考：[【Huggingface下载model】解决更改从Huggingface上下载语言模型或者数据的默认地址_huggingface默认下载路径-CSDN博客](https://blog.csdn.net/z851245955/article/details/134025660)

```python
import os
# 下载模型
os.system('huggingface-cli download --resume-download internlm/internlm-20b --local-dir your_path')
```
> huggingface-cli download的好处是可以，若发生断网等中断下载，再次运行时会接着下载

#### 运行python代码
```python
export HF_ENDPOINT=https://hf-mirror.com
# 用于设置环境变量 HF_ENDPOINT，将其值设置为 "https://hf-mirror.com"。
# 这个环境变量可能被代码中的其他部分使用，以指定从哪个地址下载或上传数据，模型等。
# 在这里，`HF_ENDPOINT` 被设置为 "https://hf-mirror.com"，
# 是一个 Hugging Face Hub 的自定义镜像地址，用于加速数据或模型的访问。
```
镜像问题具体参考：[https://zhuanlan.zhihu.com/p/676222159](https://zhuanlan.zhihu.com/p/676222159)

---

### demo运行
```
streamlit run web_demo.py --server.address 127.0.0.1 --server.port 6006

注释：
streamlit run web_demo.py：运行 Streamlit 应用程序 web_demo.py。
--server.address 127.0.0.1：设置服务的地址为本地主机（127.0.0.1），这意味着该服务只能从本地访问。
--server.port 6006：设置服务运行的端口为 6006。
运行这个命令后，可以通过在浏览器中输入 http://127.0.0.1:6006 访问该应用程序。
这个命令会启动一个本地的 Web 服务器，用于提供 Streamlit 应用程序。
```
```
python examples/web_demo.py  \
    --folder /root/model/Shanghai_AI_Laboratory/internlm-xcomposer-7b \
    --num_gpus 1 \
    --port 6006
    
注释：通过运行python脚本的方式
python examples/web_demo.py: 运行名为 web_demo.py 的 Python 脚本
--folder /root/model/Shanghai_AI_Laboratory/internlm-xcomposer-7b: 指定了一个参数 --folder，其值为 /root/model/Shanghai_AI_Laboratory/internlm-xcomposer-7b。用于指定模型的文件夹或配置文件的路径。
--num_gpus 1: 指定了一个参数 --num_gpus，其值为 1。用于指定 GPU 的数量。
--port 6006: 指定了一个参数 --port，其值为 6006。用于指定应用程序运行的端口号。
```
> web_demo.py代码
> ![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974477/1704621775149-513195bf-eb92-43e4-9a86-b425d459ef5b.png#averageHue=%23f4f0f0&clientId=u967fe440-6239-4&from=paste&height=111&id=u237df98e&originHeight=166&originWidth=793&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=36899&status=done&style=none&taskId=ua28b0240-9cd0-46ea-aa2b-5d0040b902d&title=&width=528.6666666666666)
> ![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974477/1704621788310-33f24f59-e0a1-42a4-b99f-9137b690f7e1.png#averageHue=%23f8f7f7&clientId=u967fe440-6239-4&from=paste&height=111&id=u13962d10&originHeight=166&originWidth=906&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=23355&status=done&style=none&taskId=u7834c576-6b33-4d49-b814-c094d761198&title=&width=604)
> 因此若args.private为默认情况下default=False，则输出的链接会是：0.0.0.0：6006,且share=True
> 否则才会是127.0.0.1:6006，share=False

> **share=False** 意味着 Gradio 将不会将应用程序共享到 Gradio 的服务器上。在 Gradio 中，您可以选择在其服务器上托管您的应用程序，以便您可以通过一个公共 URL 访问它，而不仅仅是在本地计算机上。如果 **share=True**，则 Gradio 将生成一个公共 URL，可以与其他人共享，使他们能够访问该应用程序。
> 通过设置 **share=False**，应用程序将仅在本地运行，并且不会通过 Gradio 服务器共享。这对于开发和测试阶段很有用，因为可以在本地进行调试，而无需将应用程序部署到 Gradio 服务器上。

> Gradio：实现AI算法可视化部署
> 优势：
> - 自动生成页面且**可交互**
> - 改动**几行代码**就能完成
> - 支持自定义多种输入输出
> - 支持生成**可外部访问的链接**进行分享


**基础作业一：使用 InternLM-Chat-7B 模型生成 300 字的小故事**
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704942672566-5ff83841-97d3-4442-83ae-a622f8b4d0c2.png#averageHue=%232b2a29&clientId=ud6e1654a-b65f-4&from=paste&height=304&id=ue360effa&originHeight=456&originWidth=1704&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=462045&status=done&style=none&taskId=u32d921b9-7fb6-4ae4-bcd3-49e27dc4aa2&title=&width=1136)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704942684599-f57c92e1-4bd8-4b52-9746-9565e8276d8e.png#averageHue=%23fefdfd&clientId=ud6e1654a-b65f-4&from=paste&height=596&id=ne0zx&originHeight=894&originWidth=1707&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=234551&status=done&style=none&taskId=u17db2610-57b4-43cc-8561-ad2f8ec1c23&title=&width=1138)

**基础作业二：熟悉 hugging face 下载功能，使用 huggingface_hub python 包，下载 InternLM-20B 的 config.json 文件到本地**

**进阶作业一：完成浦语·灵笔的图文理解及创作部署**
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704942723428-6aa07c4a-ee62-4f60-a7c7-881c0d4cfc73.png#averageHue=%23fefdfd&clientId=ud6e1654a-b65f-4&from=paste&height=567&id=OhBBt&originHeight=850&originWidth=1707&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=598090&status=done&style=none&taskId=u0633023e-8107-4447-a836-64816f77b16&title=&width=1138)

**进阶作业二：完成 Lagent 工具调用 Demo 创作部署**
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40974462/1704942701815-7a2ac764-519b-44c4-abcc-047e1f1c595a.png#averageHue=%23e3d2bc&clientId=ud6e1654a-b65f-4&from=paste&height=566&id=hXyAj&originHeight=849&originWidth=1705&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=115167&status=done&style=none&taskId=ube0f26c0-a4cd-46d8-b56f-4e0ef82f4fc&title=&width=1136.6666666666667)
