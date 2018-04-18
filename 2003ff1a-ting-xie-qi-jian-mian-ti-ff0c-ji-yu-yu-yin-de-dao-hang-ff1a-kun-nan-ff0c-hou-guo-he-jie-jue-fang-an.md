#听写期间免提，基于语音的导航：困难，后果和解决方案
**摘要     **语音识别技术不断改进，但用户仍然在使用该软件创建和编辑文档时遇到很大困难。事实上，最近的一项研究证实，用户在纠正活动中花费了66％的时间，而在听写时只花了33％。特别有趣的是，三分之一的用户时间只是从一个地方导航到另一个地方。在这篇文章中，我们调查了在面向听写的活动环境中免提语音导航的效果。我们提供有关故障率，故障原因以及这些故障后果的详细数据。我们的结果证实，面向方向的导航（例如，向上移动两行）不如面向目标的导航（例如选择目标）有效。我们确定了基于语音的导航命令失败背后的三个最常见的原因：识别错误，发布无效命令以及在发布命令的过程中暂停。我们还记录了基于语音导航命令失败的后果。作为这一分析的结果，我们确定了可以减少故障率并减少一些剩余故障后果的变化。我们还提出了一套更为实质性的改变，以简化基于方向的导航并增强基于目标的导航。必须通过未来的实证研究来评估这套最终建议的有效性。

##1.引言
语音识别技术已经大大改善（Karat，Vergo，＆Nahamoo，2003）。因此，语音识别与用于非听写任务的多模式界面中的性能改进相关联。例如，最近的一项研究证实，笔式和语音界面允许参与者比传统的键盘和鼠标界面更快地完成规划模拟任务（Cohen，McGee，＆Clow，2000）。尽管多模式解决方案可以提供许多明显的优势，但本文的重点是使用语音识别来支持标准的听写任务，因为这些问题对于用户不可用的环境尤为重要身体残疾阻碍他们使用传统输入设备的个人。在这种情况下，重要的是要注意最近对语音识别技术的改进包括提高识别准确性，更有效地整合命令和听写，并改进错误校正对话框。然而，即使有了这些改进，与传统的键盘和鼠标相比，使用语音识别时标准听写任务的速度要慢得多（Karat，Halverson，Karat，＆Horn，1999）。更重要的是，最近的研究证实，识别和纠正识别错误继续占用户大部分时间通过使用语音识别的口述创建文档（Halverson，Horn，Karat，＆Karat，1999; Karat等， 1999; Sears，Karat，Oseitutu，Karimullah，＆Feng，2001）。

例如，在前面的文章中，我们讨论了用户使用的策略以及他们的生产力和所创建文档的质量（Sears等，2001）。我们还报告说，用户花费了三分之一的时间来指定，三分之一的用户发布导航命令，另外三分之一的用户发布其他命令来纠正错误。这些结果引发了关于一般语音相互作用的错误识别和纠正过程以及关于用户用来完成空间导航任务的命令的具体问题的严重问题。有趣的是，多模态界面通常支持空间任务，如在文档中选择一个词，使用手语模式（例如手写笔）而不是语音，因为这通常导致更好的性能（例如Oviatt，1997; Oviatt等2000）。因为当用户的手不可用时，我们的重点是基于语音的交互，本文更详细地介绍了基于语音的导航。与我们之前提供用户交互高级概述的文章不同，本文提供了有关导航策略，失败率，失败命令的后果以及改进建议的详细数据。

错误纠正涉及多个步骤：用户必须确定发生了识别错误，导航至错误，然后纠正错误。基于语音的导航可以通过几种方式完成，其中一些将导航和校正活动相结合（例如，“校正星期五”选择星期五，并启动校正过程）。基于语音的导航命令的一种分类侧重于结果的连续或离散的运动类型。例如，“向左移动”可能导致鼠标光标向左移动，一次一个像素，直到用户发出“停止”命令。这种方法模拟传统的指点设备，允许用户将光标定位在屏幕上的任何位置。虽然强大的连续运动不利用命令发布的上下文。相反，离散运动通常利用上下文信息。例如，在编辑文本时，可以根据需要通过字符，单词或行来移动光标。我们的重点是基于语音导航的两种常见方法，这些方法会导致离散运动：基于目标的导航和基于方向的导航。

