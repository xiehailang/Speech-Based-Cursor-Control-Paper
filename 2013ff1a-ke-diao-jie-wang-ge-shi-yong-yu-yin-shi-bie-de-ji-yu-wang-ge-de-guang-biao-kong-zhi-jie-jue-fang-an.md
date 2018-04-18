#可调节网格 - 使用语音识别的基于网格的光标控制解决方案
**摘要    **患有运动障碍的人经常会发现无需使用基于语音的系统，因为它们提供了传统的以鼠标为中心的导航的替代方案。已经开发出少量使用语音识别的基于网格的光标控制系统。这些系统通常在屏幕上叠加编号为3x3的网格，并允许用户通过说出网格编号递归地将光标向下钻至目标位置。虽然3x3网格仍然是标准，但仍然难以确定哪种粒度可以最大限度地提高特定桌面环境的性能，特别是在时间延迟和点击任务错误率方面。这项研究的目的是开发一个可调节粒度的网格，以比较各种网格尺寸的功效，并为用户提供当前仅提供单个默认网格的系统的替代方案。
**关键词    **光标控制，导航，语音识别，网格，人机交互，用户界面，可访问性

##1.引言
鼠标是用于与个人计算机交互的最普遍和成功的输入设备之一，并且易于借助空间导航任务，这对于使用WIMP（窗口，图标，菜单，指点）风格界面的桌面图形用户界面（GUI）是至关重要的。当设计传统的人机界面时，可以忽略对运动障碍用户的独特要求。不幸的是，这一大群用户通常使用鼠标的能力有限或没有能力。阻碍小鼠使用的运动障碍可能由多种情况引起，包括脑性麻痹，帕金森病，脊髓损伤，部分麻痹，关节炎和中风。
本导言的其余部分调查并比较残疾人士的其他形式的输入界面。接下来的论文解决了我们调查的关于基于网格的光标控制界面的控制粒度的具体研究问题。

##1.1可选光标控制系统
由于鼠标控制在许多现代计算机交互中是必需的，因此运动受损的用户必须找到可选的光标控制模式。许多研究已经对光标控制技术进行了研究，眼动仪，头部追踪器，舌操作操纵杆和语音控制系统已作为可能的解决方案进行了探索[14]。最近，神经修复控制已经被研究[4]。
眼睛注视跟踪（EGT）系统直观地利用用户的注视方向来移动光标，但通常需要昂贵的外围输入设备[2]。基于肌电图（EMG）的光标控制系统需要用户将物理EMG电极附加到面部，该面部可监控与特定光标方向相关的肌肉运动[1]。最近对神经假体游标控制的算法改进允许用户用他们的想法控制游标并接近真实手臂的性能，但是这种系统在可用时将需要植入脑传感器[4]。我们对基于语音的系统的兴趣部分是因为除了标准麦克风之外，它们不需要外部设备来促进它们的使用。

##1.2基于语音的光标控制
一个用于个人电脑的全面的基于语音的控制系统需要一个文本输入机制和一个光标控制机制，它们分别提供了标准键盘和鼠标的替代方案[10]。健壮的听写（语音到文本）软件与许多商业软件应用程序捆绑在一起，如Dragon NaturallySpeaking和Windows Speech Recognition，它们都使用自动语音识别（ASR）来生成用于在桌面环境中进行交互的命令。过去的研究表明，ASR系统的生产力在传统用户使用时没有差异，而脊髓损伤导致运动功能丧失的用户则不同[12]。

虽然听写工具近年来有了明显的改进，但将语音映射到可行的光标控制解决方案已被证明更加困难。基于语音的光标控制解决方案已经分化为两种方法：基于方向（例如“向上移动三行”）和基于目标（例如“选择目标”）。

基于方向的解决方案可以是离散或连续的。离散的方法要求用户指定朝这个方向移动的单位的方向和数量。例如，用户可以说：“向左移动3个单位”。通常，这些单位是为适当的上下文指定的。例如，在商业软件Dragon NaturallySpeaking中，用户可以在文字处理应用程序中说“移回两段”。

另一方面，连续的方法要求用户指定光标移动的方向，直到达到“停止”命令。然而，这种方法存在延误。首先，用户必须察觉光标已达到目标。然后用户必须发出一个停止命令，然后电脑必须进行处理。因为有几个延迟出现的机会，这些系统往往是缓慢而容易出错的[11]。由于基于语音的命令倾向于呈现一系列固有的延迟，因此设计了可提前发出“停止”或“单击”命令的预测游标，但未显示对任务完成时间，错误率的显着改进或与标准光标相比用户满意度[7]。

Mihara，Shibayama和Takahashi提出了Migratory Cursor，它使用了使用鬼光标的离散和连续的规范[9]。根据移动的方向，带有编号的重影光标的一行或一列伴随着实际的光标。首先，用户通过使用离散命令（例如，“向右移动三个”）搜索离目标最近的幻影光标。然后用户使用连续的发声（例如，“ahhhh”连续向左移动）来微调位置。

