HEO-Essays文件夹内包含一些本人调研高轨接收机时查阅的文献，部分文献非常具有学习价值，罗列如下：

1. 高轨卫星信号可用性分析_卢克文_王新龙 2021
2. 高轨航天器GNSS技术发展_王猛 2020

这两篇文章对高轨GNSS的情况有非常全面的调研，调研的内容包含信号功率、卫星可见性、几何分布等。在《高轨航天器GNSS技术发展》中，作者用表格的形式详细列举了高轨航天器在轨试验的情况，并对高轨使用的弱信号捕获和跟踪算法进行了综述。这篇文章还针对事后精密定位和高轨差分定位技术进行了调研。
而《高轨卫星信号可用性分析》文章以AO-40高轨接收机为例分析了全弧段多普勒和多普勒变化率的最大值和平均值，具有一定的参考价值。
我们在进行调研的时候完全可以参考这两篇文章的形式。  


3. Improvement of global navigation satellite system signal acquisition using different grade inertial measurement units for high dynamic applications 2012
4. Performance Analysis of Global Navigation Satellite System Signal Acquisition Aided by different grade Inertial Navigation System under Highly Dynamic Conditions 2017

关于INS辅助GNSS信号失锁后重新捕获这一具体的课题，相关论文数量不多，而且在研究思路和研究方法上几乎也是毫无区别。此处列出两篇具有一定代表性的论文，阅读难度较小，但对于初学者比如我来说很有参考价值。

编号为3的这篇文章使用不同误差水平的INS来辅助GNSS信号重捕，缩小了信号频率搜索的范围(由于本文使用并行码相位捕获，因此未研究码相位搜索的问题)。通过仿真接收机运动轨迹，比较在给定的失锁时间下，不同误差水平的INS辅助分别对应多大的频率搜索范围。本文进行了如下的假设：信号失锁的那一时刻，INS无初始误差；信号失锁期间，接收机的位置和速度误差全部由INS引起(零偏、零偏不稳定性、随机游走)，无其他误差；在信号捕获时，不考虑信号捕获所需的时间段内INS的发散。根据本文所仿真的接收机轨迹来看，应该是个机载接收机(从万米高空降落)，因此这些假设比较合理。本文通过仿真给出的数据具有参考价值。

编号为4的这篇文章实验方案和编号3就没有区别，文章作出的假设也和编号3几乎是一模一样，连接收机运动轨迹仿真都差不多，一个槽点是本文标题说自己研究高动态，结果加速度就那么点，脸都不要了。可能是做出来了硬件实物，不然我感觉这文章能发出来都费劲。本文比前文多研究了INS辅助对码相位搜索范围的缩小，实验数据具有参考价值。

5. Feasibility Study Of GNSS As Navigation System To Reach The Moon 2015
6. Orbital Filter Aiding of a High Sensitivity GPS Receiver for Lunar Mission (ION) 2016
7. GNSS based orbital filter for Earth to Moon transfer orbits 2016

这几篇文章的第一作者Vincenzo Capuano以第一作者的身份代表他们团队发表了一系列关于地月GNSS导航的相关论文，从引用文献中大家也会发现这一点。该团队对于地月导航的研究可以说非常全面，是少有的在信号可用性分析过程中给出接收机参数的文章。但是这些论文中给出的指标是否具有参考价值是一件值得怀疑的事情。本人在2023.4.26号开题答辩的PPT中直接引用了编号6文章中给出的接收机参数，但答辩评审老师却认为这些参数不够合理。因此这些论文中的数据是否可信之后我还会向导师求证。求证之后我会及时更新此页面。【该领域的论文一定要注意是仿真的还是实测的，两者区别很大】

编号5这篇文章研究了从地球到月球的整个弧段(during the whole trajectory to reach the Moon)，使用“Spirent GSS8000”模拟器对GPS L1CA、L5导频、Galileo E1导频和E5导频进行仿真。首先，介绍了接收机轨迹。接收机轨迹设置详见table2、Fig1、Fig2和Fig3，可以看到远地点恰好是月球轨道的高度。其次，给出了接收机从低轨高度上升至月球高度过程中GNSS信号强度的变化、多普勒频移和多普勒变化率的情况。可以看出在低轨范围内多普勒和多普勒变化率较大，而在轨道高度比较高的时候，多普勒变化率比较小(<5Hz/s)。信号强度仿真表明如果灵敏度达到-168.5 dBm(注意单位，dBm而不是dBW; -168.5dBm大约对应5dB-Hz)，则可以地月全程都收得到GNSS信号。接下来，本文对接收机信号捕获(码相位并行捕获算法)与跟踪进行了仿真。设置接收机灵敏度分别为-159dBm、-164dBm、-169dBm(对应大约15dB-Hz、10dB-Hz、5dB-Hz)，为了达到设定的灵敏度，table3和table4给出了-164dBm和-169dBm所采用的接收机相关参数。本文假设使用双频接收来减小电离层的影响，还提到使用轨道滤波器或者INS辅助可以获取更精确的频率估计值，大幅减小频率搜索次数。关于信号跟踪，本文给出了信号跟踪所用的参数(相干积分时间T=0.3s，三阶锁相环Bn=0.5Hz ，码环Bn=0.005Hz)，本文还假设使用了轨道滤波器或者INS进行辅助，因此才可以将环路带宽设置得很窄。仿真表明载噪比大于5dB-Hz时环路就可以成功跟踪信号。【此处老师指出码环的Bn在实际工程中做到0.005Hz有困难】接下来本文对卫星可见性和GDOP值进行了仿真。【老师认为本文最大的问题是未指明导航卫星的天线方向图，即本文公式(1)中的Ltx，这个数值的影响是决定性的。如果Ltx的取值合理，那么本文的分析基本可信】

编号7的图3给出了天线方向图，使用的是GPS Block II-A的天线方向图，解释了上一自然段中提到的问题。

8. GNSS空间服务空域性能评估及辅助增强技术研究 2017 上交博士论文

编号8是一篇研究SSV的博士论文，对SSV的考察非常全面，读起来很像是Capuano的若干论文的集合体。

9. The Multi-GNSS Space Service Volume_NASA 2018

NASA在2018年关于SSV的一篇报告，总结了2018年之前的几年内的高轨任务，分析了GPS的SSV服务能力，并提出了展望。内有大量精美图片，快来COPY。
