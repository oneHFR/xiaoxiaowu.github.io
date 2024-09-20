### 0. To Do

1. 数学公式的输入和理解  ➡️  论文数学表达式的基本理解


### 1. Pick up

1. **`CLIP`** ➡️ match images with their corresponding texts in
open-vocabulary settings
2. **`Open Vocabulary Learning`** ➡️ [[CSDN]](!https://blog.csdn.net/jiaoyangwm/article/details/132157056) [[OVD综述]](!https://arxiv.org/pdf/2307.09220) [[OVL综述]](!https://arxiv.org/pdf/2306.15880)
3. **`Zero-Shot Learning`** / **`Few-Shot Learning`** ➡️ [[video -IBM]](!https://www.youtube.com/watch?v=pVpr4GYLzAo) 该视频也提及到了embedding space<br>
[[Medium-Open-Vocabulary Learning vs. Zero-Shot Learning]](!https://medium.com/@fceydayildiz/open-vocabulary-learning-vs-zero-shot-learning-0e1dce3c5518) Zero-shot learning approaches are designed to learn this **intermediate semantic layer**, the **attributes**, and apply them at inference time to predict new classes, provided with their description in terms of these attributes <br>
（理解有点狭隘，局限在初级的detection→）能不能理解为在训练过程中能够意识到这个是没有见过的而不是把它归类为已知的某个label上 并且使之可以通过某个环节分类出这个新类 // The objective of zero-shot learning is to enable recognition of “unseen” objects which are not adopted during training.

### 2. Reading table
<table>
    <tr>
        <td valign="top" width="500" colspan="3">
            <p><b>Read Data:</b> 24.09.17</p>
        </td>
        <td valign="top" width="500" colspan="3">
            <p><b>Publication:</b> CVPR 2021</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <b>Title:</b>
            <p>PointCLIP: Point Cloud Understanding by CLIP
  <a href="https://openaccess.thecvf.com/content/CVPR2022/papers/Zhang_PointCLIP_Point_Cloud_Understanding_by_CLIP_CVPR_2022_paper.pdf">[paper]</a>
  <a href="https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/paper/PointCLIP%20Point%20Cloud%20Understanding%20by%20CLIP.pdf"> [annotation]</a>
<a href = "https://github.com/ZrrSkywalker/PointCLIP">[code1]</a>
<a href = "https://paperswithcode.com/paper/pointclip-point-cloud-understanding-by-clip">[code2]</a>
</p>
            <b>Participants:</b>
            <p>Renrui Zhang∗1, Ziyu Guo∗2</p>
</p>
            <b>Dataset:</b>
            <p> ModelNet10 and ModelNet40 &nbsp;&nbsp;&nbsp;&nbsp;
<a href = "https://paperswithcode.com/dataset/modelnet">[ModelNet_1]</a>&nbsp;&nbsp;&nbsp;&nbsp; <a href = "https://modelnet.cs.princeton.edu/">[ModelNet_2]</a>
</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <p><b>Introduction:(背景知识/限制)</b></p>
            <p>

1.  与基于网格的二维图像数据不同，三维点云存在空间稀疏性和不规则分布的问题，阻碍直接从二维域的转移 //<br>
2D image data ➡️ grid-based<br>
3D point clouds ➡️ space sparsity and irregular distribution <br>
&nbsp;&nbsp;&nbsp;&nbsp;↪️ hinder direct methods transfer from 2D domain <br>
<!-- &nbsp;&nbsp;&nbsp;&nbsp;↪️ //  <br> -->
2.  ModelNet40有9,843个样本和40个类 + ImageNet有100万个样本和1000个类 ➡️ 进行预训练三维网络的迁移学习是非常困难的 <br>

3.  大规模的新捕获点云数据包含大量训练分类器的“看不见”类别对象 ➡️ 如果用传统的类PointNet网络训练则遇到一个陌生物体就需要训练 //  large-scale newly captured point cloud data contain a large number of objects of “unseen” categories to the trained classifier<br>
<!-- &nbsp;&nbsp;&nbsp;&nbsp;↪️ //  <br> -->


</p>
    <p><b>💡Abstract:</b></p>
    <p>文章在intro部分也自己总结了本文贡献4项 第四项就是常规的跑实验

1.  提出PointCLIP ➡️ 将点云投影到不需要渲染的多视图深度图中来编码点云 ➡️ 并聚合视图方向的零镜头预测 ➡️ 实现从二维到三维的知识转移。// propose PointCLIP which conducts alignment between CLIP encoded point cloud and 3D category texts ➡️ encode a point cloud by projecting it into multi-view depth maps without rendering ➡️ aggregate the view-wise zero-shot prediction ➡️ achieve knowledge transfer from 2D to 3D <br>

2.  设计一个视图间适配器 ➡️ 更好地提取全局特征，并自适应地将从3D学习到的少镜头知识融合到2D预训练的CLIP中 ➡️ 通过在少镜头设置中微调轻量级适配器 ➡️ 提高PointCLIP的性能 // design an inter-view adapter  ➡️ better extract the global feature and adaptively fuse the few-shot knowledge learned from 3D into CLIP pre-trained in 2D ➡️ by fine-tuning the lightweight adapter in the few-shot settings ➡️ improve the performance of PointCLIP <br>

3.  观察了PointCLIP与经典的三维监督网络之间的互补性 ➡️ 通过简单的集成，PointCLIP提高了基线的性能 // observe the complementary property between PointCLIP and classical 3D-supervised networks ➡️ By simple ensembling, PointCLIP boosts baseline’s
performance.<br>

<!-- <div align="center">
    <img src="" width="600">
 <em>Fig 2 Pipeline</em>
</div> -->
&nbsp;
</p>
            <p><b>Research Conclusion:</b></p>
            <p>

1.   <br>
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️  //  <br>
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️  //  <br>

2.   <br>
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️  //  <br>
&nbsp;&nbsp;&nbsp;&nbsp;  ✔️  //  <br>
&nbsp;
</p>
        </td>
    </tr>
    <tr>
        <td valign="top" width="1000" colspan="5">
            <p><b>Related Work:</b></p>
<p>

**1. Zero-shot Learning in 3D** <br>
【待总结】<br>

**2. Transfer Learning** <br>
【待总结】<br>

**3. Deep Neural Networks for Point Cloud** <br>
【待总结】<br>
【以前的】<br>
【本文的】将原始点投影到图像平面上，并根据垂直距离设置其像素值，得到深度图像，可以忽略 <br>

</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
                    <p><b>Method:</b></p>
            <p>【Intro部分有部分步骤介绍 截取一段 看看后面详细描述能不能借此加深理解】简单地将每个点投影到一系列预定义的图像平面上，以生成散射深度图 // proecting each point onto a series of pre-defifined image planes to generate scatter depth maps

💡**3.1. A Revisit of CLIP** <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  CLIP通过训练将图像与其相应文本描述匹配 // CLIP is trained to match images with their corresponding natural language descriptions.<br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  其中有两个独立的编码器 visual and textual features encoding  ➡️ 训练时，给定一批图像和文本，CLIP提取它们的特征，并学习在嵌入空间中对比它们 <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  确保全面，收集了4亿对训练图像文本对，使得能将图像与开放词汇表中的任何语义概念对齐，以进行OSC <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  训练过程没有新照片同时冻结的预训练编码器 // The whole process does not require new training images, but achieves promising zero-shot classification performance only by frozen pretrained encoders <br>

<div align="center" id="fig2">
    <img src="https://raw.githubusercontent.com/oneHFR/xiaoxiaowu.github.io/refs/heads/main/OVD_files/img/2-fig2.png" width="700">
 <em><br>Fig 2. Pipeline <br></em>
</div>
&nbsp;

💡**3.2 Point Cloud Understanding by CLIP** <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  **① Bridging the Modal Gap** <br>
- 多个视角投影获得深度图像的方式消除模态gap <br>
- 投影深度图来自原始点，不包含颜色信息，是分散的深度值，降低耗时和计算成本 <br>
- 这是一种轻量化的跨模态的融合 <br>

&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  **② Zero-shot Classification** <br>
- 【待整理】<br>
- 此处数学公式结合代码理解 <br>


<div align="center" id="fig2">
    <img src="https://raw.githubusercontent.com/oneHFR/xiaoxiaowu.github.io/refs/heads/main/OVD_files/img/2-fig3.png" width="500">
 <em><br>Fig 3. structure of Inter-view Adapter <br></em>
</div>
&nbsp;

💡**3.3 Inter-view Adapter for PointCLIP** <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  性能还是比不过fully-trained 3D neural networks，故进行局部优化 <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  参考NLP和CCLIP-Adapter对下游任务的预训练模型进行微调，在PointCLIP上添加了一个三层MLP即Inter-view Adapter，以进一步提高其在Few shots设置下的性能 <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  对于训练，我们冻结了CLIP的视觉和文本编码器，并通过交叉熵损失对the learnable adapter进行了微调 <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  The residual style adapter infuses newly-learned 3D few-shot knowledge with that of 2D pre-trained CLIP <br>

💡**3.4. Multi-knowledge Ensembling** <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  简单集成后有增强理解的作用，可当插件 <br>

&nbsp;
</p>
</td>
    </tr>
    <tr>
        <td valign="top" width="1000" colspan="5">
            <p><b>Expriment Results:</b></p>
            <p>&nbsp;

</p>
            <p>&nbsp;

</p>
        </td>
    </tr>
    <tr>
        <td valign="top" width="1000" colspan="5">
            <p><b>Further: </b></p>
<p>

</p>
        </td>
    </tr>
</table>


### 3. Ref-paper
1. [待修改！](https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/paper/PointCLIP%20Point%20Cloud%20Understanding%20by%20CLIP.pdf)

2. [待修改！](https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/paper/Zhu_PointCLIP_V2_Prompting_CLIP_and_GPT_for_Powerful_3D_Open-world_ICCV_2023_paper.pdf)

&nbsp;



### 4. Scripts
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
