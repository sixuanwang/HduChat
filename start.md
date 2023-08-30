# HDUchat(ChatGLM-6B版本)本地部署

## 1.1 硬件需求

| 量化等级      | 最低 GPU 显存 |
| :-------- | :-------- |
| FP16（无量化） | 13 GB     |
| INT8      | 10 GB     |
| INT4      | 6 GB      |

## 1.2 项目地址

Github:<https://github.com/THUDM/ChatGLM-6B>， <https://github.com/sixuanwang/HduChat>

Hugging Face Hub(模型地址):<https://huggingface.co/THUDM/ch>

## 2.1 从github和Hugging Face上下载所需要启动模型的文件

## 2.2 安装依赖环境

想要使用HDUchat需要安装一些依赖环境,这里给出所需要依赖环境所要求的库，需要手动安装,也可以用项目文件下提供的requirement.txt进行快速安装。

进入 HDUchat-main 目录，在上方地址栏输入cmd，打开控制台命令行，分别输入以下命令 pip install -r requirements.txt安装所有需要的依赖包

    #一键安装 
    pip install -r requirement.txt 
    #依赖的库 
    protobuf>=3.19.5,<3.20.1 
    transformers>=4.26.1 
    icetk cpm_kernels 
    torch>=1.10

注意

1、如果出现报错 Could not find module 'nvcuda.dll' 或者 RuntimeError: Unknown platform: darwin (MacOS) ，请打开并编辑 web\_demo.py 文件，将所有的 THUDM/chatglm-6b 替换成 chatglm-6b。

2、该项目默认使用显卡FP16模式运行，此模式需要12G以上的显卡才能正常运行，所以需要手动修改其中的代码

```python
# 12G以上 FP16
model = AutoModel.from pretrafned("chatglm-6b",trust remote code=True).half().cuda()
# 8G显存 INT8量化
model = AutoModel.from pretrained("chatgim-6b", trust remote code=True),half().quantize(8).cuda()
# 8G以下显存 INT4量化
model = AutoModel.from pretrained("chatgim-6b", trust remote code=True),half().quantize(4).cuda()
# CPU模式 32G内存
model m AutoModel.from pretxained("chatglm-6b", txust remote code True).float()
# CPu模式 16GB内存
model m AutoModel.from pretxained("chatglm-6b", txust remote code True).bfloat16()
```

## 2.3 对话脚本启动准备

做完以上步骤我们就可以去启动python脚本运行了,HDUchat下提供了cli\_demo.py和web\_demo.py两个文件来启动模型,第一个是使用命令行进行交互,第二个是使用gradio库使用本机服务器进行网页交互

### 2.3.1 调整模型文件的启动路径

由于要使用本地模型启动,所以我们需要把从Hugging Face Hub加载改为本地路径加载,在/home/aistudio/work/ChatGLM-6B/下的cli\_demo.py和web\_demo.py文件中进行修改

    # 将THUDM/chatglm-6b 修改为对应的llm地址
    tokenizer = AutoTokenizer.from_pretrained("THUDM/chatglm-6b", trust_remote_code=True) 
    model = AutoModel.from_pretrained("THUDM/chatglm-6b", trust_remote code=True).half().cuda()



### 2.3.2 添加环境变量

这里需要添加以下命令来解决问题

    export LD_LIBRARY_PATH=(你的服务器环境路径):$LD_LIBRARY_PATH

如果是使用外部库

    export LD_LIBRARY_PATH=(你的外部库环境路径):$LD_LIBRARY_PATH # 默认环境导入环境变量 !export LD_LIBRARY_PATH="/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/nvidia/cublas/lib:$LD_LIBRARY_PATH" # 使用外部库环境导入环境变量 !export LD_LIBRARY_PATH="/home/aistudio/work/external-libraries/nvidia/cublas/lib:$LD_L

## 3.项目启动

    !python /home/aistudio/work/HDUchat-6B/cli_demo.py


