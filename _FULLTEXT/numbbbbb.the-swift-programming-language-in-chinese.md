《The Swift Programming Language》in Chinese 中文版 Apple 官方 Swift 教程《The Swift Programming Language》 英文原版在线版 英文原版ePub版 在线阅读 使用 Gitbook 制作，可以直接在线阅读。 当前阶段 Swift 4.0 翻译中，请到 issue 中认领章节。 更新到 Swift 3.0。 2016-09-23 3.0 译者记录 相关issue - Functions: crayygy - Control Flow: Realank - Closures: LanfordCai - Protocols: chenmingbiao - The Basics:chenmingbiao - Advanced Operators: mmoaay Language Reference: - Attributes: WhoJave - Statements: chenmingjia - Declarations: chenmingjia - Expressions: chenmingjia - Types: lettleprince - Generic Parameters and Arguments: chenmingjia 2.1 & 2.2 译者记录 详见各章节开头位置。 2.0 译者记录 About Swift （xtymichael） A Swift Tour（xtymichael） The Basics（xtymichael） Basic Operators（AlanMelody） Strings and Characters（DianQK） Collection Types（AlanMelody） Control Flow（AlanMelody） Functions（dreamkidd） Closures（100mango） Enumerations（futantan） Classes and Structures（SkyJean） Properties（yangsiy） Methods（DianQK） Subscripts（shanksyang） Inheritance（shanksyang） Initialization（chenmingbiao） Deinitialization（chenmingbiao） Automatic Reference Counting（Channe） Optional Chaining（lyojo） Error Handling（lyojo） Type Casting（yangsiy） Nested Types（SergioChan） Extensions（shanksyang） Protocols（futantan） Generics（SergioChan） Access Control（mmoaay） Advanced Operators（buginux） About the Language Reference（KYawn） Lexical Structure（buginux） Types（EudeMorgen） Expressions（EudeMorgen） Statements（littledogboy） Declarations（Lenhoon） Attributes（KYawn） Patterns（ray16897188） Generic Parameters and Arguments（wardenNScaiyi） Summary of the Grammar（miaosiqi） 1.0 译者记录 欢迎使用 Swift 关于 Swift (numbbbbb) Swift 初见 (numbbbbb) Swift 教程 基础部分 (numbbbbb, lyuka, JaySurplus) 基本操作符 (xielingwang) 字符串和字符 (wh1100717) 集合类型 (zqp) 控制流 (vclwei, coverxit, NicePiao) 函数 (honghaoz) 闭包 (wh1100717) 枚举 (yankuangshi) 类和结构体 (JaySurplus) 属性 (shinyzhu) 方法 (pp-prog) 下标 (siemenliu) 继承 (Hawstein) 构造过程 (lifedim) 析构过程 (bruce0505) 自动引用计数 (TimothyYe) 可选链 (Jasonbroker) 类型检查 (xiehurricane) 嵌套类型 (Lin-H) 扩展 (lyuka) 协议 (geek5nan) 泛型 (takalard) 高级操作符 (xielingwang) 语言参考 关于语言参考 (dabing1022) 词法结构 (superkam) 类型 (lyuka) 表达式 (sg552 ) 语句 (coverxit) 声明 (marsprince) 特性 (Hawstein) 模式 (honghaoz) 泛型参数 (fd5788) 语法总结 (StanZhai) 贡献力量 如果想做出贡献的话，你可以： 帮忙校对，挑错别字、病句等等 提出修改建议 提出术语翻译建议 翻译建议 如果你愿意一起校对的话，请仔细阅读： 使用markdown进行翻译，文件名必须使用英文，因为中文的话gitbook编译的时候会出问题 翻译后的文档请放到source文件夹下的对应章节中，然后pull request即可，我会用gitbook编译成网页 工作分支为gh-pages，用于GitHub的pages服务 fork过去之后新建一个分支进行翻译，完成后pull request这个分支，没问题的话我会合并到gh-pages分支中 有其他任何问题都欢迎发issue，我看到了会尽快回复 谢谢！ 关于术语 翻译术语的时候请参考这个流程： 尽量保证和已翻译的内容一致 尽量先搜索，一般来说编程语言的大部分术语是一样的，可以参考微软官方术语搜索 如果以上两条都没有找到合适的结果，请自己决定一个合适的翻译或者直接使用英文原文，后期校对的时候会进行统一 参考流程 有些朋友可能不太清楚如何帮忙翻译，我这里写一个简单的流程，大家可以参考一下： 首先fork我的项目 把fork过去的项目也就是你的项目clone到你的本地 在命令行运行 git branch develop 来创建一个新分支 运行 git checkout develop 来切换到新分支 运行 git remote add upstream https://github.com/numbbbbb/the-swift-programming-language-in-chinese.git 把我的库添加为远端库 运行 git remote update更新 运行 git fetch upstream gh-pages 拉取我的库的更新到本地 运行 git rebase upstream/gh-pages 将我的更新合并到你的分支 这是一个初始化流程，只需要做一遍就行，之后请一直在develop分支进行修改。 如果修改过程中我的库有了更新，请重复6、7、8步。 修改之后，首先push到你的库，然后登录GitHub，在你的库的首页可以看到一个 pull request 按钮，点击它，填写一些说明信息，然后提交即可。 开源协议 基于WTFPL协议开源。