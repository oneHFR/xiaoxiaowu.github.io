<table>
    <tr>
        <td valign="top" width="500">
            <p><b>Read Data:</b> 0825</p>
        </td>
        <td valign="top" width="500" colspan="5">
            <p><b>Publication:</b> CVPR 2021</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <b>Title:</b>
            <p>Verifiability and Predictability: Interpreting Utilities of Network Architectures for Point Cloud Processing</p>
            <b>Participants:</b>
            <p>Wen Shen, Zhihua Wei, Shikun Huang, Binbin Zhang, Panyue Chen, Ping Zhao, Quanshi Zhang</p>
        </td>
    </tr>
    <tr>
        <td colspan="6" valign="top" width="1000">
            <p><b>Aim:</b></p>
            <p>研究目标是在中间层架构和它的效用之间架起一座桥梁。对三维点云处理架构效用进行严格定量的验证</p>
            <p><b>Research Question:</b></p>
            <p>从DNN表示能力的角度探索和验证每个特定中间层架构的效用，仍然是最先进算法的重大挑战。本文提出了一种定量诊断中间层网络体系结构效用的方法，为体系结构设计提供了新的思路。</p>
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
