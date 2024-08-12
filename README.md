### CHED
 A Cross-Historical Dataset with a Logical Event Schema for Classical Chinese Event Detection.

---

### 数据集说明 | Dataset Description

本数据集是古代汉语历史事件检测数据集（CHED），旨在帮助研究者对古文历史文本中的事件进行检测与分类。数据集涵盖了《二十四史》中多个历史人物和事件的记录，适用于构建和评估古代历史文本事件检测的算法与模型。

This dataset, named the Classical Chinese Historical Event Dataset (CHED), is designed to aid researchers in detecting and classifying events within classical Chinese historical texts. It covers multiple historical figures and events recorded in the "Twenty-Four Histories," making it suitable for constructing and evaluating algorithms and models for event detection in ancient historical texts.

#### 数据集文件 | Dataset Files

- **train.jsonl**
  - 包含训练数据集，用于模型的训练过程。数据集经过标注，包含了事件触发词及其对应的事件类型标签。
  - Contains the training dataset used for the model's training process. The dataset is annotated, including event trigger words and their corresponding event type labels.

- **valid.jsonl**
  - 包含验证数据集，用于在训练过程中对模型进行验证和调整。数据的标注与训练集一致。
  - Contains the validation dataset used to validate and adjust the model during training. The annotations are consistent with the training set.

- **test.jsonl**
  - 包含测试数据集，用于在模型训练完成后对其性能进行评估。标注方式与训练集和验证集一致。
  - Contains the test dataset used to evaluate the model's performance after training is complete. The annotation method is consistent with the training and validation sets.

- **all.jsonl**
  - 包含整个数据集的所有数据，包括训练集、验证集和测试集的所有内容，适用于全面分析或模型训练时的整体数据使用。
  - Contains all the data from the entire dataset, including the training, validation, and test sets, suitable for comprehensive analysis or using the entire data during model training.

- **doc2id.jsonl**
  - 该文件为文档和对应ID的映射关系，帮助标注或训练时快速定位和检索相关文本。
  - This file maps documents to their corresponding IDs, aiding in quickly locating and retrieving relevant texts during annotation or training.

- **label.jsonl**
  - 该文件定义了数据集中所有可能的事件标签，包含标签的详细信息和分类。
  - This file defines all possible event labels in the dataset, including detailed information and classification of the labels.
 
#### 数据集格式说明 | Dataset Format Description

```json
{
  "sen_id": 1986,   # 句子序号 | Sentence ID
  "doc_id": 32029,  # 文档编码 | Document ID
  "text": "寻以本官行梁州刺史。", # 文本内容 | Text Content
  "events": [  # 事件 | Events
    {
      "id": 3290,  # 标签序号 | Label ID
      "trigger": "行",  # 触发词 | Trigger Word
      "label": "职位-官位-任职",  # 事件标签 | Event Label
      "start_offset": 4,  # 触发词在“text”中的起始索引位置 | Start Offset of Trigger in Text
      "end_offset": 5  # 触发词在“text”中的终止索引位置 | End Offset of Trigger in Text
    }
  ]
}
```

#### 论文引用 | Citation

如果您在研究中使用了该数据集，请引用以下论文：

If you use this dataset in your research, please cite the following paper:

```
@inproceedings{congcong-etal-2023-ched,
    title = "{CHED}: A Cross-Historical Dataset with a Logical Event Schema for Classical {C}hinese Event Detection",
    author = "Congcong, Wei  and
      Zhenbing, Feng  and
      Shutan, Huang  and
      Wei, Li  and
      Yanqiu, Shao",
    editor = "Sun, Maosong  and
      Qin, Bing  and
      Qiu, Xipeng  and
      Jiang, Jing  and
      Han, Xianpei",
    booktitle = "Proceedings of the 22nd Chinese National Conference on Computational Linguistics",
    month = aug,
    year = "2023",
    address = "Harbin, China",
    publisher = "Chinese Information Processing Society of China",
    url = "https://aclanthology.org/2023.ccl-1.74",
    pages = "875--888",
    abstract = "{``}Event detection (ED) is a crucial area of natural language processing that automates the extraction of specific event types from large-scale text, and studying historical ED in classical Chinese texts helps preserve and inherit historical and cultural heritage by extracting valuable information. However, classical Chinese language characteristics, such as ambiguous word classes and complex semantics, have posed challenges and led to a lack of datasets and limited research on event schema construction. In addition, large-scale datasets in English and modern Chinese are not directly applicable to historical ED in classical Chinese. To address these issues, we constructed a logical event schema for classical Chinese historical texts and annotated the resulting dataset, which is called classical Chinese Historical Event Dataset (CHED). The main challenges in our work on classical Chinese historical ED are accurately identifying and classifying events within cultural and linguistic contexts and addressing ambiguity resulting from multiple meanings of words in historical texts. Therefore, we have developed a set of annotation guidelines and provided annotators with an objective reference translation. The average Kappa coefficient after multiple cross-validation is 68.49{\%}, indicating high quality and consistency. We conducted various tasks and comparative experiments on established baseline models for historical ED in classical Chinese. The results showed that BERT+CRF had the best performance on sequence labeling task, with an f1-score of 76.10{\%}, indicating potential for further improvement. 1Introduction{''}",
    language = "English",
}
```

[点击这里查看论文 | Click here to view the paper](https://aclanthology.org/2023.ccl-1.74/)
