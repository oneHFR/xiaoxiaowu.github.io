> **PICK UP**

1. The **`goal of open-vocabulary detection`** is to identify novel objects based on arbitrary textual descriptions.
2. 




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
            <p>Open-Vocabulary Point-Cloud Object Detection without 3D Annotation</p>
            <b>Participants:</b>
            <p>Yuheng Lu 1∗, Chenfeng Xu 2∗</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <p><b>Aim:</b></p>
            <p>研究目标是在中间层架构和它的效用之间架起一座桥梁。对三维点云处理架构效用进行严格定量的验证</p>
            <p><b>Research Conclusion:</b></p>
            <p>

1. propose an open-vocabulary point-cloud detector, dubbed OV-3DET,

> which is capable of localizing and naming 3D objects based on arbitrary text descriptions.
> notrequire any 3D human annotations

2. achieve this by resorting to well-established 2D pre-trained detectors and vision-language models.

</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <p><b>Method:</b></p>
            <p>在可验证性方面，我们设计了新的度量标准来量化现有中间层架构的效用，以证明直观的见解。在可预测性方面，我们进一步使用验证的洞见来修正其他网络，以改善其效用。需要注意的是，中间层架构的修改一般不会改变dnn的深度，因此我们消除了深度变化的影响。</p>
            <p>(1)对特定中间层架构的效用提出了一些假设。(2)我们设计了五个度量标准来进行比较研究，以验证这些假设，这为建筑实用功能提供了新的见解。(3)证明验证的假设可以用来修正现有的dnn，提高其效用。</p>
        </td>
    </tr>
    <tr>
        <td valign="top" width="800" colspan="4">
            <p><b>Results:</b></p>
            <p>架构1提高了对抗鲁棒性的实用性。架构2和架构4提高了旋转鲁棒性的实用性。此外，具有体系结构3的网络通常比没有</p>
            <p>增加了架构1的模块，提高了PointNet++、Point2Sequence和RSCNN的对抗鲁棒性。增加了架构2的模块，提高了PointNet++、Point2Sequence和RSCNN的旋转鲁棒性。增加架构3的模块，提高了PointNet++和RSCNN的对抗鲁棒性和邻域一致性。增加了Architecture 4的模块，提高了PointNet++、Point2Sequence和RSCNN的旋转鲁棒性架构3的网络具有更低的邻域不一致性。从更多尺度的背景中提取特征的DNN通常表现出较低的邻域不一致性。</p>
        </td>
        <td valign="top" width="200" colspan="2">
            <p><b>Discussion:</b></p>
        </td>
    </tr>
    <tr>
        <td valign="top" width="800" colspan="4">
            <p><b>Conclusion:</b></p>
            <p>在本文中，我们验证了四种特定的中间层网络架构用于三维点云处理的一些假设。通过比较研究证明了特定架构的实用性，包括旋转鲁棒性、对抗鲁棒性和邻域不一致性。在初步实验中，我们验证了架构2和架构4主要提高了旋转鲁棒性;架构1和架构3对对抗健壮性有积极影响;架构3通常会缓解邻里之间的不一致。这些经过验证的假设已被进一步用于修正现有DNN，以改善其效用。</p>
        </td>
        <td valign="top" width="200">
            <p><b>Further:</b></p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <p><b>Ref:</b></p>
            <p>&nbsp;</p>
        </td>
    </tr>
</table>

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





