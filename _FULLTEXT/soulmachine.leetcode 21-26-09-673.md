leetcode题解 在线阅读 https www gitbook com book soulmachine algorithm essentials pdf下载 leetcode题解 c 版 pdf c 文件夹下是c 版，内容一模一样，代码是用c 写的。 java 文件夹下是java版，目前正在编写中，由于拖延症，不知道猴年马月能完成。 latex模板 本书使用的是陈硕开源的模板。这个模板制作精良，很有taste，感谢陈硕 在windows下编译 安装tex live 2015 http www tug org texlive 。把bin目录例如d \texlive\2015\bin\win32加入path环境变量。 安装字体。这个latex模板总共使用了10个字体，下载地址 https pan baidu com s 1erfjxnw ，有的字体windows自带了，有的字体ubuntu自带了，但都不全，还是一次性安装完所有字体比较方便。 安装texstudio http texstudio sourceforge net 可选 启动tex live manager，更新所有已安装的软件包。 配置texstudio。 启动texstudio，选择 options configure texstudio commands，xelatex 设置为 xelatex synctex 1 interaction nonstopmode tex； 选择 options configure texstudio build build view 由默认的 pdf chain 改为 compile view； default compiler 由默认的pdflatex 修改为 xelatex ； pdf viewer 改为 “internal pdf viewer windowed ”，这样预览时会弹出一个独立的窗口，这样比较方便。 编译。用texstudio打开typeset tex，点击界面上的绿色箭头就可以开始编译了。 在下方的窗口可以看到texstudio正在使用的编译命令是xelatex synctex 1 interaction nonstopmode typeset tex 在ubuntu下编译 安装tex live 2015 http www tug org texlive 1 1 下载texlive 2015 的iso 光盘，地址 http www tug org texlive acquire iso html 1 2 mount 光盘，sudo install tl 开始安装 1 3 加入环境变量 sudo vi etc profile export path path usr local texlive 2015 bin x86 64 linux export manpath manpath usr local texlive 2015 texmf dist doc man export infpath infpath usr local texlive 2015 texmf dist doc info 安装字体。这个latex模板总共使用了10个字体，下载地址 https pan baidu com s 1erfjxnw ，有的字体windows自带了，有的字体ubuntu自带了，但都不全，还是一次性安装完所有字体比较方便。 安装texstudio http texstudio sourceforge net 配置texstudio。 启动texstudio，选择 options configure texstudio commands，xelatex 设置为 xelatex synctex 1 interaction nonstopmode tex； 选择 options configure texstudio build build view 由默认的 pdf chain 改为 compile view； default compiler 由默认的pdflatex 修改为 xelatex ； pdf viewer 改为 “internal pdf viewer windowed ”，这样预览时会弹出一个独立的窗口，这样比较方便。 编译。用texstudio打开typeset tex，点击界面上的绿色箭头就可以开始编译了。 在下方的窗口可以看到texstudio正在使用的编译命令是xelatex synctex 1 interaction nonstopmode typeset tex 1 懒人版镜像。如果不想进行上面繁琐的安装过程，我做好了一个ubuntu vmware虚拟机镜像，已经装好了 texlive 2015 texstudio和字体 详细的安装日志见压缩包注释 ，开箱即用，下载地址 http pan baidu com s 1clwkga。 如何贡献代码 编译通过后，就具备了完整的latex编译环境了。 本书模板已经写好了，基本上不需要很多latex知识就可以动手了。 欢迎给本书添加内容或纠正错误，在自己本地编译成pdf，预览没问题后，就可以发pull request过来了。 qq群 237669375 小密圈 algohub https www algohub org 是我建立的一个刷题网站，即将上线，敬请期待 纸质书 本书即将由电子工业出版社出版，敬请期待