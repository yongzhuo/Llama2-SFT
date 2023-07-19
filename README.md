# LLaMA2-SFT
LLaMA2-SFT, Llama-2-7B微调(transformers)/LORA(peft)/推理

## prompt
```官方chat-prompt为
text_1 = f"".join(["[INST] <<SYS>>\n    "
   "You are a helpful, respectful and honest assistant. "
   "Always answer as helpfully as possible, while being safe."
   " Your answers should not include any harmful, unethical, racist, sexist, toxic, dangerous, "
   "or illegal content. Please ensure that your responses are socially unbiased and positive in nature.\n\n"
   "    If a question does not make any sense, or is not factually coherent, "
   "explain why instead of answering something not correct. "
   "If you don't know the answer to a question, please don't share false information.\n"
   "<</SYS>>\n\n{0} [/INST] "]).format(
    data_point.get('instruction', '').strip() +"\t"+ data_point.get('input', '').strip())
    
    
我们缩短后为
text_1 = f"[INST] <<SYS>>\n    You are a helpful, respectful and honest assistant.<</SYS>>" \
         f"\n\n{0} [/INST] ".format(
    data_point.get('instruction', '').strip() + "\t" + data_point.get('input', '').strip())

```

## 微调样例
```shell
地址: llama2_sft/ft_llama2

配置: llama2_sft/ft_llama2/config.py
训练: python train.py
推理: python predict.py
验证: python evaluation.py
接口: python post_api.py
```



## 参考/感谢
 - [https://github.com/facebookresearch/llama](https://github.com/facebookresearch/llama)
 - [https://github.com/huggingface/peft](https://github.com/huggingface/peft)
 - [https://github.com/Instruction-Tuning-with-GPT-4/GPT-4-LLM](https://github.com/Instruction-Tuning-with-GPT-4/GPT-4-LLM)
 - [math23k](https://aclanthology.org/D17-1088)

## 免责申明
本项目相关资源仅供学术研究之用，使用涉及第三方代码的部分时，请严格遵循相应的开源协议。模型生成的内容受模型计算、随机性和量化精度损失等因素影响，本项目不对其准确性作出保证。对于模型输出的任何内容，本项目不承担任何法律责任，亦不对因使用相关资源和输出结果而可能产生的任何损失承担责任。
 - 大模型权重的详细协议见[facebookresearch/llama](https://github.com/facebookresearch/llama)
