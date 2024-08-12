<div align="center">

### CHED
_A Cross-Historical Dataset with a Logical Event Schema for Classical Chinese Event Detection_

</div>

---

<div align="center">

### 数据集说明 | Dataset Description

</div>

---

**数据集说明 | Dataset Description**

本数据集是古代汉语历史事件检测数据集（CHED），旨在帮助研究者对古文历史文本中的事件进行检测与分类。数据集涵盖了《二十四史》中多个历史人物和事件的记录，适用于构建和评估古代历史文本事件检测的算法与模型。

This dataset, named the Classical Chinese Historical Event Dataset (CHED), is designed to aid researchers in detecting and classifying events within classical Chinese historical texts. It covers multiple historical figures and events recorded in the "Twenty-Four Histories," making it suitable for constructing and evaluating algorithms and models for event detection in ancient historical texts.

---

**数据集文件 | Dataset Files**

<div align="center">

| 文件名 | 描述 |
| --- | --- |
| **train.jsonl** | 包含训练数据集，用于模型的训练过程。数据集经过标注，包含了事件触发词及其对应的事件类型标签。 Contains the training dataset used for the model's training process. The dataset is annotated, including event trigger words and their corresponding event type labels. |
| **valid.jsonl** | 包含验证数据集，用于在训练过程中对模型进行验证和调整。数据的标注与训练集一致。 Contains the validation dataset used to validate and adjust the model during training. The annotations are consistent with the training set. |
| **test.jsonl** | 包含测试数据集，用于在模型训练完成后对其性能进行评估。标注方式与训练集和验证集一致。 Contains the test dataset used to evaluate the model's performance after training is complete. The annotation method is consistent with the training and validation sets. |
| **all.jsonl** | 包含整个数据集的所有数据，包括训练集、验证集和测试集的所有内容，适用于全面分析或模型训练时的整体数据使用。 Contains all the data from the entire dataset, including the training, validation, and test sets, suitable for comprehensive analysis or using the entire data during model training. |
| **doc2id.jsonl** | 该文件为文档和对应ID的映射关系，帮助标注或训练时快速定位和检索相关文本。 This file maps documents to their corresponding IDs, aiding in quickly locating and retrieving relevant texts during annotation or training. |
| **label.jsonl** | 该文件定义了数据集中所有可能的事件标签，包含标签的详细信息和分类。 This file defines all possible event labels in the dataset, including detailed information and classification of the labels. |

</div>

---

**数据集格式说明 | Dataset Format Description**

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


---

**论文引用 | Citation**

如果您在研究中使用了该数据集，请引用以下论文：

If you use this dataset in your research, please cite the following paper:

```json
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

</div>

---

**数据分析 | Data Analysis**

1. **数据大小** | **Data Size**

   我们构建的古汉语历史检测数据集，包含来自《二十四史》中61篇文档，61个历史人物。数据集总计包含13,159个句子和236,842个汉字。其中，有8,122个带有事件标签的句子，共计145,973个汉字，并且总共有14,154个标签。

   The dataset we constructed contains 61 documents from the "Twenty-Four Histories" and covers 61 historical figures. It includes a total of 13,159 sentences and 236,842 Chinese characters. Among these, 8,122 sentences are annotated with event labels, totaling 145,973 characters, and there are 14,154 labels in total.

2. **事件逻辑体系构建** | **Event Logical Schema Construction**

   我们构建了一个完整、具有逻辑的古文历史事件类型本体。古文历史事件类型之间是有层次关系的，事件大类之间也是具有联系的，这形成了一个严密的逻辑体系。

   We constructed a comprehensive and logical schema for classical Chinese historical events. The event types are hierarchical and interconnected, forming a coherent logical system.

   二十四史是中国古代各个朝代撰写的官方正史总称，记录了古代中国几千年以来的朝代更替。我们认为，《二十四史》记载的中心主题仍然是围绕政治权力斗争和对权力的追求。

   It is our belief that the central theme of records in the Twenty-Four Histories continues to revolve around political power struggles and the pursuit of authority.

   因此，我们重点以职位事件为核心，进一步将其分为帝位和官位，反应了中国古代君臣的两大关系。政权的更替一般以“军事”事件为主，通过战争夺取政权，又而通过“法律”事件来维持政权，背后又以赋税制度为核心的“经济”事件支持政权。而皇帝为了强化自己政权的合法性，则会通过“祭祀”事件等仪式，比如祭天神，实际上是强调“君权神授”；祭地祗，包括祖先等，实际上是强调以嫡长子为核心的血缘关系继承制来强化政权的延续性；而祭人鬼，比如古代的圣贤（孔子等）是为政权提供了正统统治思想来源。

   Therefore, we focus on the **_Position_** events as the core, which are further divided into **_imperial position_** and **_official position_**, reflecting the two major relationships between emperors and officials in ancient China. The transition of political power is generally reflected in **_Military_** events, which seize power through warfare and maintain power through **_Law_** events, supported by the **_Economy_** events that are centered around the taxation system. In order to strengthen the legitimacy of their political power, emperors often hold **_Ritual_** events, including the worship of heavenly deities to emphasize the divine right of emperors, the worship of ancestral spirits to emphasize the continuity of their bloodline-based inheritance system centered around the eldest son, and the worship of sages (e.g. Confucius) to provide a source of legitimate political ideology for their regimes.

   君和臣之间是有联系的，从上至下，在以皇权为核心的政治制度下，通过“移动”，“交流”事件来实现政令的上传下达和措施的实施废止。“人生”事件主要是指皇帝和大臣的一生，这是二十四史“本纪”“列传”“世家”中主要记录的人物。

   In a political system that centers around imperial power, there exists a relationship between emperors and officials, where **_Movement_** and **_Communication_** events are utilized to facilitate the transmission of political orders and the implementation or abolition of measures from top to bottom. The **_Life_** events mainly refer to the lives of the emperor and the officials, which are the main records of figures in the Benji (本纪), Liezhuan (列传), and Shijia (世家) sections of the Twenty-Four Histories.

   同时，二十四史中对于自然事件的记录，主要是自然事件如何影响了皇帝和大臣的行为。例如《宋史》卷一，本纪第一，太祖一中“辛亥，澶、滑、卫、魏、晋、绛、蒲、孟八州饥，命发廪振之。”，这句话中包含了“饥荒”事件，由于八个州发生了饥荒，则影响了皇帝接下来的行为，即下令打开粮仓，救济百姓。

   At the same time, the records of **_Nature_** events in the Twenty-Four Histories mainly focus on how natural events affected the behavior of the emperor and the officials. For example, in Volume One of Song Shi (宋史), in the Benji (本纪) of Taizu (太祖), the sentence below contains a **_famine_** event, which affected the emperor's subsequent actions, namely, ordering the opening of granaries to provide relief for the people due to the occurrence of famine in eight provinces.

    (6) 辛亥，澶、滑、卫、魏、晋、绛、蒲、孟八州饥，命发廪振之。

    (*In Xinhai year, there was a famine in eight provinces, including Chanzhou, Huazhou, Weizhou, Jinzhou, Jingzhou, Puqizhou, and Mengzhou. The emperor commanded the opening of granaries to provide relief for the people.*)


**一级类别** | **二级类别** | **三级类别** | **四级类别**
--- | --- | --- | ---
**人生** | 出生 | - | -
**人生** | 结婚 | - | -
**人生** | 生病 | - | -
**人生** | 受伤 | - | -
**人生** | 死亡 | - | -
**人生** | 安葬 | - | -
**人生** | 分封 | - | -
**人生** | 立谥 | - | -
**职位** | 帝位 | 确立 | -
**职位** | 帝位 | 即位 | -
**职位** | 帝位 | 继位 | -
**职位** | 官位 | 任职 | -
**职位** | 官位 | 免职 | -
**职位** | 官位 | 升职 | -
**职位** | 官位 | 降职 | -
**职位** | 官位 | 赏赐 | -
**交流** | 国家交流 | 出使 | -
**交流** | 国家交流 | 盟约 | -
**交流** | 国家交流 | 朝贡 | -
**交流** | 个人交流 | 见面 | -
**交流** | 个人交流 | 商议 | -
**交流** | 个人交流 | 询问 | -
**交流** | 个人交流 | 诏令 | 命令
**交流** | 个人交流 | 诏令 | 下诏
**交流** | 个人交流 | 进言 | -
**交流** | 个人交流 | 派遣 | -
**祭祀** | 祭天神 | - | -
**祭祀** | 祭地祇 | - | -
**祭祀** | 祭人鬼 | - | -
**移动** | 到达 | - | -
**移动** | 停留 | - | -
**移动** | 离开 | - | -
**军事** | 备战 | 出兵 | -
**军事** | 备战 | 驻扎 | -
**军事** | 作战 | 攻击 | 征伐
**军事** | 作战 | 攻击 | 侵袭
**军事** | 作战 | 防守 | -
**军事** | 作战 | 谋反 | -
**军事** | 作战 | 杀害 | -
**军事** | 作战 | 救援 | -
**军事** | 作战 | 撤退 | -
**军事** | 作战 | 俘虏 | -
**军事** | 停战 | 战胜 | -
**军事** | 停战 | 战败 | -
**军事** | 停战 | 投降 | -
**经济** | 赋税 | 征税 | -
**经济** | 赋税 | 减税 | -
**经济** | 赋税 | 免税 | -
**经济** | 买卖 | 买入 | -
**经济** | 买卖 | 卖出 | -
**经济** | 生产 | 耕种 | -
**经济** | 生产 | 打猎 | -
**经济** | 生产 | 建造 | -
**法律** | 制法 | - | -
**法律** | 废法 | - | -
**法律** | 犯罪 | - | -
**法律** | 逮捕 | - | -
**法律** | 赦免 | - | -
**法律** | 处死 | - | -
**法律** | 流放 | - | -
**自然** | 灾害 | 饥荒 | -
**自然** | 灾害 | 地震 | -
**自然** | 灾害 | 水灾 | -
**自然** | 灾害 | 蝗灾 | -
**自然** | 天象 | 日食 | -
**自然** | 天象 | 流星 | -
**自然** | 天气 | - | -


#### 许可证和使用条款 | License and Terms of Use

**许可证 | License**

本数据集使用 [CC BY-NC 4.0 许可证](https://creativecommons.org/licenses/by-nc/4.0/)进行分发。您可以自由使用和分享数据集，但需注明出处，并且仅限于非商业用途。
This dataset is distributed under the [CC BY-NC 4.0 license](https://creativecommons.org/licenses/by-nc/4.0/). You may freely use and share the dataset, but you must provide proper attribution and use it only for non-commercial purposes.

**使用条款 | Terms of Use**

- **数据用途: 数据集仅用于学术研究和教育目的，不得用于商业用途。**
  Data Usage: The dataset is intended for academic research and educational purposes only, and must not be used for commercial purposes.

- **数据保护: 使用数据时，请确保遵循相关数据保护法规和伦理规范。**
  Data Protection: When using the data, please ensure compliance with relevant data protection regulations and ethical standards.

- **引用要求: 使用数据集进行研究或发布结果时，请确保正确引用数据集和相关论文。**
  Citation Requirements: When using the dataset for research or publishing results, ensure proper citation of the dataset and relevant papers.

