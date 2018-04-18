# 人机交互论文集

本人只是**翻译**英文论文以做**备忘**

如有引用请注明原有出处

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

## 2002:基于语音的光标控制 [点击这里跳转](/2002ji-yu-yu-yin-de-guang-biao-kong-zhi.md)

### 论文简述：

文章作者发现，当我们使用语音命令控制光标移动，与此同时会产生_**三种延时**_：

* 用户察觉到光标已到达期望位置的延迟
* 用户说出所需命令的延迟
* 系统识别用户发出的命令时的延迟

由于有这三种延时的影响，当用户发出“停止”命令时，移动中的光标不会立即停止。

为了解决光标无法在目标位置停止的问题，作者提出一种_**预测光标**_位置的方法：

* 当用户发出任何移动命令时，预测光标就会出现在实际光标的旁边，并沿移动方向偏移适当距离。
* 用户在预测光标移动到期望位置时发出停止命令，此时预测光标隐藏。（实际光标由于延时的影响，会产生偏移，即偏移到预测光标附近位置）

![](/assets/3pic1.png)

### 值得借鉴的地方：

1. 本文将基于语音识别的光标控制分为基于目标或方向两种。
2. 基于目标的光标导航，用户只须确定所需的目标并发出适当的指令。该方法会由于目标的数量增加，导致用户难以记住所有目标名称或更容易出错，又或者多个目标可能拥有同一个名称，并且词汇增加使识别错误率也增加。
3. 基于方向的光标导航，会导致光标离散或连续的移动。对于离散的基于方向的导航，用户指定方向和距离（例如，英寸，厘米，字母，单词）：“左移三个单词”将导致光标向左跳三个单词。对于连续的基于方向的导航，用户指定方向：“向左移动”使光标开始向左缓慢移动，直到发出“停止”命令。
4. 本文是连续的基于方向的光标导航。

## 2003：听写期间免提，基于语音的导航：困难，后果和解决方案 [点击这里跳转](/2003ff1a-ting-xie-qi-jian-mian-ti-ff0c-ji-yu-yu-yin-de-dao-hang-ff1a-kun-nan-ff0c-hou-guo-he-jie-jue-fang-an.md)

### 论文简述：

## 2004：基于语音的光标控制：基于网格的解决方案的研究 [点击这里跳转](/2004ff1a-ji-yu-yu-yin-de-guang-biao-kong-zhi-ff1a-ji-yu-wang-ge-de-jie-jue-fang-an-de-yan-jiu.md)

### 论文简述：

本文作者提出：连续的基于方向的光标导航只有当他们接近大型目标时才能快速有效的选中目标，不然随着距离的增加，所需时间也会增加，虽然变速光标会减少距离所产生的时间，但会让准确选中目标变得更困难。

为了解决距离与目标大小的影响，作者提出九光标3\*3网格与单光标3\*3网格，允许用户多级递归深入每一个网格，直至可以准确选中目标，并加入“后退”命令允许用户恢复之前的网格界面。  
![](/assets/2004pic1.png)  
![](/assets/2004pic1a.png)

与之前的光标控制方案相比，客服了大屏幕的选择问题，大型目标选择时间减少33%，小型目标选择时间节省55%，可以消除距离的影响。但是任然收到目标规模的限制。

## 2005：可迁移光标：通过使用非语言声音移动多个幻影游标来实现准确的基于语音的光标移动  [点击这里跳转](/2005ff1a-qian-yi-guang-biao-ff1a-tong-guo-shi-yong-fei-yu-yan-sheng-yin-yi-dong-duo-ge-huan-ying-you-biao-lai-shi-xian-zhun-que-de-ji-yu-yu-yin-de-guang-biao-yi-dong.md)

### 论文简述：

本文作者提出了一种“迁徙游标”，允许用户快速指定位置，在接近目标时使用音调来控制光标上升。  
![](/assets/2005pic1.png)

## 2006：声乐游戏杆：基于语音的光标控制技术的评估  [\[点击这里跳转\]](/2006ff1a-sheng-le-you-xi-gan-ff1a-ji-yu-yu-yin-de-guang-biao-kong-zhi-ji-zhu-de-ping-gu.md)

### 论文简述：

本文作者提出一种“声音操纵杆”，以元音声音特征为控制量，允许用户使用4路或8路两种控制模式，4路只有垂直轴和水平轴，并且能够识别离散声音（辅音k）用以执行用户操作（点击）。光标的速度可以通过改变元音响度来控制;声音越软，光标移动越慢，反之亦然。并验证了此模式符合Fitt's law 法则。  
![](/assets/2006pic1.png)

## 2008：会话游戏：基于语音的游标控制机制的实证研究  [\[点击这里跳转\]](/2008ff1a-hui-hua-you-xi-ff1a-ji-yu-yu-yin-de-you-biao-kong-zhi-ji-zhi-de-shi-zheng-yan-jiu.md)

### 论文简述：

本文档描述了基于语音的光标控制机制以及称为NameTags的新方法的研究。本研究旨全面分析现有的光标控制机制，并统计用户经验数据，以指引未来系统的设计，其中存在以下一个或多个条件：**实时需求，非常小的目标和移动目标。这项研究的一个这样的应用是在视频游戏领域**，在这些领域中，被摄体通常需要快速选择许多小的移动物体。这些发现也对身体受损的受试者有影响，他们的主要或唯一控制形式是言语。

### 值得借鉴的地方：

