afnetworking is a delightful networking library for ios macos watchos and tvos its built on top of the foundation url loading system extending the powerful high level networking abstractions built into cocoa it has a modular architecture with well designed feature rich apis that are a joy to use perhaps the most important feature of all however is the amazing community of developers who use and contribute to afnetworking every day afnetworking powers some of the most popular and critically acclaimed apps on the iphone ipad and mac choose afnetworking for your next project or migrate over your existing projects—youll be happy you did how to get started download afnetworking and try out the included mac and iphone example apps read the getting started guide faq or other articles on the wiki check out the documentation for a comprehensive look at all of the apis available in afnetworking read the afnetworking 3 0 migration guide for an overview of the architectural changes from 2 0 communication if you need help use stack overflow tag afnetworking if youd like to ask a general question use stack overflow if you found a bug and can provide steps to reliably reproduce it open an issue if you have a feature request open an issue if you want to contribute submit a pull request installation afnetworking supports multiple methods for installing the library in a project installation with cocoapods cocoapods is a dependency manager for objective c which automates and simplifies the process of using 3rd party libraries like afnetworking in your projects see the getting started guide for more information you can install it with the following command bash gem install cocoapods cocoapods 0 39 0 is required to build afnetworking 3 0 0 podfile to integrate afnetworking into your xcode project using cocoapods specify it in your podfile ruby source https github com cocoapods specs git platform ios 8 0 target targetname do pod afnetworking 3 0 end then run the following command bash pod install installation with carthage carthage is a decentralized dependency manager that builds your dependencies and provides you with binary frameworks you can install carthage with homebrew using the following command bash brew update brew install carthage to integrate afnetworking into your xcode project using carthage specify it in your cartfile ogdl github afnetworking afnetworking 3 0 run carthage to build the framework and drag the built afnetworking framework into your xcode project requirements afnetworking version minimum ios target minimum macos target minimum watchos target minimum tvos target notes 3 x ios 7 os x 10 9 watchos 2 0 tvos 9 0 xcode 7 is required nsurlconnectionoperation support has been removed 2 6 2 6 3 ios 7 os x 10 9 watchos 2 0 n a xcode 7 is required 2 0 2 5 4 ios 6 os x 10 8 n a n a xcode 5 is required nsurlsession subspec requires ios 7 or os x 10 9 1 x ios 5 mac os x 10 7 n a n a 0 10 x ios 4 mac os x 10 6 n a n a macos projects must support 64 bit with modern cocoa runtime programming in swift try alamofire for a more conventional set of apis architecture nsurlsession afurlsessionmanager afhttpsessionmanager serialization afurlrequestserialization afhttprequestserializer afjsonrequestserializer afpropertylistrequestserializer afurlresponseserialization afhttpresponseserializer afjsonresponseserializer afxmlparserresponseserializer afxmldocumentresponseserializer macos afpropertylistresponseserializer afimageresponseserializer afcompoundresponseserializer additional functionality afsecuritypolicy afnetworkreachabilitymanager usage afurlsessionmanager afurlsessionmanager creates and manages an nsurlsession object based on a specified nsurlsessionconfiguration object which conforms to nsurlsessiontaskdelegate nsurlsessiondatadelegate nsurlsessiondownloaddelegate and nsurlsessiondelegate creating a download task objective c nsurlsessionconfiguration configuration nsurlsessionconfiguration defaultsessionconfiguration afurlsessionmanager manager afurlsessionmanager alloc initwithsessionconfiguration configuration nsurl url nsurl urlwithstring http example com download zip nsurlrequest request nsurlrequest requestwithurl url nsurlsessiondownloadtask downloadtask manager downloadtaskwithrequest request progress nil destination nsurl nsurl targetpath nsurlresponse response nsurl documentsdirectoryurl nsfilemanager defaultmanager urlfordirectory nsdocumentdirectory indomain nsuserdomainmask appropriateforurl nil create no error nil return documentsdirectoryurl urlbyappendingpathcomponent response suggestedfilename completionhandler nsurlresponse response nsurl filepath nserror error nslog file downloaded to filepath downloadtask resume creating an upload task objective c nsurlsessionconfiguration configuration nsurlsessionconfiguration defaultsessionconfiguration afurlsessionmanager manager afurlsessionmanager alloc initwithsessionconfiguration configuration nsurl url nsurl urlwithstring http example com upload nsurlrequest request nsurlrequest requestwithurl url nsurl filepath nsurl fileurlwithpath file path to image png nsurlsessionuploadtask uploadtask manager uploadtaskwithrequest request fromfile filepath progress nil completionhandler nsurlresponse response id responseobject nserror error if error nslog error error else nslog success response responseobject uploadtask resume creating an upload task for a multi part request with progress objective c nsmutableurlrequest request afhttprequestserializer serializer multipartformrequestwithmethod post urlstring http example com upload parameters nil constructingbodywithblock id formdata formdata appendpartwithfileurl nsurl fileurlwithpath file path to image jpg name file filename filename jpg mimetype image jpeg error nil error nil afurlsessionmanager manager afurlsessionmanager alloc initwithsessionconfiguration nsurlsessionconfiguration defaultsessionconfiguration nsurlsessionuploadtask uploadtask uploadtask manager uploadtaskwithstreamedrequest request progress nsprogress nonnull uploadprogress this is not called back on the main queue you are responsible for dispatching to the main queue for ui updates dispatch async dispatch get main queue update the progress view progressview setprogress uploadprogress fractioncompleted completionhandler nsurlresponse nonnull response id nullable responseobject nserror nullable error if error nslog error error else nslog response responseobject uploadtask resume creating a data task objective c nsurlsessionconfiguration configuration nsurlsessionconfiguration defaultsessionconfiguration afurlsessionmanager manager afurlsessionmanager alloc initwithsessionconfiguration configuration nsurl url nsurl urlwithstring http httpbin org get nsurlrequest request nsurlrequest requestwithurl url nsurlsessiondatatask datatask manager datataskwithrequest request completionhandler nsurlresponse response id responseobject nserror error if error nslog error error else nslog response responseobject datatask resume request serialization request serializers create requests from url strings encoding parameters as either a query string or http body objective c nsstring urlstring http example com nsdictionary parameters foo bar baz 1 2 3 query string parameter encoding objective c afhttprequestserializer serializer requestwithmethod get urlstring urlstring parameters parameters error nil get http example com foo bar baz 1 baz 2 baz 3 url form parameter encoding objective c afhttprequestserializer serializer requestwithmethod post urlstring urlstring parameters parameters error nil post http example com content type application x www form urlencoded foo bar baz 1 baz 2 baz 3 json parameter encoding objective c afjsonrequestserializer serializer requestwithmethod post urlstring urlstring parameters parameters error nil post http example com content type application json foo bar baz 1 2 3 network reachability manager afnetworkreachabilitymanager monitors the reachability of domains and addresses for both wwan and wifi network interfaces do not use reachability to determine if the original request should be sent you should try to send it you can use reachability to determine when a request should be automatically retried although it may still fail a reachability notification that the connectivity is available is a good time to retry something network reachability is a useful tool for determining why a request might have failed after a network request has failed telling the user theyre offline is better than giving them a more technical but accurate error such as request timed out see also wwdc 2012 session 706 networking best practices shared network reachability objective c afnetworkreachabilitymanager sharedmanager setreachabilitystatuschangeblock afnetworkreachabilitystatus status nslog reachability afstringfromnetworkreachabilitystatus status afnetworkreachabilitymanager sharedmanager startmonitoring security policy afsecuritypolicy evaluates server trust against pinned x 509 certificates and public keys over secure connections adding pinned ssl certificates to your app helps prevent man in the middle attacks and other vulnerabilities applications dealing with sensitive customer data or financial information are strongly encouraged to route all communication over an https connection with ssl pinning configured and enabled allowing invalid ssl certificates objective c afhttpsessionmanager manager afhttpsessionmanager manager manager securitypolicy allowinvalidcertificates yes not recommended for production unit tests afnetworking includes a suite of unit tests within the tests subdirectory these tests can be run simply be executed the test action on the platform framework you would like to test credits afnetworking is owned and maintained by the alamofire software foundation afnetworking was originally created by scott raymond and mattt thompson in the development of gowalla for iphone afnetworkings logo was designed by alan defibaugh and most of all thanks to afnetworkings growing list of contributors security disclosure if you believe you have identified a security vulnerability with afnetworking you should report it as soon as possible via email to security alamofire org please do not post it to a public issue tracker license afnetworking is released under the mit license see license for details