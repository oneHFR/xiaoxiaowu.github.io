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
<a href = "https://paperswithcode.com/dataset/sun-rgb-d">[SUN RGB]</a>&nbsp;&nbsp;&nbsp;&nbsp; <a href = "https://paperswithcode.com/dataset/scannet">[ScanNet</a>
</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <p><b>Introduction:</b></p>
            <p>

1. 点云检测器在有限数量对象上训练 无法扩展到 现实丰富的对象 // Current SOTA point-cloud detectors are trained on a limited classes ≠ classes in the real world. <br>
&nbsp;&nbsp;&nbsp;&nbsp;↪️检测器不能推广看不见对象 // detectors fail to generalize to   **`unseen object`**   classes <br>

2. 开放词汇表检测需要模型学习一般的表示并将其与文本联系 // open-vocabulary detection requires the model to learn general representations and relate those representations to text cues. <br>
&nbsp;&nbsp;&nbsp;&nbsp;↪️点云领域数据收集和注释的困难 //  the difficulty of both data collection and annotation. <br>
&nbsp;&nbsp;&nbsp;&nbsp;↪️阻碍点云检测器学会如何将表示与文本提示连接起来 // hinders point-cloud detectors from learning to connect the representation with text prompts. <br>
&nbsp;
</p>
            <p><b>💡Aim:</b></p>
            <p>

1. 提出 **`OV-3DET`** 利用**图像/视觉语言预训练模型**实现开放词汇表3D点云检测 // propose **`OV-3DET`**, which leverages advanced **`image pre-trained models`**  and **`vision-language pre-trained models`** to achieve **O**pen-**V**ocabulary **3**D point-cloud **DET**ection 
2. **`OV-3DET`** 以点云和文本作为输入，并根据文本描述检测对象 不依赖于大量类标签和文本对的大规模点云数据）
<div align="center">
    <img src="https://raw.githubusercontent.com/oneHFR/xiaoxiaowu.github.io/refs/heads/main/OVD_files/img/1-fig1.png" width="600">
 <em>Fig 1</em>
</div>
&nbsp;
</p>
            <p><b>Research Conclusion:</b></p>
            <p>

1. 提出开放词汇表的点云检测器 **`OV-3DET`**  <br>
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️ 基于任意的文本描述来本地化和命名3D对象 // localize and name 3D objects based on arbitrary text descriptions. <br>
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️ **`OV-3DET`** 的训练不需要任何3D人工注释 // not require any 3D human annotations <br>

2. 通过**二维预先训练的检测器**和**视觉语言模型实现** // **`2D image pre-trained detectors`** and **`vision-language models`**. <br>
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️ 从二维预训练的检测器中定位三维对象 // localize 3D objects from **`2D pre-trained detectors`**, <br>
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️ 通过连接文本和点云嵌入来对检测到的对象进行分类 // classify the detected objects by connecting text and **`point-cloud embeddings`**. <br>
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
💡**① 【Localization 从二维预训练的检测器中获得定位能力 有展开】** <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️ 直接使用二维预训练的检测器在相应的图像中生成一系列二维边界框或二维实例掩码 // directly take **`2D image pre-trained detector`** to generate a series of 2D bounding boxes or 2D instance masks in the corresponding images.  <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️ 根据点云的几何形状将棱台（取景框看fig2）转换为相对紧密的边界盒后 → 预测的二维边界盒作为点云探测器的伪边界盒 // use the **`predicted 2D bounding boxes`** as the **`pseudo bounding box`** of the point-cloud detector after transforming the **`frustum`** into relatively tight bounding box according to the **point-cloud geometry**, as shown in Fig. 2. 

<div align="center" id="fig8">
    <img src="https://raw.githubusercontent.com/oneHFR/xiaoxiaowu.github.io/refs/heads/main/OVD_files/img/1-fig2.png" width="500">
 <em>Fig 2</em>
</div>
&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;    ✔️ 没有使用 class labels predicted by **`2D image pre-trained detector`** <br>

&nbsp;&nbsp;&nbsp;&nbsp;    ✔️ 使用粗糙的二维边界框或二维实例掩码来监督3D点云检测器来学习定位3D对象 // use the coarse 2D bounding boxes or 2D instance masks to supervise **`3D point-cloud detectors`** to learn localizing 3D objects. <br>



💡**② 【Classification 跨模态将点云对象进行分类】** <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️ 提出一种 **去偏三重态跨模态对比学习方法** 来将点云、图像和文本联系起来 // propose a **`de-biased triplet cross-modal contrastive learning method`** to connect the modalities among point-cloud, image, and text <br>
&nbsp;&nbsp;&nbsp;&nbsp;✔️ 使点云检测器能够将对象与相应的文本描述联系起来 // **`point-cloud detector`** is able to relate the objects with corresponding text descriptions. <br>
&nbsp;&nbsp;&nbsp;&nbsp;✔️ 在推理过程中，只使用点云检测器和文本提示 // During inference, only **`point-cloud detector`** and  **`text prompts`** are used. <br>

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

#### 3.2 Notation and Preliminaries
$T$ ➡️ text <br>
$I$ ➡️ image <br>
$P$ ➡️ point-cloud <br>
$I \in \mathbb{R}^{3 \times H \times W}$, $P = \{p_i \in \mathbb{R}^3, i = 1, 2, 3, \dots, N\}$, where $N$ is the point number in the point-cloud. <br>

During training, the unlabeled point-clouds dataset with its paired image is used, denotes as <br>

$D^{pc}$ = ${{P_j}}^{|D_{pc}|}_{j=1}$ 

$D^{img}$  = ${I_j}^{|D_{img}|}_{j=1}$

【还有一些没写】<br>

Perform open-vocabulary classification by comparing between $f_{1D}$ (text feature) and $f_{3D}$, where $f_{3D}$ represents 


#### 3.3 Learn to Localize 3D Objects from 2D Pre-trained Detector
1. 对于$D^{pc}$和$D^{img}$一对图像与点云 ➡️ 2D预训练探测器首先预测一系列的2D边界框或实例掩码 // For a pair of image and point-cloud from $D^{pc}$ and $D^{img}$ ➡️ 2D pre-trained detectors first predict a series of 2D bounding boxes or instance masks, if available.

2. 将2D边界框反向投影到三维空间 ➡️ 得到3D框 // Back-project the 2D bounding box into 3D space ➡️ the frustum（棱台状）3D box that could not tightly enclose the 3D object, as shown in [Fig. 2](#fig8)

3. 缩小三维边界框 ➡️ 利用点云的几何形状 ➡️ 对棱台内的三维点进行聚类 ➡️ 去除背景点和离群点 // Shrink the 3D bounding box ➡️ leverage the geometry of the point-cloud ➡️ perform clustering on points inside ➡️ remove background and outlier points.

4. $L_{loc} = L_{box}^{3D}(\mathbf {\bar {b}}_{3D}, \hat {\mathbf {b}}_{3D})$,   &nbsp;&nbsp;&nbsp;&nbsp; 
$\mathbf {\bar {b}}_{3D} = cluster(\mathbf {\bar {b}}_{2D} \circ K^{-1})$ <br>
$L_{box}^{3D}$ denotes the bounding box regression
loss used in [3DETR](https://openaccess.thecvf.com/content/ICCV2021/papers/Misra_An_End-to-End_Transformer_Model_for_3D_Object_Detection_ICCV_2021_paper.pdf)


> - $L_{loc}$ 表示局部损失，它依赖于三维伪边界框 $L_{box}^{3D}$ 的计算结果。<br>
> - $L_{box}^{3D}$ 是一个三维边界框回归损失函数，用于训练一个名为3DETR的三维目标检测模型 <br>
> - $\mathbf{\bar{b}}_{3D}$ 是一个三维伪边界框，它通过将二维边界框 $\mathbf{\bar{b}}_{2D}$ 经过逆变换 $K^{-1}$ 后，再进行聚类得到。<br>
> - $\mathbf{\bar{b}}_{2D}$ 是一个二维边界框，由一个预训练的二维检测器预测得到。<br>
> - $\mathbf{\bar{b}}_{3D}$ 包含7个参数，用于表示三维空间中的位置和尺寸信息。<br>
> - $\circ$ 表示矩阵或向量的组合操作。<br>
> - $\hat{\mathbf{b}}_{3D}$ 是真实三维边界框的表示，用于与预测的 $\mathbf{\bar{b}}_{3D}$ 进行比较。<br>

#### 3.4 Learn to Classify 3D Objects from 2D Pre-trained vision-language Model

1. 指导模型根据文本提示从本地边界框中找对应物体 // guide the model to find the objects of interest from localized bounding boxes according to the text prompting.

2. 以图像模态为中介，提出一种去偏三重态交叉模态对比学习（DTCC 文中有详解 此处略）来连接文本和点云 // Take image modality as the intermediary ➡️ a De-biased Triplet Cross Modal Contrastive Learning (DTCC 文中有详解 此处略) ➡️ connect text and point-cloud

#### 3.5 Synopsis Explain (主要解释这个图来串讲上面的method)
1. 训练过程中[**3DETR?**] ➡️ 得到点云预测是一系列具有$ROI$特征$f_{3D}$的3D边界框 $b^{3D}$

2. 基于投影矩阵$K$投影预测的3D边界框$b^{3D}$ ➡️ 对相应的图像补丁进行裁剪Crop ➡️ 将其发送到预先训练好的视觉语言模型[CLIP]中 ➕ 进行文本提示

3. 得到：文本特征$f_{1D}$ ➕ 图像补丁特征$f_{2D}$

4. 利用 **`DTCC`** 来连接$f_{1D}$、$f_{2D}$和$f_{3D}$



<div align="center">
    <img src="https://raw.githubusercontent.com/oneHFR/xiaoxiaowu.github.io/refs/heads/main/OVD_files/img/1-fig3.png" width="700">
 <em>Fig 3</em>
</div>
&nbsp;

<div align="center">
    <img src="https://raw.githubusercontent.com/oneHFR/xiaoxiaowu.github.io/refs/heads/main/OVD_files/img/1-fig4.png" width="400">
 <em>Fig 4</em>
</div>
&nbsp;

<div align="center">
    <img src="https://raw.githubusercontent.com/oneHFR/xiaoxiaowu.github.io/refs/heads/main/OVD_files/img/1-fig8.png" width="400">
 <em>Fig 8</em>
</div>
&nbsp;


### 4.Scripts {23}
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
1️⃣2️⃣3️⃣4️⃣5️⃣6️⃣7️⃣8️⃣9️⃣🔟➡️ ❗⚠️、


[Fig. 2](#fig8)
<div align="center" id="fig8">