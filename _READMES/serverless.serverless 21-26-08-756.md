website • docs • newsletter • gitter • forum • meetups • twitter • were hiring the serverless framework – build applications comprised of microservices that run in response to events auto scale for you and only charge you when they run this lowers the total cost of maintaining your apps enabling you to build more logic faster the framework uses new event driven compute services like aws lambda google cloud functions and more its a command line tool providing scaffolding workflow automation and best practices for developing and deploying your serverless architecture its also completely extensible via plugins serverless is an mit open source project actively maintained by a full time venture backed team watch the video guide here serverless framework feedback survey contents quick start examples services features plugins example projects contributing community consultants licensing previous version 0 5 x quick start watch the video guide here or follow the steps below to create and deploy your first serverless microservice in minutes install via npm bash npm install g serverless set up your provider credentials watch the video on setting up credentials create a service you can create a new service or install existing services bash create a new serverless service project serverless create template aws nodejs path my service change into the newly created directory cd my service deploy a service use this when you have made changes to your functions events or resources in serverless yml or you simply want to deploy all changes within your service at the same time bash serverless deploy v deploy the function use this to quickly upload and overwrite your aws lambda code on aws allowing you to develop faster bash serverless deploy function f hello invoke the function invokes an aws lambda function on aws and returns logs bash serverless invoke f hello l fetch the function logs open up a separate tab in your console and stream all logs for a specific function using this command bash serverless logs f hello t remove the service removes all functions events and resources from your aws account bash serverless remove how to install a service this is a convenience method to install a pre made serverless service locally by downloading the github repo and unzipping it services are listed below bash serverless install u https github com your url to the serverless service check out the serverless framework guide for more information services v1 0 the following are services you can instantly install and use by running serverless install url service github url serverless examples crud crud service scala port crud with faunadb crud service using faunadb crud with s3 crud service using s3 graphql boilerplate graphql application boilerplate service authentication authentication boilerplate service mailer service for sending emails kinesis streams service to showcase kinesis stream support dynamodb streams service to showcase dynamodb stream support landingpage backend landingpage backend service to store e mail addresses facebook messenger chatbot chatbot for the facebook messenger platform lambda chaining service which chains lambdas through sns secured api service which exposes an api key accessible api authorizer service that uses api gateway custom authorizers thumbnails service that takes an image url and returns a 100x100 thumbnail boilerplate opinionated boilerplate es6 jest es6 jest boilerplate php call a php function from your lambda ruby call a ruby function from your lambda slack app slack app boilerplate with oauth and bot actions swift full featured project template to develop lambda functions in swift cloudwatch alerts on slack get aws cloudwatch alerts notifications on slack note the serverless install command will only work on v1 0 or later features supports node js python java scala c f go groovy kotlin php swift manages the lifecycle of your serverless architecture build deploy update delete safely deploy functions events and their required resources together via provider resource managers e g aws cloudformation functions can be grouped serverless services for easy management of code resources processes across large projects teams minimal configuration and scaffolding built in support for multiple stages optimized for ci cd workflows loaded with automation optimization and best practices 100 extensible extend or modify the framework and its operations via plugins an ecosystem of serverless services and plugins a passionate and welcoming community plugins v1 0 use these plugins to extend or overwrite the frameworks functionality add a plugin to this list auto generated content start generate serverless plugin table this table is generated from https github com serverless plugins blob master plugins json please make additions there plugin author go serverless goformation for serverless create serverless configs with go structs thepauleh raml serverless serverless plugin to work with raml api spec documents andrewcurioso serverless alexa plugin serverless plugin to support alexa lambda events rajington serverless alexa skills manage your alexa skills with serverless framework marcy terui serverless aliyun function compute serverless alibaba cloud function compute plugin aliyun serverless api cloudfront plugin that adds cloudfront distribution in front of your api gateway for custom domain cdn caching and access log droplr serverless api stage serverless api stage plugin enables stage variables and logging for aws api gateway leftclickben serverless apib validator validate that an api blueprint has full coverage over a serverless config onlicar serverless apig s 3 serve static front end content from s3 via the api gateway and deploy client bundle to s3 sdd serverless apigateway plugin configure the aws api gateway binary support headers and body template mappings gfg serverless apigw binary plugin to enable binary support in aws api gateway maciejtreder serverless apigwy binary serverless plugin for configuring api gateway to return binary responses ryanmurakami serverless appsync plugin serverless plugin to deploy appsync graphql api sid88in serverless attach managed policy a serverless plugin to automatically attach an aws managed iam policy or policies to all iam roles created by the service nordstrom serverless aws alias this plugin enables use of aws aliases on lambda functions hyperbrain serverless aws documentation serverless plugin to add documentation and models to the serverless generated api gateway 9cookies serverless aws nested stacks yet another aws nested stack plugin concon121 serverless aws resource names serverless plugin to alter the default naming conventions for sls resources via a simple mapping file concon121 serverless build plugin a node js focused build plugin for serverless nfour serverless cf vars enables use of aws pseudo functions and fn sub string substitution kabo serverless cljs plugin enables clojurescript as an implementation language for lambda handlers nervous systems serverless cloudformation changesets natively deploy to cloudformation via change sets instead of directly allowing you to queue changes and safely require escalated roles for final deployment trek10inc serverless cloudformation parameter setter set cloudformation parameters when deploying trek10inc serverless cloudformation resource counter a plugin to count the resources generated in the aws cloudformation stack after deployment drexler serverless cloudformation sub variables serverless framework plugin for easily supporting aws cloudformation sub function variables santiagocardenas serverless coffeescript a serverless plugin to compile your coffeescript into javascript at deployment duanefields serverless command line event args this module is serverless framework plugin event json passes to your lambda function in commandline horike37 serverless content encoding enable content encoding in aws api gateway during deployment xeno dohai serverless crypt securing the secrets on serverless framework by aws kms encryption marcy terui serverless custom packaging plugin plugin to package your sourcecode using a custom target path inside the zip hypoport serverless dir config plugin experimental serverless plugin to load function and resource definitions from a directory economysizegeek serverless domain manager serverless plugin for managing custom domains with api gateways amplify education serverless dotenv fetch environment variables and write it to a env file jimdo serverless dotnet a serverless plugin to run dotnet commands as part of the deploy process fruffin serverless dynalite run dynalite locally no jvm all js to simulate dynamodb watch serverless yml for table config updates sdd serverless dynamodb autoscaling configure amazon dynamodbs native auto scaling for your table capacities sbstjn serverless dynamodb local serverless dynamodb local plugin allows to run dynamodb locally for serverless 99xt serverless dynamodb ttl configure dynamodb ttl in serverless yml until cloudformation supports this jimdo serverless enable api logs enables coudwatch logging for api gateway events paulsambolin serverless env generator manage environment variables with yaml and load them with dotenv supports variable encryption with kms multiple stages and custom profiles dieproduktmacher serverless ephemeral build and include custom stateless libraries for any language accenture serverless event constant inputs allows you to add constant inputs to events in serverless 1 0 for more info see constant values in cloudwatch dittto serverless export env export environment variables into a env file with automatic aws cloudformation reference resolution arabold serverless express making express app development compatible with serverless framework mikestaub serverless functions base path easily define a base path where your serverless functions are located kevinrambaud serverless go build build go source files or public functions using yml definition file sean9keenan serverless gulp a thin task wrapper around goserverless that allows you to automate build test and deploy tasks using gulp rhythminme serverless haskell deploying haskell applications to aws lambda with serverless seek oss serverless hooks plugin run arbitrary commands on any lifecycle event in serverless uswitch serverless iam roles per function serverless plugin for easily defining iam roles per function via the use of iamrolestatements at the function level functionalone serverless iot local aws iot events with serverless offline tradle serverless jest plugin a serverless plugin for the serverless framework which adds support for test driven development using jest sc5 serverless kms secrets allows to easily encrypt and decrypt secrets using kms from the serverless cli sc5 serverless kubeless serverless plugin for deploying functions to kubeless serverless serverless local dev server speeds up development of alexa skills chatbots and apis by exposing your functions as local http endpoints and mapping received events dieproduktmacher serverless local environment serverless plugin to set local environment variables and remote environment variable to different values piercus serverless local schedule schedule aws cloudwatch event based invocations in local time with dst support unitedincome serverless log forwarding serverless plugin for forwarding cloudwatch logs to another lambda function amplify education serverless micro plugin to help manage multiple micro services under one main service barstoolsports serverless mocha plugin a serverless plugin for the serverless framework which adds support for test driven development using mocha sc5 serverless multi dotnet a serverless plugin to pack c lambdas functions that are spread to multiple cs projects tsibelman serverless nested stack a plugin to workaround for cloudformation 200 resource limit jagdish 176 serverless offline emulate aws λ and api gateway locally when developing your serverless project dherault serverless offline direct lambda allow offline direct lambda to lambda interactions by exposing lambdas with no api gateway event via http civicteam serverless offline scheduler runs scheduled functions offline while integrating with serverless offline ajmath serverless offline sns serverless plugin to run a local sns server and call serverless sns handlers with events notifications mj1618 serverless offline ssm read ssm parameters from a env file instead of aws janders223 serverless package common deploy microservice python serverless services with common code onlicar serverless package python functions packaging python lambda functions with only the dependencies requirements they need ubaniabalogun serverless parameters add parameters to the generated cloudformation templates svdgraaf serverless plugin api docs serverless plugin to automatically create a lambda function which returns swagger ui html api documentation page based on the given swagger spec json file 8select serverless plugin aws alerts a serverless plugin to easily add cloudwatch alarms to functions acloudguru serverless plugin aws resolvers resolves variables from ess rds or kinesis for serverless services dopplerlabs serverless plugin bespoken creates a local server and a proxy so you dont have to deploy anytime you want to test your code bespoken serverless plugin bind deployment id a serverless plugin to bind the randomly generated deployment resource to your custom resources jacob meacham serverless plugin browserifier reduce the size and speed up your node js based lambdas using browserify digitalmaas serverless plugin browserify speed up your node based lambdas doapp ryanp serverless plugin canary deployments a serverless plugin to implement canary deployments of lambda functions davidgf serverless plugin cfauthorizer this plugin allows you to define your own api gateway authorizers as the serverless cloudformation resources and apply them to http endpoints sc5 serverless plugin chrome plugin which bundles and ensures that headless chrome chromium is running when your aws lambda function handler is invoked adieuadieu serverless plugin cloudwatch sumologic plugin which auto subscribes a log delivery lambda function to lambda log groups created by serverless acloudguru serverless plugin common excludes adds commonly excluded files to package excludes dougmoscrop serverless plugin custom domain reliably sets a basepathmapping to an api gateway custom domain dougmoscrop serverless plugin deploy environment plugin to manage deployment environment across stages dopplerlabs serverless plugin diff compares your local aws cloudformation templates against deployed ones nicka serverless plugin dynamodb autoscaling auto generate auto scaling configuration for configured dynamodb tables medikoo serverless plugin elastic beanstalk a serverless plugin to deploy applications to aws elasticbeanstalk rawphp serverless plugin encode env var objects serverless plugin to encode any environment variable objects yonomi serverless plugin external sns events add ability for functions to use existing or external sns topics as an event source silvermine serverless plugin git variables a serverless plugin to expose git variables branch name head description full commit hash to your serverless services jacob meacham serverless plugin graphiql a serverless plugin to run a local http server for graphiql and your graphql handler bencooling serverless plugin include dependencies this is a serverless plugin that should make your deployed functions smaller dougmoscrop serverless plugin inject dependencies painlessly deploy serverless projects with only the required dependencies loanmarket serverless plugin iopipe see inside your lambda functions with high fidelity metrics and monitoring iopipe serverless plugin lambda dead letter a serverless plugin that can configure a lambda with a dead letter queue or topic gmetzker serverless plugin log subscription adds a cloudwatch logsubscription for functions dougmoscrop serverless plugin metric creates dynamically aws metric filter resources with custom patterns alex20465 serverless plugin multiple responses enable multiple content types for response template silvermine serverless plugin node shim serverless plugin to run your functions in nodejs version 8 lts 9 on aws lambda jzimmek serverless plugin offline kinesis events plugin that works with serverless offline to allow offline testing of serverless functions that are triggered by kinesis events dopplerlabs serverless plugin offline kinesis serverlessofflines plugin which listens kinesis stream and invokes locally your handlers godu serverless plugin offline dynamodbstreams serverlessofflines plugin which listens dynamodbstreams stream and invokes locally your handlers godu serverless plugin optimize bundle with browserify transpile with babel to es5 and minify with uglify your serverless functions fidellimited serverless plugin package dotenv file a serverless plugin to copy a env file into the serverless package acloudguru serverless plugin provider groups a plugin to allow management of grouped settings within large serverless projects loanmarket serverless plugin reducer reduce node js lambda package so it contains only lambda dependencies medikoo serverless plugin scripts add scripting capabilities to the serverless framework mvila serverless plugin select select which functions are to be deployed based on region and stage fidellimited serverless plugin simulate simulate aws lambda and api gateway locally using docker gertjvr serverless plugin split stacks migrate certain resources to nested stacks dougmoscrop serverless plugin stack config a serverless plugin to manage configurations for a stack across micro services rawphp serverless plugin stack outputs displays stack outputs for your serverless stacks when sls info is ran svdgraaf serverless plugin stackstorm reusable functions from stackstorm exchange stackstorm serverless plugin stage variables add stage variables for serverless 1 x to apigateway so you can use variables in your lambdas svdgraaf serverless plugin subscription filter a serverless plugin to register aws cloudwatchlogs subscription filter tsub serverless plugin tracer trace serverless hooks as they execute enykeev serverless plugin transpiler transpile lambda files during packaging step medikoo serverless plugin typescript serverless plugin for zero config typescript support graphcool serverless plugin vpc eni cleanup automatic cleanup of vpc network interfaces on stage removal medikoo serverless plugin warmup keep your lambdas warm during winter fidellimited serverless plugin webpack a serverless plugin to automatically bundle your functions individually with webpack goldwasserexchange serverless plugin write env vars write environment variables out to a file that is compatible with dotenv silvermine serverless prune plugin deletes old versions of functions from aws preserving recent and aliased versions claygregory serverless pseudo parameters use aws accountid and other cloudformation pseudo parameters in your serverless yml values svdgraaf serverless python individually a serverless framework plugin to install multiple lambda functions written in python cfchou serverless python requirements serverless plugin to bundle python packages unitedincome serverless reqvalidator plugin serverless plugin to add request validator to api gateway methods rafpe serverless resources env after deploy this plugin fetches cloudformation resource identifiers and sets them on aws lambdas and creates local env file rurri serverless run function plugin run serverless function locally lithin serverless s 3 encryption set or remove the encryption settings on your s3 buckets tradle serverless s 3 remover a serverless plugin to make s3 buckets empty before deleting cloudformation stack when sls remove sinofseven serverless s 3 sync a plugin to sync local directories and s3 prefixes for serverless framework k1low serverless s 3 bucket sync sync a local folder with a s3 bucket after sls deploy sbstjn serverless sam exports an aws sam template for a service created with the serverless framework sapessi serverless scriptable plugin customize serverless behavior without writing a plugin weixu365 serverless sentry automatic monitoring of memory usage execution timeouts and forwarding of lambda errors to sentry https sentry io arabold serverless shell drop to a runtime shell with all the environment variables set that youd have in lambda unitedincome serverless sns filter serverless plugin to add sns subscription filters to events mechanicalrock serverless spa serverless plugin to deploy your website to aws s3 using webpack to bundle it gilmarsquinelato serverless sqs alarms plugin wrapper to setup cloudwatch alarms on sqs queue length sbstjn serverless sqs fifo a serverless plugin to handle creation of sqs fifo queues in aws stop gap vortarian serverless ssm fetch sets aws systems manager parameter store ssm parameters into functions environment variables gozup serverless stack output store output from your aws cloudformation stack in json yaml toml files or to pass it to a javascript function for further processing sbstjn serverless stage manager super simple serverless plugin for validating stage names before deployment jeremydaly serverless static easily serve files from a folder while developing on localhost with the serverless offline plugin iliasbhal serverless step functions aws step functions with serverless framework horike37 serverless sthree env serverless plugin to get config from a json formatted file in s3 and copy them to environment variable styletributeit serverless subscription filter serverless plugin to register subscription filter for lambda logs register and pipe the logs of one lambda to another to process blackevil245 serverless tag api gateway serverless plugin to tag api gateway gfragoso serverless tag cloud watch logs serverless plugin to tag cloudwatchlogs gfragoso serverless tag sqs serverless plugin to tag sqs simple queue service gfragoso serverless vpc discovery serverless plugin for discovering vpc subnet security group configuration by name amplify education serverless webpack serverless plugin to bundle your lambdas with webpack serverless heaven serverless wsgi serverless plugin to deploy wsgi applications flask django pyramid etc and bundle python packages logandk auto generated content end this table is generated from https github com serverless plugins blob master plugins json please make additions there example projects v1 0 auto generated content start generate serverless examples table this table is generated from https github com serverless examples blob master community examples json please make additions there project name author serverless architecture boilerplate boilerplate to organize and deploy big projects using serverless and cloudformation on aws msfidelis babelbot lambda api gateway zero to chatbot in 10 lines of js built in integrations for messenger telegram kik line twilio skype and wechat or roll your own abiglobalhealth jwt authorizr custom jwt authorizer lambda function for amazon api gateway with bearer jwt serverlessbuch slack signup serverless serverless signup to slack and more lambda with python stepfunctions and web front end python boilerplate included dzimine serverless graphql api serverless graphql api using lambda and dynamodb boazdejong serverless screenshot serverless screenshot service using phantomjs svdgraaf serverless postgraphql graphql endpoint for postgresql using postgraphql rentrop serverless messenger boilerplate serverless messenger bot boilerplate sc5 serverless npm registry serverless private npm registry proxy and cache craftship serverless pokego serverless powered api to fetch nearby pokemon go data jch254 serverless weekly 2 pocket app serverless powered api for sending posts to pocket app s0enke serverless facebook quotebot 100 serverless facebook messenger chatbot which will respond with inspiring quotes pmuens serverless slack trevorbot slack bot for info on where in the world is trevor gerhardt conveyal serverless garden aid iot garden aid backend garden aid serverless react boilerplate a serverless react boilerplate for offline development 99xt serverless delivery framework this is a boilerplate for version release pipeline with serverless framework 99xt serverless mailgun slack a serverless function for posting to a slack webhook in response to a mailgun route marcus l pfs email serverless this is a lambda function created by the serverless framework it searches through members in our mongodb who have not been sent emails and sends them an email with their custom token to unlock the pledge free stream it then marks those members off as already receiving the email scpr plaid cashburndown service service for calculating cash burndown with plaid frontend code can be found here https github com cplee cashburndown site cplee cordis serverless a serverless api for eu cordis data marzeelabs serverless newsletter signup saves user details into dynamodb table required values are email first name and last name ivanderbu2 serverless slack cron lambda function which sends messages to slack channel in regular intervals via cron trigger ivanderbu2 giphy bot giphy bot for facebook chat tywong jwt lambda python minimal proof of concept implementation of jwt with serverless aws lambda mikaelmork sls access counter site visitor counter takahashim sls form mail send sns email from form data takahashim serverless python sample a simple serverless python sample with rest api endpoints and dependencies bennybauer serverless msg gateway a messaging aggregator for kik skype twilio telegram messenger send and receive messages in a standard format yonahforst serverless aws rekognition finpics use aws rekognition to provide a faces search of finpics com rgfindl serverless slack emojibot serverless slack bot for emoji markhobson keboola developer portal keboola developer portal built with serverless keboola serverless cloudwatch rds custom metrics a nodejs based mysql rds data collection script to push custom metrics to cloudwatch with serverless andrewfarley jrestless examples jrestless java jax rs examples for api gateway functions plain jax rs spring binary data requests responses custom authorizers and cognito user pool authorizers sns functions asynchronous communication between functions and service functions synchronous http like communication between functions transparent through feign bbilger sc 5 serverless boilerplate a boilerplate that contains setup for test driven development sc5 serverless blog to podcast service that reads rss feed and converts the entries to a podcast feed and audio files using amazon polly sc5 offset trump single page app using serverless c runtime and s3 site hosting pledge to do a good thing for the next four years to offset the potential negative effects of the us presidency flgmwt serverless url shortener a simple url shortener using serverless framework aletheia serverless html pdf service that convert html to pdf using phantomjss rasterize example calvintychan serverless examples cached rds ws a serverless framework example project that uses api gateway elasticache and rds postgresql mugglmenzel bittman a serverless project that follows a stock trading algorithm and uses scheduled functions to save data to dynamodb and send emails through mailgun rhlsthrm adoptable pet bot tweets adoptable pets using serverless node js and aws lambda lynnaloo owntracks serverless a serverless implementation of the owntracks http backend dschep serverless modern koa serverless modern koa starter kit barczag serverless react js universal rendering boilerplate reactjs web app starter kit does universal isomorphic rendering with serverless tylorshin open bot an unoptionated github bot driven by a configuration file in the repository open bot aws ses serverless example aws ses example in nodejs using lambda lakshmantgld aws api gateway serverless project written in go a serverless project that contains an api gateway endpoint powered by a lambda function written in golang and built using eawsy aws lambda go shim yunspace video preview and analysis service an event driven service that generates labels using amazon rekognition and creates preview gif animation from a video file laardee serverless es 6 7 crud api serverless stack examples of backend crud apis dynamodb lambda api gateway cognito user pool authorizer for react js single page app anomalyinnovations sqs worker with aws lambda and cloud watch alarms process messages stored in sqs with an auto scaled aws lambda worker function sbstjn serverless image manager image upload download with resizing used api gateways binary support serverless tylorshin aws lambda power tuning powered by step functions build a step functions state machine to optimize your aws lambda function memory power configuration alexcasalboni amazon kinesis streams fan out via kinesis analytics use amazon kinesis analytics to fan out your kinesis streams and avoid read throttling alexcasalboni grants api serverless es6 api to consume data from an external api ingest into elasticsearch and return a queryable endpoint on top of elasticsearch comicrelief honey lambda a simple serverless application designed to create and monitor url honey tokens on top of aws lambda and amazon api gateway 0x4d31 faultline error tracking tool on aws managed services faultline stack overflow monitor monitor stack overflow questions and post them in a slack channel picsoung serverless analytics write your own google analytics clone and track website visitors serverless with api gateway kinesis lambda and dynamodb sbstjn react stripe serverless ecommerce serverless e commerce app with aws lambda stripe and react patrick michelberger serverless medium text to speech serverless based text to speech service for medium articles rafalwilinski serverless java dynamo db imlementation example example for java programmers that want to work with aws lambda and dynamodb igorbakman aws cognito custom user pool example example cloudformation custom resource backed by a lambda using cognito user pools bsdkurt serverless lambda protobuf responses demo using api gateway and lambda with protocol buffer theburningmonk serverless telegram bot this example demonstrates how to setup an echo telegram bot using the serverless framework ⚡🤖 jonatasbaldin serverless dashboard for atom editor atom editor package which allows you to deploy and visualize your serverless services with serverless framework on your editor horike37 serverless lambda vpc nat redis demo using api gateway and lambda with vpc and nat to access internet and aws resource ittus serverless gitlab ci simple gitlab ci template for automatic testing and deployments bvincent1 serverless ffmpeg bucket event driven ffmpeg using serverless input bucket serverless ffmpeg output bucket kvaggelakos serverless ssh command example of executing ssh command with openwhisk upgle realtime ww 2 alexa skill an alexa skill project thats using alexa sdk can also be used for a working example of serverless webpack with use of async await via babel ceilfors serverless kakao bot easy development for kakaotalk bot with serverless jisupark serverless q a example inspired by the aws example forum a multitenancy q a template for surveys forums and more jacksoncharles personal access tokens cron check audit for leaked pat in your contentful organization how to use serverless as cronjobs to keep your personal access tokens secure madtrick slack lunch club weekly lunch matches with your slack teams pwa built with serverless react graphql arangodb and aws mikestaub slack github stats bot slack bot that returns contributions stats for selected repository build with typescript react phantomjs and nivo pavelvlasov auto generated content end this table is generated from https github com serverless examples blob master community examples json please make additions there contributing we love our contributors please read our contributing document to learn how you can start working on the framework yourself check out our help wanted or good first issue labels to find issues we want to move forward on with your help community email updates serverless forum gitter chatroom serverless meetups stackoverflow facebook twitter contact us consultants these consultants use the serverless framework and can help you build your serverless projects andrew griffiths independent consultant specialising in serverless technology trek10 parallax – they also built the david guetta campaign sc5 online carrot creative microapps apiwise useful io and hail messaging whaletech hop labs webscale api talent who also run serverless auckland meetup branded crate cloudonaut promptworks craftship epx labs runs serverless nyc meetup red badger langa they built trails js emerging technology advisors onespeed seraro who also runs atlanta serverless meetup https www meetup com atlanta cabi camp cloud ai blockchain iot and delhi serverless meetup https www meetup com delhi ncr serverless architecture meetup superluminar runs serverlessdays hamburg and serverless meetup hamburg licensing serverless is licensed under the mit license all files located in the node modules and external directories are externally maintained libraries used by this software which have their own licenses we recommend you read them as their terms may differ from the terms in the mit license previous serverless version 0 5 x you can find projects and plugins relating to version 0 5 here note that these are not compatible with v1 0 but we are working diligently on updating them guide on building v1 0 plugins you can read the v0 5 x documentation at readme io