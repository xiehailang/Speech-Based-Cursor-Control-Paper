# 移动设备的语音识别

**摘要    **简要介绍会议讨论的内容。

## 1.简介

谷歌专注于利用多通道技术使信息普及，包括语音输入。谷歌语音小组自2005年成立以来，为美国等国家开发了几种成功的语音识别服务。 2006年，在美国推出了GOOG-411，这是一种可以通过任意手机使用语音识别驱动的目录辅助服务。随着智能手机如iPhone，黑莓，诺基亚S60平台和运行Android操作系统的手机（如Nexus One等）越来越广泛地使用，我们转而努力为搜索引擎（搜索语音）和其他应用程序提供语音输入手机。许多最近的智能手机只有软键盘，难以打字，尤其是对于较长的输入词和句子。与拉丁字母语言相比，一些亚洲语言（例如日语和中文）更难打字，因为基本字符数量非常高。口语输入是改善这些问题的自然选择，更多细节将在下面讨论。

我们还一直致力于美国英语的语音邮件转录和YouTube转录，这些语言也是美国公开发布的产品，但此处重点将放在移动设备环境中的语音识别。

## 2 GOOG-411

GOOG-411是Google在美国和加拿大运行的基于语音识别的目录辅助服务[^1,2]。 此应用程序使用免费号码1-800-GOOG-411（1-800-4664-411）。 系统会提示用户说明城市，州和企业名称（他）正在查找。 使用文本到语音的服务可以提供地址和电话号码，或者可以将用户直接连接到企业。 使用Google Maps Local的后端信息。

虽然这是一个有用的应用程序来搜索餐厅，商店等，它仅限于企业。 这种服务的其他困难包括对话的必要性，相对昂贵的运营成本，在后端数据库中列出错误，并且最重要的是不能够给用户提供更丰富的信息（如在智能手机屏幕上）。

## 3语音搜索

2008年，Google在美国推出了多种智能手机的语音搜索功能[^3]。语音搜索仅增加了向电话发送搜索查询的功能，而不必将其键入浏览器。音频被发送到Google服务器，在那里被识别，并将识别结果和搜索结果一起发送回手机。数据通过数据信道而不是语音信道，从而实现更高质量的音频传输，因此识别率更高。我们的语音识别技术比较标准，在一些细节之下。

**前端和声学模型。**对于前端，我们使用LDA的39维PLP特征。声学模型是ML和MMI训练的，triphone决策树绑定3态HMMs，总数达到10k个州。状态分布由具有STC的50-300k对角线协方差高斯模型来建模。我们使用高斯选择的时间同步有限状态转换器（FST）解码器用于快速可能性计算。

**字典。**根据不同的语言，我们的手机包含30到100部手机。我们在字典中使用200k到1.5M之间的单词，这些单词是从基于Web的查询流中自动提取的。这些单词的发音大多由一个自动系统生成，对数字，缩写和其他例外进行特殊处理。

**语言模型。**由于我们的目标是识别搜索查询，因此我们可以从基于Web的匿名搜索查询中挖掘我们的语言模型数据。我们大多使用3克或5克与Katz退避训练数月或数年的查询数据。语言模型必须适当修剪，以便最终的解码器图形适合服务器的内存。

**声学数据。**为了训练初始系统，我们使用专门为此设计的Android应用程序收集了大约250k的口头查询[^4]。数百个扬声器从屏幕读取查询并记录相应的语音样本。由于大多数查询没有错误，所以我们不必手动转录这些查询。

**指标。**我们希望优化用户体验。传统上，语音识别系统专注于最小化字错误率。这对我们来说也是一种有用的措施，但更好的是规范化的句子错误率，因为它不取决于单词的定义。作为最接近用户体验的指标，我们使用WebScore：我们将假设和参考发送到搜索后端，并比较我们获得的链接。假设参考以这种方式生成正确的搜索结果，我们知道该假设的搜索结果是否在前三个结果之内 - 这样用户就可以在他的智能手机屏幕上看到正确的结果。

**语言。**在美国英语之后，我们为英国，澳大利亚和印度推出了语音搜索。 2009年末增加了普通话[^5]和日语。外语带来许多额外的挑战。例如，日语和中文等一些亚洲语言在单词之间没有空格。对于这些我们写了一个分词器，它优化了最大化句子可能性的单词定义。大多数语言的字符超出正常的ASCII字符集，有些情况下会有数千字符，这会使自动发音规则复杂化。

**额外的挑战。**有许多细节对于获得良好的用户体验至关重要，但由于空间限制，我们无法在此讨论。这些包括正确地获取用户界面，优化协议以实现最小延迟，正确处理数字，日期和缩略词等特殊情况，避免显示令人讨厌的查询，并在使用数据进入后有效地改进系统。

## 4展望

对于移动设备来说，语音是一种有吸引力的输入方式，除了语音搜索之外，我们一直在研究其他功能，包括更多通用的语音输入[^6]，联系人拼写（在美国推出）和识别特殊短语以触发手机上的某些应用程序。我们相信，未来几年，语音输入将变得更加准确，更加被接受和有用，足以帮助用户高效地访问和浏览通过移动设备提供的信息。

## 参考文献

1. Bacchiani, M., Beaufays, F., Schalkwyk, J., Schuster, M., Strope, B.: Deploying GOOG-411: Early lessons in data, measurement, and testing. In: Proceedings of ICASSP, pp. 5260–5263 \(2008\)

2. van Heerden, C., Schalkwyk, J., Strope, B.: Language Modeling for What-with- Where on GOOG-411. In: Proceedings of Interspeech, pp. 991–994 \(2009\)

3. Schalkwyk, J., Beeferman, D., Beaufays, F., Byrne, B., Chelba, C., Cohen, M., Kamvar, M., Strope, B.: Google Search by Voice: A case study. In: Weinstein, A. \(ed.\) Visions of Speech: Exploring New Voice Apps in Mobile Environments, Call Centers and Clinics. Springer, Heidelberg \(2010\) \(in Press\)

4. Hughes, T., Nakajima, K., Ha, L., Vasu, A., Moreno, P., LeBeau, M.: Building transcribed speech corpora quickly and cheaply for many languages. In: Interspeech \(submitted 2010\)

5. Shan, J., Wu, G., Hu, Z., Tang, X., Jansche, M., Moreno, P.: Search by Voice in Mandarin Chinese. In: Interspeech \(submitted 2010\)

6. Ballinger, B., Allauzen, C., Gruenstein, A., Schalkwyk, J.: On-Demand Language Model Interpolation for Mobile Speech Input. In: Interspeech \(submitted 2010\)


