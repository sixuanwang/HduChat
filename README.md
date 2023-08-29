# HduChat
Domain Large Language Model developed by Binjiang Institute of Hangzhou Dianzi University(HDU)

# 1、简介 Introduction
HduChat是一个由杭州电子科技大学大滨江研究院开发完成的垂直领域大语言模型。 与当前其它大模型相比，HduChat强化了基于RPA和知识图谱的信息抽取融合能力、垂直领域知识库向量检索和语义匹配能力、垂直领域产研结合多场景多任务生成能力。目前HduChat初步构建了面向科技教育、政务服务、医疗健康垂直领域的底层模型能力，后续将继续在金融科技、法律法规、开放知识等方面进一步加强。目前HduGPT支持包括智能知识问答、领域关键词提取、内容文本生成、文本摘要、简单代码生成、简单逻辑推理等多项能力。HduGPT还在在持续建设和优化中！期待对垂直领域大模型技术兴趣的人士加入，共建垂直领域大模型社区。

# 2、模型功能 Model Capabilities
目前，HduGPT支持包括智能知识问答、领域关键词提取、内容文本生成、文本摘要、简单代码生成、简单逻辑推理等多项能力。

## 智能知识问答
| 问题| 答案 |
| ------ | ------ |
| 个人如何操作自己缴纳社保？ | 个人可以通过以下方式自行缴纳社保：前往当地社保缴费大厅或自助缴费机进行现金缴费。登录当地社保缴费网站，使用个人身份证号码和密码进行登录，完成缴费。前往当地农商行各营业网点办理城乡居民医保委托扣缴事宜，将足额资金存入委托扣缴账户中，以确保扣款成功。使用支付宝、微信等第三方支付平台，完成城乡居民医保缴费。持本人社会保障卡（或身份证）至就近的银行进行现金缴费。注意：具体操作方式可能会因地区而异，建议您根据实际情况选择合适的方式进行缴费。 |

## 领域关键词提取
| 问题| 答案 |
| ------ | ------ |
| 【导语】：符合条件的企业应在2022年12月31日(含)前提出申请杭州一次性吸纳就业补贴，其中招用时间为2022年12月的，可在2023年1月31日前提出申请。　　2022年一次性吸纳就业补贴　　1、补贴对象　　营业执照注册地址在杭州市的中小微企业(营业执照注册地址在杭州市的1000人以下企业)。　　2、补贴条件　　同时符合以下条件：　　⑴在2022年新招用毕业年度高校毕业生(不含本单位法定代表人、负责人);　　⑵签订12个月以上劳动合同，依法连续缴纳社保费1个月以上。　　3、补贴标准　　每人一次性1500元。　　4、申报时间　　符合条件的企业应在2022年12月31日(含)前提出申请，其中招用时间为2022年12月的，可在2023年1月31日前提出申请。逾期申请，不予受理。　　同时符合疫情响应期间企业用工补贴、一次性扩岗补助和一次性吸纳就业补贴条件的，就高享受补贴政策，但不重复享受。个人可以通过以下方式自行缴纳社保：前往当地社保缴费大厅或自助缴费机进行现金缴费。登录当地社保缴费网站，使用个人身份证号码和密码进行登录，完成缴费。前往当地农商行各营业网点办理城乡居民医保委托扣缴事宜，将足额资金存入委托扣缴账户中，以确保扣款成功。使用支付宝、微信等第三方支付平台，完成城乡居民医保缴费。持本人社会保障卡（或身份证）至就近的银行进行现金缴费。注意：具体操作方式可能会因地区而异，建议您根据实际情况选择合适的方式进行缴费。 | 关键词：2022 年一次性吸纳就业补贴，营业执照注册地址，杭州市，中小微企业，毕业年度高校毕业生，劳动合同，社保费，补贴标准，申报时间，疫情响应期间企业用工补贴，一次性扩岗补助，申请入口，申请流程，常见问题。

## 内容文本生成
| 问题| 答案 |
| ------ | ------ |

