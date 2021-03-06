模拟人类实际神经网络的数学方法问世以来，人们已慢慢习惯了把这种人工神经网络直接称为神经网络。
神经网络在系统辨识、模式识别、智能控制等领域有着广泛而吸引人的前景，特别在智能控制中，人们对神经网络的自学习功能尤其感兴趣，
并且把神经网络这一重要特点看作是解决自动控制中控制器适应能力这个难题的关键钥匙之一。

BP（Back Propagation）神经网络是1986年由Rumelhart和McCelland为首的科学家小组提出，
是一种按误差逆传播算法训练的多层前馈网络，是目前应用最广泛的神经网络模型之一。
BP网络能学习和存贮大量的输入-输出模式映射关系，而无需事前揭示描述这种映射关系的数学方程。
它的学习规则是使用最速下降法，通过反向传播来不断调整网络的权值和阈值，使网络的误差平方和最小。
BP神经网络模型拓扑结构包括输入层（input）、隐层(hidden layer)和输出层(output layer)。

若从速度的角度出发，人脑神经元之间传递信息的速度要远低于计算机，前者为毫秒量级，而后者的频率往往可达几百兆赫。
但是，由于人脑是一个大规模并行与串行组合处理系统，因而，在许多问题上可以作出快速判断、决策和处理，其速度则远高于串行结构的普通计算机。
人工神经网络的基本结构模仿人脑，具有并行处理特征，可以大大提高工作速度。

神经网络的研究内容相当广泛，反映了多学科交叉技术领域的特点。主要的研究工作集中在以下几个方面：
（1）生物原型研究。从生理学、心理学、解剖学、脑科学、病理学等生物科学方面研究神经细胞、神经网络、神经系统的生物原型结构及其功能机理。
（2）建立理论模型。根据生物原型的研究，建立神经元、神经网络的理论模型。其中包括概念模型、知识模型、物理化学模型、数学模型等。
（3）网络模型与算法研究。在理论模型研究的基础上构作具体的神经网络模型，以实现计算机模拟或准备制作硬件，包括网络学习算法的研究。这方面的工作也称为技术模型研究。
（4）人工神经网络应用系统。在网络模型与算法研究的基础上，利用人工神经网络组成实际的应用系统，例如，完成某种信号处理或模式识别的功能、构作专家系统、制成机器人等等。

BP (Back Propagation)神经网络，即误差反传误差反向传播算法的学习过程，由信息的正向传播和误差的反向传播两个过程组成。
输入层各神经元负责接收来自外界的输入信息，并传递给中间层各神经元；中间层是内部信息处理层，负责信息变换，根据信息变化能力的需求，中间层可以设计为单隐层或者多隐层结构；
最后一个隐层传递到输出层各神经元的信息，经进一步处理后，完成一次学习的正向传播处理过程，由输出层向外界输出信息处理结果。当实际输出与期望输出不符时，进入误差的反向传播阶段。
误差通过输出层，按误差梯度下降的方式修正各层权值，向隐层、输入层逐层反传。周而复始的信息正向传播和误差反向传播过程，是各层权值不断调整的过程，也是神经网络学习训练的过程，此过程一直进行到网络输出的误差减少到可以接受的程度，或者预先设定的学习次数为止。

BP神经网络模型BP网络模型包括其输入输出模型、作用函数模型、误差计算模型和自学习模型。
（1）节点输出模型
隐节点输出模型：Oj=f(∑Wij×Xi-qj) (1)
输出节点输出模型：Yk=f(∑Tjk×Oj-qk) (2)
f-非线形作用函数；q -神经单元阈值。
（2）作用函数模型
作用函数是反映下层输入对上层节点刺激脉冲强度的函数又称刺激函数，一般取为(0,1)内连续取值Sigmoid函数： f(x)=1/(1+e乘方（-x）) （3）
（3）误差计算模型
误差计算模型是反映神经网络期望输出与计算输出之间误差大小的函数：
tpi- i节点的期望输出值；Opi-i节点计算输出值。
（4）自学习模型
神经网络的学习过程，即连接下层节点和上层节点之间的权重矩阵Wij的设定和误差修正过程。BP网络有师学习方式-需要设定期望值和无师学习方式-只需输入模式之分。自学习模型为
△Wij(n+1)= h ×Фi×Oj+a×△Wij(n) （5）
h -学习因子；Фi-输出节点i的计算误差；Oj-输出节点j的计算输出；a-动量因子。

神经网络可以用作分类、聚类、预测等。神经网络需要有一定量的历史数据，通过历史数据的训练，网络可以学习到数据中隐含的知识。
在你的问题中，首先要找到某些问题的一些特征，以及对应的评价数据，用这些数据来训练神经网络。
虽然BP网络得到了广泛的应用，但自身也存在一些缺陷和不足，主要包括以下几个方面的问题。
首先，由于学习速率是固定的，因此网络的收敛速度慢，需要较长的训练时间。
对于一些复杂问题，BP算法需要的训练时间可能非常长，这主要是由于学习速率太小造成的，可采用变化的学习速率或自适应的学习速率加以改进。
其次，BP算法可以使权值收敛到某个值，但并不保证其为误差平面的全局最小值，这是因为采用梯度下降法可能产生一个局部最小值。
对于这个问题，可以采用附加动量法来解决。
再次，网络隐含层的层数和单元数的选择尚无理论上的指导，一般是根据经验或者通过反复实验确定。
因此，网络往往存在很大的冗余性，在一定程度上也增加了网络学习的负担。
最后，网络的学习和记忆具有不稳定性。也就是说，如果增加了学习样本，训练好的网络就需要从头开始训练，对于以前的权值和阈值是没有记忆的。
但是可以将预测、分类或聚类做的比较好的权值保存。

http://www.cnblogs.com/luxiaoxun/archive/2012/12/10/2811309.html