对于基于目标的导航，用户使用文档中存在的单词指定目的地。基于目标的导航采用Command目标的形式。例如，“选择星期五”将突出显示星期五。对于当前基于方向的导航，用户发出一个命令，然后发出一个方向，距离和运动单位。例如，用户可以说“移动左五个单词”。基于目标的导航可以允许用户快速移动到期望的位置，通常只用一个命令。如果目标多次出现在屏幕上，可能需要额外的命令。相反，基于方向的导航则强制用户将当前和期望光标位置之间的差异转换为一系列命令（例如，一个垂直移动而另一个垂直移动）。鉴于基于方向的导航命令的复杂性增加，我们预计用户将难以构建有效的基于方向的命令，基于方向的导航将失败得更频繁，基于目标的导航将需要更少的命令来完成成功的导航序列，并且当基于方向和目标的命令失败时，结果将会有所不同。

在下面的章节中，我们提供了关于基于语音的导航效率的全面数据，用户遇到困难背后的原因以及导航命令失败的后果。基于这些数据，我们提出了三条改进基于语音导航的建议。重点修改路径命令的重点在第三处理，其中涉及对可用命令的根本性更改。

##2.相关研究
语音识别已成功整合到各种应用中。一些应用程序采用多模式解决方案，允许在最有效的情况下使用语音，而另一些应用程序专注于用户的手或眼睛不可用的情况，或者传统键盘输入不可用时。例子包括基于语音的应用程序，旨在允许放射科医师决定他们的报告（Lai＆Vergo，1997），为身体障碍患者设计的应用程序（Thomas，Basson和Gardner-Bonneau，1999），环境控制系统（Burmeister，Machate ，＆Klein，1997）以及各种电话应用（例如Wolf＆Zadrozny，1998）。

研究人员已经探索了嘈杂环境中发生的说话模式的变化以及这些变化如何影响语音识别（Rollins，1985），用户在遇到识别错误时如何修改他们的语音（Oviatt，MacEachern，＆Levow，1998），以及为儿童设计语音识别系统（Nix，Fairweather，＆Adams，1998）;但是涉及语音识别的界面导向研究最活跃的领域是多模式界面（参见Oviatt，2003）。两个特别感兴趣的领域包括任务类型和用户喜欢的模式之间的关系（例如，Hauptmann，1989; Cohen＆Oviatt，1995; Oviatt，1997）以及如何使用多模态相互作用来减少错误（例如，Oviatt，2000; Oviatt等，2000）。 Oviatt讨论了在纯语音接口上的多模式界面中基于用户和基于架构的错误处理方面的改进，以及各种潜在好处，包括改进了带有口音和移动应用的扬声器的性能。她的研究表明，对于视觉空间任务而言，与纯语音交互相比，笔语交互可显着减少任务完成时间，任务关键内容错误和自发不良行为（Oviatt，1997; Oviatt＆Kuhn，1998）。这一点以及其他近期的努力表明，通过仔细组合多种输入模式，可以使出错易发的技术更加强大。这些努力中的许多都突出了基于言语的互动的潜力，当它们与其他互动形式有效地结合时（例如Oviatt，2000,2003; Oviatt等人，2000; Suhm，Myers和Waibel，2001）。虽然基于语音的交互在用户活动受到限制时（例如，电话，特定于语言的听写，环境控制）或当语音是多模式解决方案的一部分时最为有效，但我们的重点是基于语音的导航。因此，本节的其余部分将回顾三个领域的研究：基于语音的数据录入任务应用，纠正识别错误和基于语音的导航。

