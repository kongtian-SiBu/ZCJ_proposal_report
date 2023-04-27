HEO-Essays文件夹内包含一些本人调研高轨接收机时查阅的文献，部分文献非常具有学习价值，罗列如下：

1. 高轨卫星信号可用性分析_卢克文_王新龙 2021
2. 高轨航天器GNSS技术发展_王猛 2020

这两篇文章对高轨GNSS的情况有非常全面的调研，调研的内容包含信号功率、卫星可见性、几何分布等。在《高轨航天器GNSS技术发展》中，作者用表格的形式详细列举了高轨航天器在轨试验的情况，并对高轨使用的弱信号捕获和跟踪算法进行了综述。这篇文章还针对事后精密定位和高轨差分定位技术进行了调研。
而《高轨卫星信号可用性分析》文章以AO-40高轨接收机为例分析了全弧段多普勒和多普勒变化率的最大值和平均值，具有一定的参考价值。
我们在进行调研的时候完全可以参考这两篇文章的形式。

3. Improvement of global navigation satellite system signal acquisition using different grade inertial measurement units for high dynamic applications 2012
4. Performance Analysis of Global Navigation Satellite System Signal Acquisition Aided by different grade Inertial Navigation System under Highly Dynamic Conditions 2017

关于INS辅助GNSS信号失锁后重新捕获这一具体的课题，相关论文数量不多，而且在研究思路和研究方法上几乎也是毫无区别。此处列出两篇具有一定代表性的论文，阅读难度较小，但对于初学者比如我来说很有参考价值。

编号为3的这篇文章使用不同误差水平的INS来辅助GNSS信号重捕，缩小了信号频率搜索的范围(由于本文使用并行码相位捕获，因此未研究码相位搜索的问题)。通过仿真接收机运动轨迹，比较在给定的失锁时间下，不同误差水平的INS辅助分别对应多大的频率搜索范围。本文进行了如下的假设：信号失锁的那一时刻，INS无初始误差；信号失锁期间，接收机的位置和速度误差全部由INS引起(零偏、零偏不稳定性、随机游走)，无其他误差；在信号捕获时，不考虑信号捕获所需的时间段内INS的发散。根据本文所仿真的接收机轨迹来看，应该是个机载接收机(从万米高空降落),因此这些假设比较合理。本文通过仿真给出的数据具有参考价值。
