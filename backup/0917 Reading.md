### 0. To Do

1. 数学公式的输入和理解  ➡️  论文数学表达式的基本理解
2. 代码没有跑过  ➡️  Pytorch的入门
3. 在网页上编辑还是太难了 转到本地VScode会不会快捷键缩进之类好一些？  ➡️  及时渲染的插件

### 1. Pick up

1. **`open-vocabulary detection`** ➡️ The goal of **`open-vocabulary detection`** is to identify novel objects based on arbitrary textual descriptions.
&nbsp;&nbsp;&nbsp;&nbsp;  ➡️ **`open-vocabulary detection`** (or known as zero-shot ) targets to detect the novel classes that are not provided labels during training which usually accompanied by arbitrary text description // 开放词汇表目标检测 目标为检测出在训练中没有提供标签的新类 通常伴随着任意的文本描述
2. **`unseen objects`** ➡️ novel objects **`unseen objects`** , namely, not ever defined and trained by the already deployed 3D systems.
4. **`vision-language pre-trained models/detector`** ➡️e.g. [CLIP](https://openai.com/index/clip/)
5. **`2D image pre-trained models`**  ➡️e.g. [Detic](https://arxiv.org/pdf/2201.02605)&nbsp;&nbsp; [Mask R-CNN](https://openaccess.thecvf.com/content_ICCV_2017/papers/He_Mask_R-CNN_ICCV_2017_paper.pdf)&nbsp;&nbsp; [Fast R-CNN](https://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Girshick_Fast_R-CNN_ICCV_2015_paper.pdf) etc.
6. **`point-cloud detector`** ➡️
7. **`image-text pairs`** ➡️
8. **`semantics`** ➡️
9. **`embedding layer`** ➡️
10. **`point-cloud embeddings`** ➡️
11. **` `** ➡️
12. **` `** ➡️
13. **` `** ➡️

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
</p>
            <b>Dataset:</b>
            <p>
<a href = "https://paperswithcode.com/dataset/sun-rgb-d">
<b>[SUN RGB]</b></a>&nbsp;&nbsp;&nbsp;&nbsp; <a href = "https://paperswithcode.com/dataset/scannet">
<b>[ScanNet]</b></a>
</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <p><b>Introduction:</b></p>
            <p>

1. 点云检测器在有限数量对象上训练 无法扩展到 现实丰富的对象 // Current SOTA point-cloud detectors are trained on a limited classes ≠ classes in the real world.
&nbsp;&nbsp;&nbsp;&nbsp;↪️检测器不能推广看不见对象 // detectors fail to generalize to   **`unseen object`**   classes
2. 开放词汇表检测需要模型学习一般的表示并将其与文本联系 // open-vocabulary detection requires the model to learn general representations and relate those representations to text cues.
&nbsp;&nbsp;&nbsp;&nbsp;↪️点云领域数据收集和注释的困难 //  the difficulty of both data collection and annotation.
&nbsp;&nbsp;&nbsp;&nbsp;↪️阻碍点云检测器学会如何将表示与文本提示连接起来 // hinders point-cloud detectors from learning to connect the representation with text prompts.
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
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️ 基于任意的文本描述来本地化和命名3D对象 // localize and name 3D objects based on arbitrary text descriptions.
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️ **`OV-3DET`** 的训练不需要任何3D人工注释 // not require any 3D human annotations

2. 通过**二维预先训练的检测器**和**视觉语言模型实现** // **`2D image pre-trained detectors`** and **`vision-language models`**.
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️ 从二维预训练的检测器中定位三维对象 // localize 3D objects from **`2D pre-trained detectors`**,
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️ 通过连接文本和点云嵌入来对检测到的对象进行分类 // classify the detected objects by connecting text and **`point-cloud embeddings`**.
&nbsp;
</p>
        </td>
    </tr>
    <tr>
        <td valign="top" width="1000" colspan="5">
            <p><b>Related Work:</b></p>
<p>

**1. Open-Vocabulary 2D and 3D Detection**
【待总结】

**2. Weakly-Supervised Detection**
【待总结】

</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <p>

~~#### Framework Overview:
**`OV-3DET`** is a divide-and conquer method ➡️ two stages
① **`point-cloud detector`** learns to localize the unknown objects
② **`point-cloud detector`** learns to name them according to the text prompts.~~

#### Method:（和·framework的序号顺序是一致的）
💡**① 【Localization 从二维预训练的检测器中获得定位能力】**
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️ 直接使用二维预训练的检测器在相应的图像中生成一系列二维边界框或二维实例掩码 // directly take **`2D image pre-trained detector`** to generate a series of 2D bounding boxes or 2D instance masks in the corresponding images. 
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️ 根据点云的几何形状将棱台（取景框看fig2）转换为相对紧密的边界盒后 → 预测的二维边界盒作为点云探测器的伪边界盒 // use the **`predicted 2D bounding boxes`** as the **`pseudo bounding box`** of the point-cloud detector after transforming the **`frustum`** into relatively tight bounding box according to the **point-cloud geometry**, as shown in Fig. 2.

<div align="center">
    <img src="https://github.com/user-attachments/assets/14935857-38d9-4714-962c-9104438bb1e9" width="500">
 <em>Fig 2</em>
</div>
&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;    ✔️ 没有使用 class labels predicted by **`2D image pre-trained detector`**
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️ 使用粗糙的二维边界框或二维实例掩码来监督3D点云检测器来学习定位3D对象 // use the coarse 2D bounding boxes or 2D instance masks to supervise **`3D point-cloud detectors`** to learn localizing 3D objects.


💡**② 【Classification 跨模态将点云对象进行分类】**
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️ 提出一种 **去偏三重态跨模态对比学习方法** 来将点云、图像和文本联系起来 // propose a **`de-biased triplet cross-modal contrastive learning method`** to connect the modalities among point-cloud, image, and text
&nbsp;&nbsp;&nbsp;&nbsp;✔️ 使点云检测器能够将对象与相应的文本描述联系起来 // **`point-cloud detector`** is able to relate the objects with corresponding text descriptions. 
&nbsp;&nbsp;&nbsp;&nbsp;✔️ 在推理过程中，只使用点云检测器和文本提示 // During inference, only **`point-cloud detector`** and  **`text prompts`** are used.

&nbsp;
</p>
            <p>&nbsp;

</p>
        </td>
    </tr>
    <tr>
        <td valign="top" width="1000" colspan="5">
            <p><b>Results:</b></p>
            <p>&nbsp;

</p>
            <p>&nbsp;

</p>
        </td>
    </tr>
    <tr>
        <td valign="top" width="1000" colspan="5">
            <p><b>Further: (ablation study 只简介设计与操作和所得结果)</b></p>
<p>

 #### ablation

</p>
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