1. Oviatt在“Multimodal Interactive Maps: Designing for Human Performance.（1997）”中研究发现文本输入与光标控制是语音系统必须支持的两个要素。
2. Halverson等人在“The Beauty of Errors: Patterns of Error Correction in Desktop Speech systems.（1999）”中指出语音识别准确率在受控环境下已经提高到98%。
3. 基于目标的光标导航的研究有：
   * The Integrated Communication 2 Draw \(IC2D\): A Drawing Program for the Visually Impaired. （1999）
   * A Study of Blind Drawing Practice: Creating Graphical Information without the Visual Channel.（2000）
   * Sketching Images Eyes-free: A Grid-based Dynamic Drawing Tool for the Blind. （2002）
   * Speech-based Cursor Control: A Study of Grid-based Solutions. （2004）
4. 基于方向的光标导航的研究有：
   * SUITEKeys: A Speech Understanding Interface for the Motor-control Challenged.（1998）
   * An Intelligent Interface for Keyboard and Mouse Control - Providing Full Access to PC Functionality via Speech.（2001）
   * Speech-based Cursor Control.（2002）
   * 使用“非语音”来控制移动：
     * Voice as Sound: Using Non-verbal Voice Input for Inter- active Control.（2001）
     * The Vocal Joystick: Evaluation of Voice-based Cursor Control Techniques. （2006）
     * Non-speech Input and Speech Recognition for Real-time Control of Computer Games.（2006）
5. 使用非语音以及基于方向和基于目标的光标控制的混合控制：
   * The Migratory Cursor: Accurate Speech-based Cursor Movement by Moving Multiple Ghost Cursors using Non-Verbal Vocalizations.（2005）
6. Hauptmann在“Speech and Gestures for Graphic Image Manipulation. （1989）”中指出人们喜欢使用手势和语音进行图形操作。用户更喜欢多模式交互系统。多模式指将新的控制机制与标准操纵杆或鼠标键盘控制相结合。

## 2009：基于语音的导航 - 改进基于网格的解决方案  [\[点击这里跳转\]](/2009ji-yu-yu-yin-de-dao-hang-gai-jin-ji-yu-wang-ge-de-jie-jue-fang-an.md)

### 论文简述：

本文作者为了解决现有的基于网格的导航的局限性，增加了放大和微调功能，一旦网格变得足够小，放大功能向用户显示网格的放大版本，使得更容易看到小目标。微调功能允许用户使用四个简单的命令来微调光标位置：“向上，向下，向右和向左”。每个命令都可以通过特定数量的预定义单位将光标移动到特定方向，这使得在选择目标所需的全部内容时可以轻松地将光标移动很小的距离。  
![](/assets/2009pic1.png)  
（a）放大前（b）放大后（c）在微调之前（d）微调后（e）在放大和微调之前（f）放大和微调后。

## 2010:针对点击式任务的非语言语音控制光标的设计和评估  [\[点击这里跳转\]](/2010zhen-dui-dian-ji-shi-ren-wu-de-fei-yu-yan-yu-yin-kong-zhi-guang-biao-de-she-ji-he-ping-gu.md)

### 论文简述：

本文作者以“嗡嗡声”为语音特征进行语音命令，使用基于网格的导航，但是只有4格。  
![](/assets/2010pic1.png)

## 2010：调查基于网格的导航：身体残疾的影响 [\[点击这里跳转\]](/2010ff1a-diao-cha-ji-yu-wang-ge-de-dao-hang-ff1a-shen-ti-can-ji-de-ying-xiang-3002.md)

### 论文简述：

## 2013：可调节网格 - 使用语音识别的基于网格的光标控制解决方案[\[点击这里跳转\]](/2013ff1a-ke-diao-jie-wang-ge-shi-yong-yu-yin-shi-bie-de-ji-yu-wang-ge-de-guang-biao-kong-zhi-jie-jue-fang-an.md)

### 论文简述：

## 2017：通过语音识别API实现与Android系统和应用程序的高度交互[\[点击这里跳转\]](/2017tong-guo-yu-yinshi-bie-api-shi-xian-yu-android-xi-tong-he-app-de-wan-quan-hu-dong.md)

### 论文简述：

本文作者提出一种有效地从语音的角度与移动设备进行交互的方法。是使用有行、列和空间标识符的网格来分割屏幕。用户可以在视觉上识别他们想要触摸的点，发出某个位置指令，并由应用程序在所选位置模拟点击操作。为了满足用户设备型号和屏幕尺寸不同的需求，增加了配置模式，其中可以修改网格布局。  
![](/assets/pic1.png)  
![](/assets/pic2.png)  
本文作者提出一种有效地从语音的角度与移动设备进行交互的方法。是使用有行、列和空间标识符的网格来分割屏幕。用户可以在视觉上识别他们想要触摸的点，发出某个位置指令，并由应用程序在所选位置模拟点击操作。为了满足用户设备型号和屏幕尺寸不同的需求，增加了配置模式，其中可以修改网格布局。

## 总结：

David Thornton在2008年通过“Talking Games: An Empirical Study of Speech-based Cursor Control Mechanisms”这篇论文，对以往的语音识别中基于目标或方向的光标控制的研究做出了总结，并提出人们喜欢使用手势和语音进行图形操作，更喜欢带有语音识别的多模式交互系统。多模式指将新的控制机制与标准操纵杆或鼠标键盘控制相结合。

