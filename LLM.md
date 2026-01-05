## LLM

-   **对齐（alignment）**
-   **ELMo技术: Embeddings from Language Models**

-   **分布式集群并行**

-   **训练LLM三阶段**
    -   **预训练（Pretraining）**
    -   **监督微调（Supervised Fine-Tuning，SFT）**
    -   **强化学习与人类反馈（Reinforcement Learning with Human Feedback，RLHF）**

-   **有监督微调/无监督微调**
-   **指令遵循（Instruction Following）: 指令微调**

-   **旋转位置编码（Rotary Positional Encoding，RoPE）**

-   | 符号  | 英文词   | 中文量级 | 数值（10 的幂）          | 举个例子                  |
    | ----- | -------- | -------- | ------------------------ | ------------------------- |
    | **K** | Kilo     | 千       | 10³ = 1,000              | 32K tokens → 3.2万字      |
    | **M** | Million  | 百万     | 10⁶ = 1,000,000          | 13M 参数 → 1300万         |
    | **B** | Billion  | 十亿     | 10⁹ = 1,000,000,000      | GPT-3：175B 参数 → 1750亿 |
    | **T** | Trillion | 万亿     | 10¹² = 1,000,000,000,000 | GPT-5 可能 1T 参数级      |

-   **分布式训练框架: 例如DeepSpeed**

-   | 模型             | 全称                  | 功能           | 输入          | 核心思想             |
    | ---------------- | --------------------- | -------------- | ------------- | -------------------- |
    | **Transformer**  | 通用注意力结构        | 理解序列       | 词序列        | Self-Attention       |
    | **ViT**          | Vision Transformer    | 理解图片       | 图像块序列    | 把图片当“句子”读     |
    | **DiT**          | Diffusion Transformer | 生成图片/视频  | 噪声 + 条件   | Transformer 去噪生成 |
    | **Action Token** | 动作指令向量          | 控制时序与动作 | 动作/时间信息 | 多模态控制生成       |

-   **精度**
-   **分片（Sharding）**

-   **Adam (Adaptive Moment Estimation)** 

-   **prompt/completion**

-   **PEFT(Parameter-Efficient Fine-Tuning) 参数高效微调**

-   **Adapter:插在原模型里的“小型可训练模块”**

    >   PEFT 是方法论（“只训练少量参数”），Adapter 是实现方式（“往大模型里插小模块”）

-   **Processor:** 把原始数据变成模型能吃的格式的工具包

## Huggingface

```python
from transformers import HfArgumentParser #专门用来配合 dataclass 解析命令行参数的工具类
parser = HfArgumentParser((ModelArguments, DataArguments, TrainingArguments))
model_args, data_args, training_args = parser.parse_args_into_dataclasses()  #把命令行参数自动解析成多个 dataclass 实例

from transformers import TrainingArguments     #配置训练全过程的参数类，用来控制训练行为，例如学习率、batch size、保存模型方式、评估频率等

from peft import LoraConfig,get_peft_model, PeftModel     #PEFT 是 HuggingFace 的一个大组件，用来做 LoRA / QLoRA / Adapter / Prompt-Tuning   PEFT = Parameter-Efficient Fine-Tuning
lora_config = LoraConfig(    # 描述 LoRA 的超参数和作用范围的配置对象
    task_type='CAUSAL_LM',   # 任务类型
    r=training_args.lora_r,  # LoRA 的秩
    lora_alpha=training_args.lora_alpha,  # 缩放系数
    lora_dropout=training_args.lora_dropout, # dropout，防止过拟合
    bias=training_args.lora_bias,
    target_modules=target_modules,  # 要插 LoRA 的层名列表
    modules_to_save=['embed_tokens', 'lm_head'] if tune_lm_head else None
)
model = get_peft_model(model, lora_config, adapter_name="my_lora")  # 把一个普通的 HF 模型包装成带 LoRA 适配器的 PeftModel

from transformers import AutoConfig     # 根据模型名称选择Config 类
config = AutoConfig.from_pretrained("Qwen/Qwen2-VL-7B")
```

| 类                    | from_pretrained 来源 |
| --------------------- | -------------------- |
| `PreTrainedModel`     | 用来加载模型权重     |
| `PreTrainedTokenizer` | 加载 tokenizer       |
| `PretrainedConfig`    | 加载 config          |







