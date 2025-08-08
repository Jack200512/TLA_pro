- 常见的数据集文件格式主要有哪些，分别有什么特点 >>>
    - json，常为一个列表，列表中的每一个元素是字典
    - jsonl，json lines。每一行是一个独立的json对象
    - csv/tsv ,每一列对应一个字段，多个字段组成一行，一行相当于是一个json对象
- 
- 与json相比，jsonl有什么优势 >>>
    - jsonl支持流式加载，数据规模大时占优
    - 数据增量处理更加方便，直接追加行即可
- 
- 最常见的情况下，在数据集中，每条样本的组成是什么 >>>
    - instruction，样本核心部分，通常是完整的命令或问题
    - input，对instruction的补充，可以在input放instruction需要的材料
    - output，参考答案，模型需要根据instruction和input尝试输出output
- 
- 单一文本格式样本的组成 >>>
    - prompt，相当于instruction和input的结合体
    - response，对应output
- 
- 多轮对话样本的组成特点 >>>
    - 每条样本是一个对话数组，一个对话数组中含有多轮对话
    - 每轮对话包含说话人的角色role和内容content
- 
- 在多轮对话中，所谓的记忆是如何实现的 >>>
    - 上下文记忆
    - 在输入时，模型往往会拼接一定长度的历史对话与本轮输入，作为最终的输入
    - 每次对话生成都是独立的过程，模型将历史对话加入到输入中，添加了历史信息。
- 
- 
- Dataset从功能上，可以划分为几类 >>>
    - 训练集，为模型学习提供主要数据
    - 验证集，用于调整超参数，避免过拟合
    - 测试集，最终评估性能效果
- 
- 超参数是什么，包含哪些参数。简要解释 >>>
    - 超参数是在训练前手动设定的参数，在训练过程中不会变化
    - 通常包含learning rate, batch size , epochs ,weight decay, dropout比例(随机屏蔽神经元）
- 
- 如何简单理解过拟合 >>>
    - 模型在训练集上表现得好，但是在新数据上表现得差
    - 体现为对训练集的过度拟合贴近，与真实客观规律偏差较大
    - 模型泛化能力减弱
    - overfitting
- 
- 如何理解欠拟合 >>>
    - 模型学习太少，在训练集和验证集表现都差
    - underfitting
- 
- 如何简单理解模型泛化 >>>
    - 模型在未见过的数据上保持良好性能的能力
    - 泛化与过拟合可以理解为两个互相对立的概念
    - generalization
- 
- 
- 样本数量和样本质量如何影响指令微调的效果 >>>
    - 样本数量的影响较小，但不能太少
    - 样本质量更加重要，质量低的样本可能会直接降低模型表现
- 
- 如何对样本进行处理来提升样本质量，这个步骤叫做什么 >>>
    - 删除重复样本和过滤无效或无意义，甚至是错误的指令 
    - 叫做数据去重与清洗
- 
- 如何理解token相关的概念 >>>
    - token是模型处理文本的最小单位，可以理解为基本的计量单位
- 
- token是如何得到的，有什么特点 >>>
    - 通过tokenizer分词器得到，分词器内置分词算法
    - token长度不固定，取决于分词算法
    - 在一般情况下，同一个词，用同一个分词器多次处理，得到的分词结果相同
- 
- 
- .
    ```
    [
  {
    "instruction": "Translate English to French",
    "input": "Hello",
    "output": "Bonjour"
  },
  {
    "instruction": "Summarize the text",
    "input": "Artificial intelligence is transforming industries.",
    "output": "AI is changing industries."
  }
]
===
 {"instruction": "Translate English to French", "input": "Hello", "output": "Bonjour"}
{"instruction": "Summarize the text", "input": "Artificial intelligence is transforming industries.", "output": "AI is changing industries."}
===
instruction,input,output
"Translate English to French","Hello","Bonjour"
"Summarize the text","Artificial intelligence is transforming industries.","AI is changing industries."
 
    ```
- 
