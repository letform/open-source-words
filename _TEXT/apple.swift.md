swift programming language architecture master package macos x86 64 ubuntu 14 04 x86 64 ubuntu 16 04 x86 64 ubuntu 16 10 x86 64 swift community hosted ci platforms os architecture build debian 9 1 raspberry pi armv7 fedora 27 x86 64 ubuntu 16 04 x86 64 ubuntu 16 04 tensorflow x86 64 ubuntu 16 04 ppc64le ubuntu 16 04 aarch64 ubuntu 16 04 android x86 64 welcome to swift swift is a high performance system programming language it has a clean and modern syntax offers seamless access to existing c and objective c code and frameworks and is memory safe by default although inspired by objective c and many other languages swift is not itself a c derived language as a complete and independent language swift packages core features like flow control data structures and functions with high level constructs like objects protocols closures and generics swift embraces modules eliminating the need for headers and the code duplication they entail to learn more about the programming language visit swift org contributing to swift contributions to swift are welcomed and encouraged please see the contributing to swift guide to be a truly great community swift org needs to welcome developers from all walks of life with different backgrounds and with a wide range of experience a diverse and friendly community will have more great ideas more unique perspectives and produce more great code we will work diligently to make the swift community welcoming to everyone to give clarity of what is expected of our members swift has adopted the code of conduct defined by the contributor covenant this document is used across many open source communities and we think it articulates our values well for more see the code of conduct getting started these instructions give the most direct path to a working swift development environment to build from source you will need about 2 gb of disk space for the source code and up to 70 gb of disk space for the build artifacts with full debugging depending on your machine a clean build can take a few minutes to several hours naturally incremental builds are much faster system requirements macos ubuntu linux lts and the latest ubuntu linux release are the current supported host development operating systems macos to build for macos you need xcode 10 beta 3 the required version of xcode changes frequently and is often a beta release check this document or the host information on https ci swift org for the current required version you will also need cmake and ninja which can be installed via a package manager homebrew brew install cmake ninja macports sudo port install cmake ninja instructions for installing cmake and ninja directly can be found below linux for ubuntu youll need the following development dependencies sudo apt get install git cmake ninja build clang python uuid dev libicu dev icu devtools libbsd dev libedit dev libxml2 dev libsqlite3 dev swig libpython dev libncurses5 dev pkg config libblocksruntime dev libcurl4 openssl dev systemtap sdt dev tzdata rsync note lldb currently requires at least swig 1 3 40 but will successfully build with version 2 shipped with ubuntu build instructions for ubuntu 14 04 lts can be found here getting sources for swift and related projects first create a directory for all of the swift sources mkdir swift source cd swift source note this is important since update checkout see below checks out repositories next to the swift source directory this means that if one clones swift and has other unrelated repositories update checkout may not clone those repositories and will update them instead via https for those checking out sources as read only https works best git clone https github com apple swift git swift utils update checkout clone via ssh for those who plan on regularly making direct commits cloning over ssh may provide a better experience which requires uploading ssh keys to github git clone git github com apple swift git swift utils update checkout clone with ssh building swift the build script is a high level build automation script that supports basic options such as building a swift compatible lldb building the swift package manager building for various platforms running tests after builds and more there are two primary build systems to use xcode and ninja the xcode build system allows you to work in xcode but ninja is a bit faster and supports more environments to build using ninja run utils build script release debuginfo when developing swift it helps to build what youre working on in a debug configuration while building the rest of the project with optimizations below are some examples of using debug variants utils build script release debuginfo debug swift swift frontend built in debug utils build script release debuginfo debug swift stdlib standard library built in debug utils build script release debuginfo debug swift force optimized typechecker swift frontend sans type checker built in debug limiting the amount of debug code in the compiler has a very large impact on swift compile times and in turn the test execution time if you want to build the entire project in debug you can run utils build script debug for documentation of all available arguments as well as additional usage information see the inline help utils build script h xcode to build using xcode specify the xcode argument on any of the above commands xcode can be used to edit the swift source code but it is not currently fully supported as a build environment for sdks other than macos the generated xcode project does not integrate with the test runner but the tests can be run with the check swift target build products all of the build products are placed in swift source build tool mode product platform if macos swift with ninja in debugassert mode was built all of the products would be in swift source build ninja debugassert swift macosx x86 64 it helps to save this directory as an environment variable for future use export swift build dir swift source build ninja debugassert swift macosx x86 64 ninja once the first build has completed ninja can perform fast incremental builds of various products these incremental builds are a big timesaver when developing and debugging cd swift build dir ninja swift this will build the swift compiler but will not rebuild the standard library or any other target building the swift stdlib target as an additional layer of testing from time to time is also a good idea to build just the standard library run ninja swift stdlib it is always a good idea to do a full build after using update checkout using xcode to open the swift project in xcode open swift build dir swift xcodeproj it will auto create a lot of schemes for all of the available targets a common debug flow would involve select the swift scheme pull up the scheme editor ⌘⇧ select the arguments tab and click the add the command line options close the scheme editor build and run another option is to change the scheme to wait for executable to be launched then run the build product in terminal build failures make sure you are using the correct release of xcode if you have changed xcode versions but still encounter errors that appear to be related to the xcode version try passing clean to build script when a new version of xcode is released you can update your build without recompiling the entire project by passing the reconfigure option make sure all repositories are up to date with the update checkout command described above testing swift see docs testing md in particular the section on lit py learning more be sure to look through the docs directory for more information about the compiler in particular the documents titled debugging the swift compiler and continuous integration for swift are very helpful to understand before submitting your first pr building documentation to read the compiler documentation start by installing the sphinx documentation generator tool by running the command easy install u sphinx once complete you can build the swift documentation by changing directory into docs and typing make this compiles the rst files in the docs directory into html in the docs build html directory many of the docs are out of date but you can see some historical design documents in the docs directory another source of documentation is the standard library itself located in stdlib much of the language is actually implemented in the library including int and the standard library gives some examples of what can be expressed today build dependencies cmake cmake is the core infrastructure used to configure builds of swift and its companion projects at least version 3 4 3 is required on macos you can download the cmake binary distribution bundled as an application copy it to applications and add the embedded command line tools to your path export path applications cmake app contents bin path on linux if you have not already installed swifts development dependencies you can download and install the cmake package separately using the following command sudo apt get install cmake ninja ninja is the current recommended build system for building swift and is the default configuration generated by cmake pre built packages are available for macos and linux distributions you can also clone ninja next to the other projects and it will be bootstrapped automatically via https git clone https github com ninja build ninja git cd ninja git checkout release cat readme via ssh git clone git github com ninja build ninja git cd ninja git checkout release cat readme