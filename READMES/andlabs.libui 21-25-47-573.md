libui a portable gui library for c this readme is being written status it has come to my attention that i have not been particularly clear about how usable or feature complete libui is and that this has fooled many people into expecting more from libui right this moment than i have explicitly promised to make available i apologize for not doing this sooner libui is currently mid alpha software much of what is currently present runs stabily enough for the examples and perhaps some small programs to work but the stability is still a work in progress much of what is already there is not feature complete some of it will be buggy on certain platforms and theres a lot of stuff missing in short heres a list of features that i would like to add to libui but that arent in yet tables and trees the former is currently wip and may land in preliminary form soon clipboard support including drag and drop more and better dialogs printing accessibility for uiarea and custom controls document based programs tighter os integration especially for document based programs to allow programs to fully feel native rather than merely look and act native better support for standard dialogs and features search bars etc opengl support this was already being worked on by someone else but i dont know what happened to them in addition here is a list of issues generalizing existing problems furthermore libui is not properly fully documented yet this is mainly due to the fact that the api was initially unstable enough so as to result in rewriting documentation multiple times in addition to me not being happy with really any existing c code documentation tool that being said i have started to pin down my ideal code documentation style in parts of ui h most notably in the uiattributedstring apis over time i plan on extending this to the rest of the headers you can also use the documentation for libuis go bindings as a reference though it is somewhat stale and not optimally written but libui is not dead i am working on it whenever i can and i hope to get it to a point of real quality soon news note that todays entry eastern time may be updated later today 30 may 2018 merged the previous announcements and updates section of this readme into a single news section and merged the respective archive files into a single news md file 16 may 2018 thanks to parro it and msink libui now has better ci including appveyor for windows ci and automated creation of binary releases when i make a tagged release 13 may 2018 added new functions to work with uidatetimepickers uidatetimepickertime uidatetimepickersettime and uidatetimepickeronchanged these operate on standard time h struct tms thanks cody271 release builds on windows with msvc should be fixed now thanks l0calh05t slahn mischnic and zentner kyle 12 may 2018 gtk and os x now have a cleaner build process for static libraries which no longer has intermediate files and differing configurations as a result certain issues should no longer be present new naming rules for internal symbols of libui have also started being drafted runtime symbols and edge cases still need to be handled and the rules applied to windows before this can become a regular thing 2 may 2018 on windows you no longer need to carry around a libui res file with static builds you do need to link in the appropriate manifest file such as the one in the windows folder i still need to figure out exactly what is needed apart from the common controls v6 dependency or at least to create a complete ish template or at least include it alongside your executables this also means you should no longer see random cmake errors when building the static libraries 18 april 2018 introduced a new uitimer function for running code on a timer on the main thread thanks to cody271 migrated all code in the common directory to use uipriv prefixes for everything that isnt static this is the first step toward fixing static library oddities within libui allowing libui to truly be safely used as either a static library or a shared library 18 march 2018 introduced an all new formatted text api that allows you to process formatted text in ways that the old api wouldnt allow you can read on the whole api here there is also a new examples for it drawtext which shows the whole api at a glance it doesnt yet support measuring or manipulating text nor does it currently support functions that would be necessary for things like text editors all of this will be added back later libui also now uses my utf library for utf 8 and utf 16 processing to allow consistent behavior across platforms this usage is not completely propagated throughout libui but the windows port uses it in most places now and eventually this will become what libui will use throughout also introduced a formal set of contribution guidelines see contributing md for details they are still wip 17 february 2018 the longstanding enter escape crashes on windows have finally been fixed thanks to lxn alpha 3 5 is now here this is a quickie release primiarly intended to deploy the above fix to package ui itself it is a partial binary release sorry more new things will come in the next release which will also introduce semver so it will be called v0 4 0 instead alpha 3 5 also includes a new control gallery example the screenshots below have not been updated yet old announcements can be found in the news md file runtime requirements windows windows vista sp2 with platform update or newer unix gtk 3 10 or newer mac os x os x 10 8 or newer build requirements all platforms cmake 3 1 0 or newer windows either microsoft visual studio 2013 or newer 2013 is needed for va copy — you can build either a static or a shared library mingw w64 other flavors of mingw may not work — you can only build a static library shared library support will be re added once the following features come in isolation awareness which is how you get themed controls from a dll without needing a manifest unix nothing else specific mac os x nothing else specific so long as you can build cocoa programs building out of tree builds typical of cmake are preferred you must be in the top level libui directory otherwise this wont work mkdir build cd build cmake pass dbuild shared libs off to cmake to build a static library the standard cmake build configurations are provided if none is specified debug is used if you use a makefile generator with cmake then make make tester for the test program make examples for examples and pass verbose 1 to see build commands build targets will be in the build out folder project file generators should work but are untested by me on windows i use the unix makefiles generator and gnu make built using the build w32 bat script included in the source and run in the visual studio command line in this state if mingw w64 either 32 bit or 64 bit is not in your path cmake will use msvc by default otherwise cmake will use with whatever mingw w64 is in your path set path path c \msys2\mingw 32 64 \bin should be enough to temporarily change to a mingw w64 build for the current command line session only if you installed mingw w64 through msys2 no need to change global environment variables constantly installation arch linux can be built from aur https aur archlinux org packages libui git documentation needs to be written consult ui h and the examples for details for now language bindings libui was originally written as part of my package ui for go now that libui is separate package ui has become a binding to libui as such package ui is the only official binding other people have made bindings to other languages language bindings c libui cpp cpp libui qtlike c net framework libui binding c net core devzh ui sharpui libuisharp chicken scheme wasamasa libui common lisp jinwoo cl ui crystal libui cr hedron d derelictlibui flat api libuid object oriented euphoria libui euphoria harbour hbui haskell haskell libui javascript node js libui node libui js merged into libui node proton native vuido julia libui jl kotlin kotlin libui lua libuilua libui lua lui lui nim ui php ui python pylibui pylibui cffi ruby libui ruby rust libui rs arcturu libui rs leotindall libui rs scala scalaui swift libui swift frequently asked questions why does my program start in the background on os x if i run from the command line os x normally does not start program executables directly instead it uses launch services to coordinate the launching of the program between the various parts of the system and the loading of info from an app bundle one of these coordination tasks is responsible for bringing a newly launched app into the foreground this is called activation when you run a binary directly from the terminal however you are running it directly not through launch services therefore the program starts in the background because no one told it to activate now it turns out there is an api that we can use to force our app to be activated but if we use it then wed be trampling over launch services which already knows whether it should activate or not therefore libui does not step over launch services at the cost of requiring an extra user step if running directly from the command line see also this and this contributing see contributing md screenshots from examples controlgallery