Harada等人提出了人声操纵杆，这是一种特别有前途的基于方向的解决方案，允许用户通过改变诸如元音质量，音高和响度等人声参数来连续移动光标[5]。在他们的系统中，元音会连续映射到二维光标空间，当用户停止发声时，光标会停止。理论上，人声操纵杆的最佳性能可能与手动操纵杆的性能相当。这种方法对于绘制应用程序非常有效，当流体光标移动被重视时，但在所有基于方向的系统中，目标选择任务的性能取决于光标的先前位置。换句话说，光标远离目标，选择变得更加困难和耗时[8]。

##1.2.2基于目标的解决方案
基于目标的系统会立即将光标移动到屏幕上的特定点，与基于方向的解决方案不同，它们的性能不依赖于光标的先前位置。例如，在文本文档中，用户可以说“选择星期五”，其将突出显示星期五。在使用Windows语音识别的另一种基于目标的方法中，用户可以说“开始”（它将打开开始菜单），然后用户可以通过在开始菜单上说出程序的名称来启动程序。

当存在与每个目标相关联的上下文信息时，基于目标的解决方案是有用的，特别是文字处理。但是，将光标移动到屏幕上的任意点可能会很困难，例如，当屏幕上的所有项目都不与标签相关联或多个目标名称相同（例如，网页搜索中的链接）时，这种方法会很困难。随着界面变得越来越复杂，将屏幕上的每个项目映射到上下文标签将是不切实际的。出于这些原因，我们将重点转移到允许用户将光标移动到屏幕上的特定点而没有任何上下文标签的解决方案上。

##参考文献
[1] Chin, C. A., Barreto, A., Cremades, J. G., and Adjouadi, M. 2008. Integrated electromyogram and eye-gaze tracking cursor control system for computer users with motor disabilities. Journal of Rehabilitation Research & Development, 45 (1), 161-174.

[2] Corno F., Farinetti, L., and Signorile, I. 2002. An eye-gaze input device for people with severe motor disabilities. Proceedings of SSGRR-2002 (L’Aquila, Italy).

[3] Dai, L., Goldman, R., Sears, A., and Lozier, J. 2005. Speech- based cursor control using grids: modelling performance and comparisons with other solutions. Behaviour and Information Technology, 24 (3), 219-230.

[4] Gilja, V., Nuyujukian, P., Chestek, C. A., Cunningham, J. P., Yu, B. M., Fan, J. M., Ryu, S. I., and Shenoy, K. V. 2012. A brain machine interface control algorithm designed from a feedback control perspective. Proceedings of the 34th Annual IEEE EMBS Conference, (San Diego, CA), 1318-1322.

[5] Harada, S., Landay, J. A., Malkin, J., Li, X., and Bilmes, J. A. 2006. The Vocal Joystick: Evaluation of Voice-based Cursor Control Techniques. Proceedings of the 8th International ACM SIGACCESS Conference on Computers and Accessibility, (Portland, OR), 197-204.

[6] Kamel, H. M. and Landay, J. A. 1999. The Integrated Communication 2 Draw (IC2D): A Drawing Program for the Visually Impaired, Proceedings of the ACM SIGCHI Conference on Human Factors in Computing Systems(Pittsburgh, PA), 222-223.

[7] Karimullah, A. S. and Sears, A. 2002. Speech-Based Cursor Control. Proceedings of the 5th International ACM Conference on Assistive Technologies, (Edinburgh, Scotland, UK), 178-185.

[8] Karimullah, A., Sears, A., Lin, M., and Goldman, R. 2003. Speech-based cursor control: Understanding the effects of variable cursor speed on target selection. Proceedings of the HCII, 681–685.

[9] Mihara, Y., Shibayama, E., and Takahashi, S. 2005. The migratory cursor: accurate speech-based cursor movement by moving multiple ghost cursors using non-verbal vocalizations. Proceedings of the 7th International ACM SIGACCESS Conference on Computers and Accessibility, (Baltimore, MD), 76-83.

[10] Oviatt, S. 1997. Multimodal interactive maps: designing for human performance. Human-Computer Interaction, 12 (1), 93-129.

[11] Sears, A., Feng, J., Oseitutu, K., and Karat, C. M. 2003. Hands-Free, Speech-Based Navigation During Dictation: Difficulties, Consequences, and Solutions. Human-Computer Interactions, 18 (3), 229-257.

[12] Sears, A., Karat, C. M., Oseitutu, K., Karimullah, A. S., and Feng, J. 2001. Productivity, satisfaction, and interaction strategies of individuals with spinal cord injuries and traditional users interacting with speech recognition software. Universal Access in the Information Society, 1 (1), 4-15.

[13] Sears, A., Lin, M., and Karimullah, A. S. 2003. Speech- based cursor control: understanding the effects of target size, cursor speed, and command selection. Human-Computer Interaction; Theory and Practice. Part II, Stephanidis, C. and Jacko, J. eds. L. Erlbaum Associates, Inc., Mahwah, NJ, 681-685.

[14] Sears, A., Young, M., and Feng, J. 2003. Physical Disabilities and Computing Technologies: An Analysis of Impairments. The Human-Computer Interaction Handbook, Jacko, J. and Sears, A. eds. L. Erlbaum Associates Inc., Hillsdale, NJ, 482-503.

[15] Zhu, S., Feng, J., and Sears, A. 2010. Investigating Grid- Based Navigation: The Impact of Physical Disability. ACM Transactions on Accessible Computing, 3 (1), 1-30.