### 1. Pick up

1. **`open-vocabulary detection`** ➡️ The goal of **`open-vocabulary detection`** is to identify novel objects based on arbitrary textual descriptions.
2. **`unseen objects`** ➡️ novel objects **`unseen objects`** , namely, not ever defined and trained by the already deployed 3D systems.
3. **`vision-language pre-trained models/detector`** ➡️e.g. [CLIP](https://openai.com/index/clip/)
4. **`2D image pre-trained models`**  ➡️e.g. [Detic](https://arxiv.org/pdf/2201.02605)
5. **`point-cloud detector`** ➡️
6. **`point-cloud embeddings`** ➡️
7. **` `** ➡️
8. **` `** ➡️
9. **` `** ➡️

### 2. Reading table
<table>
    <tr>
        <td valign="top" width="500" colspan="3">
            <p><b>Read Data:</b> 24.09.17</p>
        </td>
        <td valign="top" width="500" colspan="3">
            <p><b>Publication:</b> CVPR 2023</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <b>Title:</b>
            <p>Open-Vocabulary Point-Cloud Object Detection without 3D Annotation
  <a href="https://openaccess.thecvf.com/content/CVPR2023/papers/Lu_Open-Vocabulary_Point-Cloud_Object_Detection_Without_3D_Annotation_CVPR_2023_paper.pdf">[paper]</a>
  <a href="https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/paper/Lu_Open-Vocabulary_Point-Cloud_Object_Detection_Without_3D_Annotation_CVPR_2023_paper.pdf"> [annotation]</a>
<a href = "https://github.com/lyhdet/OV-3DET">[code]</a>
</p>
            <b>Participants:</b>
            <p>Yuheng Lu 1∗, Chenfeng Xu 2∗</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <p><b>Introduction:</b></p>
            <p>

1. 点云检测器在有限数量对象上训练 ≠ 解释现实的对象 // Current SOTA point-cloud detectors are trained on a limited classes ≠ classes in the real world.
↪️检测器不能推广看不见对象 // detectors fail to generalize to   **`unseen object`**   classes
2. 开放词汇表检测需要模型学习一般的表示并将其与文本联系 // open-vocabulary detection requires the model to learn general representations and relate those representations to text cues.
↪️点云领域数据收集和注释的困难 //  the difficulty of both data collection and annotation.
↪️阻碍点云检测器学会如何将表示与文本提示连接起来 // hinders point-cloud detectors from learning to connect the representation with text prompts.
&nbsp;
</p>
            <p><b>💡Aim:</b></p>
            <p>

1. 提出 **`OV-3DET`** 利用**图像/视觉语言预训练模型**实现开放词汇表3D点云检测 // propose **`OV-3DET`**, which leverages advanced **`image pre-trained models`**  and **`vision-language pre-trained models`** to achieve **O**pen-**V**ocabulary **3**D point-cloud **DET**ection 
2. **`OV-3DET`** 以点云和文本作为输入，并根据文本描述检测对象 不依赖于大量类标签和文本对的大规模点云数据）
<div align="center">
    <img src="https://github.com/user-attachments/assets/8e23da74-e5a1-4510-b3f8-3a199a850c4a" width="600">
 <em>Fig 1</em>
</div>
&nbsp;
</p>
            <p><b>Research Conclusion:</b></p>
            <p>

1. 提出开放词汇表的点云检测器 **`OV-3DET`** 
  ✔️ 基于任意的文本描述来本地化和命名3D对象 // localize and name 3D objects based on arbitrary text descriptions.
  ✔️ **`OV-3DET`** 的训练不需要任何3D人工注释 // not require any 3D human annotations

2. 通过**二维预先训练的检测器**和**视觉语言模型实现** // **`2D image pre-trained detectors`** and **`vision-language models`**.
  ✔️ 从二维预训练的检测器中定位三维对象 // localize 3D objects from **`2D pre-trained detectors`**,
  ✔️ 通过连接文本和点云嵌入来对检测到的对象进行分类 // classify the detected objects by connecting text and **`point-cloud embeddings`**.
&nbsp;
</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <p>

~~#### Framework
**`OV-3DET`** is a divide-and conquer method ➡️ two stages
① **`point-cloud detector`** learns to localize the unknown objects
② **`point-cloud detector`** learns to name them according to the text prompts.~~
#### Method
💡① 直接使用二维预训练的检测器在相应的图像中生成一系列二维边界框或二维实例掩码 // directly take **`2D image pre-trained detector`** to generate a series of 2D bounding boxes or 2D instance masks in the corresponding images. 
    ✔️ 没有使用 class labels predicted by **`2D image pre-trained detector`**
    ✔️ 使用粗糙的二维边界框或二维实例掩码来监督3D点云检测器来学习定位3D对象 // use the coarse 2D bounding boxes or 2D instance masks to supervise **`3D point-cloud detectors`** to learn localizing 3D objects.

💡②  提出一种去偏三重态跨模态对比学习方法来将点云、图像和文本联系起来 // propose a **`de-biased triplet cross-modal contrastive learning method`** to connect the modalities among point-cloud, image, and text
✔️ 使点云检测器能够将对象与相应的文本描述联系起来 // **`point-cloud detector`** is able to relate the objects with corresponding text descriptions. 
✔️ 在推理过程中，只使用点云检测器和文本提示 // During inference, only **`point-cloud detector`** and  **`text prompts`** are used.

&nbsp;
</p>
            <p>&nbsp;

</p>
        </td>
    </tr>
    <tr>
        <td valign="top" width="800" colspan="4">
            <p><b>Results:</b></p>
            <p>&nbsp;

</p>
            <p>&nbsp;

</p>
        </td>
        <td valign="top" width="200" colspan="2">
            <p><b>Discussion:</b></p>
        </td>
    </tr>
    <tr>
        <td valign="top" width="800" colspan="4">
            <p><b>Conclusion:</b></p>
            <p>

&nbsp;

</p>
        </td>
        <td valign="top" width="200">
            <p><b>Further:</b></p>
        </td>
    </tr>
</table>


### 3. Ref-paper
1. [PointCLIP: Point Cloud Understanding by CLIP](https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/paper/PointCLIP%20Point%20Cloud%20Understanding%20by%20CLIP.pdf)

2. [PointCLIP V2: Prompting CLIP and GPT for Powerful 3D Open-world Learning](https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/paper/Zhu_PointCLIP_V2_Prompting_CLIP_and_GPT_for_Powerful_3D_Open-world_ICCV_2023_paper.pdf)

&nbsp;

### 4.Scripts
> 下面是github文本框的markdown强调用法举例？
>这是一个引用块，可以用来高亮显示重要信息。
- 重要的事项1
这是普通文本，而`这是行内代码`。
1.*这是斜体文本* 2._这也是斜体文本_
1.**这是加粗的文本** 2.__这也是加粗的文本__
```python
def hello_world():
    print("Hello, world!")
```
**`open-vocabulary detection`**
[paper](https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/paper/Lu_Open-Vocabulary_Point-Cloud_Object_Detection_Without_3D_Annotation_CVPR_2023_paper.pdf)
😈 → ▶️➡️↪️➕✔️
1️⃣2️⃣3️⃣4️⃣5️⃣6️⃣7️⃣8️⃣9️⃣🔟➡️ ❗⚠️



