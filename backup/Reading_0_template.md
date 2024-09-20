### 0. To Do

1. 数学公式的输入和理解  ➡️  论文数学表达式的基本理解


### 1. Pick up

1. **`CLIP`** ➡️ match images with their corresponding texts in
open-vocabulary settings
2. **` `** ➡️
3. **` `** ➡️

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

2.  大规模的新捕获点云数据包含大量训练分类器的“看不见”类别对象 //  large-scale newly captured point cloud data contain a large number of objects of “unseen” categories to the trained classifier<br>
<!-- &nbsp;&nbsp;&nbsp;&nbsp;↪️ //  <br> -->


</p>
            <p><b>💡Abstract:</b></p>
            <p>文章在intro部分也自己总结了本文贡献4项 第四项就是常规的跑实验

1.  提出PointCLIP ➡️ 将点云投影到不需要渲染的多视图深度图中来编码点云 ➡️ 并聚合视图方向的零镜头预测 ➡️ 实现从二维到三维的知识转移。// propose PointCLIP which conducts alignment between CLIP encoded point cloud and 3D category texts ➡️ encode a point cloud by projecting it into multi-view depth maps without rendering ➡️ aggregate the view-wise zero-shot prediction ➡️ achieve knowledge transfer from 2D to 3D <br>

2.  设计一个视图间适配器 ➡️ 更好地提取全局特征，并自适应地将从3D学习到的少镜头知识融合到2D预训练的CLIP中 ➡️ 通过在少镜头设置中微调轻量级适配器 ➡️ 提高PointCLIP的性能 // design an inter-view adapter  ➡️ better extract the global feature and adaptively fuse the few-shot knowledge learned from 3D into CLIP pre-trained in 2D ➡️ by fine-tuning the lightweight adapter in the few-shot settings ➡️ improve the performance of PointCLIP <br>

3.  观察了PointCLIP与经典的三维监督网络之间的互补性 ➡️ 通过简单的集成，PointCLIP提高了基线的性能 // observe the complementary property between PointCLIP and classical 3D-supervised networks ➡️ By simple ensembling, PointCLIP boosts baseline’s
performance.<br>

<div align="center">
    <img src="" width="600">
 <em>Fig 1</em>
</div>
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

**1. i**
【待总结】

**2. W**
【待总结】

</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
                    <p><b>Method:</b></p>
            <p>

💡**① 【】** <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  //  <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  //  <br>



💡**② 【】** <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  //  <br>
&nbsp;&nbsp;&nbsp;&nbsp;    ✔️  //  <br>

&nbsp;
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
1️⃣2️⃣3️⃣4️⃣5️⃣6️⃣7️⃣8️⃣9️⃣🔟➡️ ❗⚠️、


[Fig. 2](#fig8)
<div align="center" id="fig8">