## 简单代码生成
| 问题| 答案 |
| ------ | ------ |

## 简单逻辑推理
| 问题| 答案 |
| ------ | ------ |

# 3、准备工作 Preparation
由于ChatGLM开源协议的限制，本模型仅限于研究和学习用途使用。请严格遵守chatglm的使用要求和规范。为了确保这一点，我们需要确认您具有chatglm的原始权重，并来自完全合法渠道。<br>
部署门槛：FP16 半精度下，ChatGLM-6B 需要至少 13 GB 的显存进行推理，结合模型量化技术，这一需求可以进一步降低到 10GB（INT8）和 6GB。<br>
部署环境：<br>
操作系统：Ubuntu 22.04<br>
CUDA：12.0.1<br>
Python 3.10<br>

# 4、使用方法 Model Usage
1.下载工程文件<br>
2.在config.yml文件中修改LLM模型路径<br>
3.选择合适的知识库构建方法，并填写使用的embeding模型路径<br>
4.调整知识库参数（count，overlap，chunk_size等）<br>
5.加载知识库（运行plugin文件夹中的对应python文件）<br>
6.运行对应LLM的脚本文件 <br>

# 5、交流合作Collaborative
我们将持续开放部分相关领域的微调数据集、不同模型的微调与训练模型、基于本地知识库的领域大模型代码工具、基于领域大模型的典型应用。<br>
HduGPT还在在持续建设和优化中！如您对垂直领域大模型技术感兴趣，比如相应的算力、算法、数据、应用，期待您的加入，共建垂直领域大模型社区。

# 6、免责声明 Disclaimers
该项目仅供学习交流使用，禁止用于商业用途。在使用过程中，使用者需认真阅读并遵守以下声明:<br>
1.本项目仅为大模型测试功能而生，使用者需自行承担风险和责任，如因使用不当而导致的任何损失或伤害，本项目概不负责。<br>
2.本项目中出现的第三方链接或库仅为提供便利而存在，其内容和观点与本项目无关。使用者在使用时需自行辨别，本项目不承担任何连带责任；<br>
3.使用者在测试和使用模型时，应遵守相关法律法规，如因使用不当而造成损失的，本项目不承担责任，使用者应自行承担；<br>
4.本模型中出现的任何违反法律法规或公序良俗的回答，均不代表本项目观点和立场，我们将不断完善模型回答以使其更符合社会伦理和道德规范。<br>
使用本项目即表示您已经仔细阅读、理解并同意遵守以上免责声明。本项目保留在不预先通知任何人的情况下修改本声明的权利。<br>

# 7、Citation
如果使用本项目的代码、数据或模型，请引用本项目。
```
@misc{HduChat,
 author = {Sixuan Wang, Guanhua Qu, Yongjun Zhong, Fang Xu},
 title = {HduChat: Domain Large Language Model developed by Hangzhou Dianzi University},
 year = {2023},
 publisher = {GitHub},
 journal = {GitHub repository},
 howpublished = {\url{https://github.com/sixuanwang/HduChat}},
}
```

我们对ChatGLM团队的工作表示衷心的感谢！
```
@article{zeng2022glm,
  title={Glm-130b: An open bilingual pre-trained model},
  author={Zeng, Aohan and Liu, Xiao and Du, Zhengxiao and Wang, Zihan and Lai, Hanyu and Ding, Ming and Yang, Zhuoyi and Xu, Yifan and Zheng, Wendi and Xia, Xiao and others},
  journal={arXiv preprint arXiv:2210.02414},
  year={2022}
}
@inproceedings{du2022glm,
  title={GLM: General Language Model Pretraining with Autoregressive Blank Infilling},
  author={Du, Zhengxiao and Qian, Yujie and Liu, Xiao and Ding, Ming and Qiu, Jiezhong and Yang, Zhilin and Tang, Jie},
  booktitle={Proceedings of the 60th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)},
  pages={320--335},
  year={2022}
}
```