研究人员已经研究了将语音识别用于各种数据录入任务。 Ainsworth（1988）研究了数字输入的最佳字符串长度，而Ainsworth和Pratt（1992）研究了用于电话拨号场景的纠错策略。这两项研究都使用孤立词SR系统，短输入字符串（例如1-14位数字）和小词汇表（例如11或14个字），这使得难以将其结果推广到用于规定的大型词汇系统显着更大的文件。同样，Noyes和Frankish（1994）在每个单词或六个单词序列之后探讨了听觉或视觉反馈的效果; Baber和Hone（1993）致力于提供反馈意见，并要求在处理之前确认每个单词的正确性。这些方法都不可行，因为这些方法是非常重要的。更重要的是，单独的语音导航并没有被这些研究人员所探索。

许多研究人员已经探索了包含一些基于语音的交互的多模式界面。如前所述，这些努力表明，多模式解决方案在空间导航任务方面优于纯语音​​解决方案（例如，Oviatt，1997; Oviatt等人，2000）。 Suhm等人（2001）提供了多模态界面研究和纠错对话框的重要研究之间的桥梁。 Suhm等人（2001）调查了几种纠正识别错误的多模式方法，包括使用键盘，鼠标，手写笔和语音。他们发现与单独使用语音相比，多模式技术导致更快的纠错时间。然而，所有探索的技术都使用基于触摸屏的导航，用户只需触摸他们想修改的单词即可。同样，Danis等人（1994）开发了一个面向言语的编辑器，允许用户使用“指向和说话”方法在口述时改变插入点，但光标移动是使用鼠标完成的。

相反，McNair和Waibel（1994）探讨了错误纠正活动，并明确重点讨论了基于言语的错误词汇选择。他们描述了一个早期版本的基于目标的导航，在确定用户想要选择哪个单词时，使用识别的单词以及每个单词的可能替代方案列表。他们通过确定它能够成功识别用户想要选择的单词的频率来评估这种技术。他们报告了85％的成功率，但没有其他命令是活跃的，用户也不能口述。因此，这种技术在实际应用环境中使用时可能会更经常失败。最后，他们没有探究用户因失败的命令的15％而经历的后果。

Manaris和Harkreader（1998）并没有把重点放在纠正错误上，而是研究了使用SR作为产生击键和鼠标事件的替代机制，目的是为上肢运动控制的个体开发替代数据输入技术，控制障碍。使用基于方向的导航命令完成导航，导航命令生成连续的光标移动（例如“向左移动”，然后是“停止”）以及基于目标的命令，将光标移动到屏幕的五个预定义区域之一（例如，离散运动）。使用Wizard-of-Oz模拟他们的解决方案进行了一项试点研究，但没有关于其语音导航机制的有效性的结果。作者的确表明，对于不能使用键盘和鼠标的个人而言，语音对于键盘和鼠标来说可能是一种有希望的替代方案。

同样，de Mauro，Gori，Maggini和Martinelli（2001）讨论了语音控制鼠标的设计。他们的系统根据简单的话语产生连续的运动。与用户说完整命令的大多数实现（即“向左移动”）不同，个别元音被映射到命令。结果，用户必须学习从命令（例如，“向左移动”）到导致该命令被执行的话语（例如“A”）的适当映射。他们的系统还支持窗口区域内的基于目标的导航。因此，一旦光标位于窗口的标题栏上，就可以使用适用于该特定上下文的几个命令，例如最小化，关闭和移动。目前，文本文档中的导航仅支持使用连续的鼠标移动，并且没有提供关于导航机制功效的数据。

Christian，Kules，Shneiderman和Youssef（2000）在网络环境下探讨了基于语音的导航。导航是通过说出充当链接的字词或由浏览器自动与链接相关联的数字来完成的。与基于鼠标的导航相比，这种基于目标的导航导致的错误极少，但任务完成时间明显更长。更重要的是，考虑到用户执行的任务，其他命令不活跃，用户无法指定文本。因此，错误率（以及错误的后果）可能并不能代表在面向听写的应用环境中预期的结果。

