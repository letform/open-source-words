what is notepad notepad is a free free as in both free speech and free beer source code editor and notepad replacement that supports several programming languages and natural languages running in the ms windows environment its use is governed by gpl license build status to build notepad from source there are two components that need to be built separately notepad exe depends on scilexer dll scilexer dll with nmake you can build notepad with or without boost the release build of notepad is built with boost since notepad version 6 0 the build of scilexer dll that is distributed uses features from boosts boost regex library you can build scilexer dll without boost ie with its default posix regular expression support instead of boosts pcre one this is useful if you would like to debug notepad but dont have boost to build notepad exe open powereditor\visual net\notepadplus vcxproj build notepad like a normal visual studio project to build scilexer dll with boost here are the instructions to build scilexer dll for both 32 bit 64 bit for notepad download the boost source code v1 55 should be used with vs 2013 then unzip it in my case boost 1 55 0 is copied in c \sources\ go to scintilla\boostregex\ then run buildboost bat with your boost path in my case buildboost bat c \sources\boost 1 55 0 if you are compiling a 64 bit scintilla under your vs2013 x64 native tool command prompt add x64 flag in my case buildboost bat c \sources\boost 1 55 0 x64 go in scintilla\win32\ then run nmake f scintilla mak to build scilexer dll without boost this will work with notepad exe however some functionality in notepad will be broken to build scilexer dll without pcre support for both 32 bit 64 bit for 32 bit open a command prompt for building a k a the developer command prompt for vs2013 from the ide you can do this by right clicking on a file in solution explorer and clicking open command prompt this will open up a command prompt with all the proper environment variables from the windows start screen menu type developer command prompt for vs2013 and click select the result from an already open command prompt run vcvarsall bat e g c \program files x86 \microsoft visual studio 12 0\vc\vcvarsall bat for 64 bit open vs2013 x64 native tool command prompt change directory cd or pushd to scintilla\win32\ build scilexer dll with one of the following commands nmake noboost 1 f scintilla mak normal build nmake noboost 1 debug 1 f scintilla mak debugging build copy scilexer dll from scintilla\bin\ to the same directory as notepad exe for the unicode release configuration the output directory where notepad exe is is powereditor\bin\ for the unicode debug configuration the output directory where notepad exe is is powereditor\visual net\unicode debug\ see the notepad official site for more information notepad contributors