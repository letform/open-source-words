for more details head to https hyper is usage download the latest release linux arch and derivatives hyper is available in the aur use an aur package manager like aurman sh aurman s hyper macos use homebrew cask to download the app by running these commands bash brew update brew cask install hyper windows use chocolatey to install the app by running the following command package information can be found here bash choco install hyper note the version available on homebrew cask chocolatey or the aur may not be the latest please consider downloading it from here if thats the case contribute regardless of the platform you are working on you will need to have yarn installed if you have never installed yarn before you can find out how at https yarnpkg com en docs install install necessary packages windows be sure to run yarn global add windows build tools to install windows build tools macos once you have installed yarn you can skip this section linux you can see here what your linux is based on rpm based graphicsmagick libicns utils xz installed by default on some distributions debian based graphicsmagick icnsutils xz utils fork this repository to your own github account and then clone it to your local device install the dependencies yarn build the code and watch for changes yarn run dev to run hyper yarn run app from another terminal tab window pane if you are using visual studio code select launch hyper in debugger configuration to launch a new hyper instance with debugger attached to make sure that your code works in the finished application you can generate the binaries like this bash yarn run dist after that you will see the binary in the dist folder known issues that can happen during development error building node pty if after building during development you get an alert dialog related to node pty issues make sure its build process is working correctly by running yarn run rebuild node pty if you are on macos this typically is related to xcode issues like not having agreed to the terms of service by running sudo xcodebuild after a fresh xcode installation error with codesign on macos when running yarn run dist if you have issues in the codesign step when running yarn run dist on macos you can temporarily disable code signing locally by setting export csc identity auto discovery false for the current terminal session related repositories art website sample extension sample theme awesome hyper