这些努力提供了有关使用基于语音的交互的见解。显然，演讲比其他演讲更适合某些活动。多模式解决方案提供了有希望的结果，特别是在纠正识别错误和空间导航活动的情况下。虽然一些研究已经探索了纠正识别错误的过程，但是通常使用多模式解决方案来完成导航。例如，Suhm et al。 （2001）让用户使用触摸屏指出错误，而Danis等人（1994）使用鼠标。一些研究人员已经探索了基于语音的导航，但是必须全面研究在基于听写的活动中如何使用基于语音的导航命令。目前的研究在完成标准听写任务的同时探索导航策略，失败率和失败后果。我们还确定了三个具体的增强功能，以解决用户在使用基于语音的导航时遇到的一些问题。

以下部分报告的结果代表作为更大型研究的一部分而收集的数据的一个子集，旨在提供对面向听写任务的语音识别功效的深入了解。这项较大型研究的目标之一是了解与身体残疾者使用语音识别相关的问题，与传统计算机用户相比，如果这种方式更方便，他们可以选择使用键盘和鼠标。结果，这项研究包括两组参与者，如下所述。早期的一篇文章讨论了生产力，满意度以及这两个用户群所采用的策略（Sears et al。，2001），而本文仅关注基于语音的导航。由于本文的主要焦点是基于语音的导航命令的失败以及如何重新设计这些命令以获得成功，我们的分析证实两组参与者的失败率没有差异，两组的结果进行所有后续分析。

##参考文献
Ainsworth, W. A. (1988). Optimization of string length for spoken digit input with er- ror correction. International Journal of Man-Machine Studies, 28, 573–581.

Ainsworth, W. A., & Pratt, S. R. (1992). Feedback strategies for error correction in speech recognition systems. International Journal of Man-Machine Studies, 36, 833–842.

Baber, C., & Hone, K. (1993). Modeling error recovery and repair in automatic speech recognition. International Journal of Man-Machine Studies, 39, 495–515.

Bazzi I., & Glass, J. (2001). Learning units for domain-independent out-of-vocabulary word modelling. Proceedings of Eurospeech 2001, 61–64.

Burmeister, M., Machate, J., & Klein, J. (1997). Access for all: HEPHAISTOS—a per- sonal home assistant. Extended Abstracts of the ACM SIGCHI Conference on Human Factors in Computing Systems (CHI 97; pp. 36–37). New York: ACM.

Christian, K., Kules, B., Shneiderman, B., & Youssef, A. (2000). A comparison of voice controlled and mouse controlled web browsing. Proceedings of the ACM SIGCAPH Conference on Assistive Technologies (Assets 2000), 72–79.

Cohen, P. R., McGee, D. R., & Clow, J. (2000). The efficiency of multimodal interac- tion for a map-based task. Proceedings of the Applied Natural Language Processing Con- ference (ANLP’00), 331–338.

Cohen, P. R., & Oviatt, S. L. (1995). The role of voice input for human-machine com- munication. Proceedings of the National Academy of Sciences, 92, 9921–9927.

Danis, C., Comerford, L., Janke, E., Davies, K., Devries, J., & Bertrand, A. (1994). Storywriter: A speech oriented editor. Conference Companion for the ACM SIGCHI Conference on Human Factors in Computing Systems (CHI 94), 277–278.

de Mauro, C., Gori, M., Maggini, M., & Martinelli E. (2001). Easy access to graphical in- terfaces by voice mouse. Available from the author at demauro@dii.unisi.it

Feng, J., Sears, A., & Forgionne, G. (in press). Command selection in speech recogni- tion software: A decision-making approach. Proceedings of the 12th International WOSC Congress.

Halverson, C., Horn, D., Karat, C-M., & Karat, J. (1999). The beauty of errors: Pat- terns of error correction in desktop speech systems. Proceedings of the ACM SIGCHI Conference on Human Factors in Computing Systems (INTERACT 99), 133–140.

Hauptmann, A. G. (1989). Speech and gestures for graphic image manipulation. Pro- ceedings of the ACM SIGCHI Conference on Human Factors in Computing Systems (CHI 89), 241–245.

Karat, C-M., Halverson, C., Karat, J., & Horn, D. (1999). Patterns of Entry and Correc- tion in Large Vocabulary Continuous Speech Recognition Systems. Proceedings of the ACM SIGCHI Conference on Human Factors in Computing Systems (CHI 99), 568–575.

