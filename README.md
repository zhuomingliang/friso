Friso完整版本(词库, 词库管理工具, winNT下的dll文件, 开发帮助文档)下载: https://code.google.com/p/friso/ <br />

<h3>一. 关于Friso: </h3>
Friso是使用c语言开发的一款开源的高性能中文分词器，使用流行的mmseg算法实现。完全基于模块化设计和实现，可以很方便的植入其他程序中，例如：MySQL，PHP，源码无需修改就能在各种平台下编译使用，加载完20万的词条，内存占用稳定为14.5M.


1。目前最高版本：friso 1.6.1，同时支持对UTF-8/GBK编码的切分，绑定了php扩展和sphinx token插件

2。三种切分模式：

	(1). 简易模式：FMM算法，适合速度要求场合。
	(2). 复杂模式- MMSEG四种过滤算法，具有较高的岐义去除，分词准确率达到了98.41%。
	(3). (!New)检测模式：只返回词库中已有的词条，很适合某些应用场合。(1.6.1版本开始)

请参考本算法的原作：http://technology.chtsai.org/mmseg/。

3。支持自定义词库。在dict文件夹下，可以随便添加/删除/更改词库和词库词条，并且对词库进行了分类。

4。简体/繁体/简体混合支持, 可以方便的针对简体，繁体或者简繁体切分。同时还可以以此实现简繁体的相互检索。

5。支持中英/英中混合词的识别(维护词库可以识别任何一种组合)。例如：卡拉ok, 漂亮mm, c语言，IC卡，哆啦a梦。

7。很好的英文支持，英文标点组合词识别, 例如c++, c#, 电子邮件，网址，小数，百分数。

8。(!New)自定义保留标点：你可以自定义保留在切分结果中的标点，这样可以识别出一些复杂的组合，例如：c++, k&r，code.google.com。

9。(!New)复杂英文切分的二次切分：默认Friso会保留数字和字母的原组合，开启此功能，可以进行二次切分提高检索的命中率。例如：qq2013会被切分成：qq/ 2013/ qq2013。

10。支持阿拉伯数字/小数基本单字单位的识别，例如2012年，1.75米，5吨，120斤，38.6℃。

11。自动英文圆角/半角，大写/小写转换。

12。同义词匹配：自动中文/英文同义词追加. (需要在friso.ini中开启friso.add_syn选项)。

13。自动中英文停止词过滤。(需要在friso.ini中开启friso.clr_stw选项)。

14。多配置支持, 安全的应用于多进程/多线程环境。

15。提供friso.ini配置文件, 可以依据你的需求轻松打造适合于你的应用的分词。


<h3>二。分词速度: </h3>

测试环境：2.8GHZ/2G/Ubuntu 

简单模式：3.8M/秒  

复杂模式：1.8M/秒

<h3>三。分词测试：</h3>

文本：

歧义和同义词:研究生命起源，混合词: 做B超检查身体，x射线本质是什么，今天去奇都ktv唱卡拉ok去，哆啦a梦是一个动漫中的主角，单位和全角: 2009年８月６日开始大学之旅，岳阳今天的气温为38.6℃, 也就是101.48℉, 英文数字: bug report chenxin619315@gmail.com or visit http://code.google.com/p/jcseg, we all admire the hacker spirit!特殊数字: ① ⑩ ⑽ ㈩.

分词结果：

歧义 和 同义词 : 研究 琢磨 研讨 钻研 生命 起源 ， 混合词 : 做 b超 检查 身体 ， x射线 本质 是 什么 ， 今天 去 奇都ktv 唱 卡拉ok 去 ， 哆啦a梦 是 一个 动漫 中 的 主角 ， 单位 和 全角 : 2009年 8月 6日 开始 大学 之旅 ， 岳阳 今天 的 气温 为 38.6℃ , 也就是 101.48℉ , 英文 英语 数字 : bug report chenxin 619315 gmail com chenxin619315@gmail.com or visit http : / / code google com code.google.com / p / jcseg , we all admire appreciate like love enjoy the hacker spirit mind ! 特殊 数字 : ① ⑩ ⑽ ㈩ .


<h3>四。Friso其他主页: </h3> 
Friso官方主页: https://code.google.com/p/friso/ <br />
Friso开源中国: http://www.oschina.net/p/friso <br />

