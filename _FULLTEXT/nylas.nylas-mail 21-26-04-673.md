nylas mail the open source extensible mail client nylas mail was an open source mail client built on the modern web with electron react and flux it was designed to be easy to extend and many third party plugins are available that add functionality to the client ⚠️ nylas mail was initially released and open sourced in early 2015 and was maintained by nylas until spring 2017 while nylas no longer supports nylas mail you can download the latest release or build it from source there are also several forks that are being actively developed and maintained getting started setup your environment mac install homebrew install nvm redis brew install nvm redis install node 6 via nvm nvm install 6 npm install setup your environment linux debian ubuntu install node 6 via nodesource trusted curl sl https deb nodesource com setup 6 x sudo e bash sudo apt get install y nodejs install redis locally sudo apt get install y redis server redis tools benefit of letting us use subdomains npm install running nylas mail npm run client starts the app npm run test client run the tests npm run lint client lint the source eslint coffeelint lesslint exploring the source this repository contains the full source code to the nylas mail client and its backend services it is divided into the following packages isomorphic core shared code across local client and cloud servers client app the main electron app for nylas mail mirrored to open source repo client sync the local mailsync engine integreated in nylas mail client private plugins private nylas mail plugins like sfdc cloud api the cloud based auth and metadata apis for n1 cloud core shared code used in all remote cloud services cloud workers cloud workers for services like send later see packages for the separate pieces each folder in packages is designed to be its own stand alone repository they are all bundled here for the ease of source control management digging deeper in early 2016 the nylas mail team wrote extensive documentation for the app that was intended for plugin developers this documentation lives on github pages and offers a great overview of the apps architecture and important classes here are some good places to get started application architecture debugging nylas mail the team has also given conference talks and published blog posts about the client reacteurope how react flux turn apps into extensible platforms forwardjs electron react pixel perfect experiences blog splitting from atom blog building plugins for react apps blog nylas mail build process blog low level electron debugging blog a new search parser blog developers guide to emoji blog nylas pro blog nylas mail pgp blog calendar events and rrules running the cloud when you download and build nylas mail from source it runs without its cloud components the concept of a nylas id subscription has been removed and plugins that require server side processing are disabled by default plugins like snooze send later etc in order to use these plugins and get the full nylas mail experience you need to deploy the backend infrastructure located in the cloud packages deploying these services is challenging because they are implemented as microservices and designed to be run at enterprise scale with redis postgres etc because these backend services must access your email account it is also important to use security best practices at the very least ssl encryption at rest and a partitioned vpc for more information about building and deploying this part of the stack check out the cloud core readme themes the nylas mail user interface is styled using css which means its easy to modify and extend nylas mail comes stock with a few beautiful themes and there are many more which have been built by community developers bundled themes dark darkside designed by jamie wilson taiga designed by noah buscher ubuntu designed by ahmed elhanafy less is more designed by alexander adkins community themes toogabooga material monokai agapanthus—inbox inspired theme stripe kleinstein—hides account sidebar arc dark solarized dark darkish predawn ido—polymail inspired theme berend elementaryos levelup sunrise borabora honeyduke snow hull express darksoda bemind dracula mouseeatscat sublime dark firefox gmail to install community themes download and unzip the repo in nylas mail select developer install a package manually navigate to where you downloaded the theme and select the root folder the theme is copied into the nylas mail folder for your convinence select change theme from the top level menu and youll see the newly installed theme thats it want to dive in more try creating your own theme plugins some plugins come pre installed and are a great starting points for creating your own translate—works with 10 languages quick replies—send emails faster with templates emoji keyboard—insert emoji by typing a colon followed by the name of an emoji symbol github sidebar info view on github personal level indicators phishing detection community plugins note these are not tested or officially supported by nylas but we still think they are really cool if you find bugs with them please open github issues on their individual project pages not the nylas mail n1 repo page thanks jiffy—insert animated gifs weather todoist unsubscribe squirt speed reader website launcher—opens a url in separate window cypher—pgp encryption avatars events calendar wip mail in chat wip evernote wunderlist participants display github when you install packages theyre moved to nylas mail packages and nylas mail runs apm install on the command line to fetch dependencies listed in the packages package json forks there are several forks of nylas mail that you should check out if youre just learning about nylas mail it is highly recommended you use one of these instead mailspring significant rewrite by one of the original authors focused on performance and cloud plugins nylas mail lives community effort to fix bugs and improve the client seeking maintainers