Karat, C., Vergo, J., & Nahamoo, D. (2003). Conversational interface technologies. In J. Jacko & A. Sears (Eds.), The human-computer interaction handbook (pp. 169–186). 

Mahwah, NJ: Lawrence Erlbaum Associates, Inc.Lai, J., & Vergo, J. (1997). MedSpeak: Report creation with continuous speech recogni- tion. Proceedings of the ACM SIGCHI Conference on Human Factors in Computing Systems (CHI 99; pp. 431–438). New York: ACM.

Manaris, B., & Harkreader, A. (1998). SUITEKeys: A speech understanding interface for the motor-control challenged. Proceedings of the ACM SIGCAPH Conference on Assistive Technologies (ASSETS’98), 108–115.

McNair, A., & Waibel, A. (1994). Improving recognizer acceptance through robust, natural speech repair. Proceedings of the International Conference on Spoken Language Processing, 1299–1302.

Nix, D., Fairweather, P., & Adams B. (1998). Speech recognition, children, and read- ing. Late-Breaking Results for the ACM SIGCHI Conference on Human Factors in Com- puting Systems (CHI 98), 245–246.

Noyes, J. M., & Frankish, C.R. (1994). Errors and error correction in automatic speechrecognition systems. Ergonomics, 37, 1943–1957.

Oviatt, S. (1994). Interface techniques for minimizing disfluent input to spoke lan- guage systems. Proceedings of the ACM SIGCHI Conference on Human Factors in Com- puting Systems (CHI 94), 205–210.

Oviatt, S. L. (1997). Multimodal interactive maps: Designing for human performance. Human–Computer Interaction, 12, 93–129.

Oviatt, S. L. (2000). Taming speech recognition errors within a multimodal interface. Communications of the ACM, 43(9), 45–51.

Oviatt, S. L. (2003). Multimodal interfaces, In J. A. Jacko & A. Sears (Eds.), The hu- man–computer interaction handbook (pp. 286–304). Mahwah, NJ: Lawrence Erlbaum Associates, Inc.

Oviatt, S. L., Cohen, P. R., Wu, L., Vergo, J., Duncan, L., Suhm, B., et al. (2000). Designing the user interface for multimodal speech and gesture applications: State-of-the-art sys- tems and research directions. Human–Computer Interaction, 15, 263–322.

Oviatt, S. L., & Kuhn, K. (1998). Referential features and linguistic indirection in multimodal language. Proceedings of the International Conference on Spoken Language Processing, 6 (pp. 2339–2342). Syndey, Australia: ASSTA.

Oviatt, S., MacEachern, M., & Levow, G-A. (1998). Predicting hyperarticulate speech during human-computer error resolution. Speech Communication, 24(2), 87–110.

Rollins, A. (1985). Speech recognition and manner of speaking in noise and in quiet.Proceedings of the ACM SIGCHI Conference on Human Factors in Computing Systems (CHI 85), 197–199.

Sears, A., Karat, C-M., Oseitutu, K., Karimullah, A., & Feng, J. (2001). Productivity, satisfaction, and interaction strategies of individual with spinal cord injuries and traditional users interacting with speech recognition software. Universal Access in the Information Society, 1, 4–15.

Suhm, B., Myers, B., & Wailbel, A. (2001). Multimodal error correction for speech user interfaces. ACM Transactions on Computer–Human Interaction, 8(1), 60–98.

Thomas, J. C., Basson, S., & Gardner-Bonneau, D. (1999). Universal access and assistive technology. In D. Gardner-Bonneau (Ed.), Human factors and voice interac- tive systems (pp. 135–146). 

Boston: Kluwer.Wolf, C., & Zadrozny, W. (1998). Evolution of the conversation machine: A case study of bringing advanced technology to the marketplace. Proceedings of the ACM SIGCHI Con- ference on Human Factors in Computing Systems (CHI 98; pp. 488–495). New York: ACM.



