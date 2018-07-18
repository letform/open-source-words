中文版 日本語版 한국어 project guidelines · while developing a new project is like rolling on a green field for you maintaining it is a potential dark twisted nightmare for someone else heres a list of guidelines weve found written and gathered that we think works really well with most javascript projects here at elsewhen if you want to share a best practice or think one of these guidelines should be removed feel free to share it with us 🔥 checkout our minimal react redux starter in flow with hot reloading and server side rendering git some git rules git workflow writing good commit messages documentation environments consistent dev environments consistent dependencies dependencies testing structure and naming code style some code style guidelines enforcing code style standards logging api api design api security api documentation licensing 1 git 1 1 some git rules there are a set of rules to keep in mind perform work in a feature branch why because this way all work is done in isolation on a dedicated branch rather than the main branch it allows you to submit multiple pull requests without confusion you can iterate without polluting the master branch with potentially unstable unfinished code read more https www atlassian com git tutorials comparing workflows feature branch workflow branch out from develop why this way you can make sure that code in master will almost always build without problems and can be mostly used directly for releases this might be overkill for some projects never push into develop or master branch make a pull request why it notifies team members that they have completed a feature it also enables easy peer review of the code and dedicates forum for discussing the proposed feature update your local develop branch and do an interactive rebase before pushing your feature and making a pull request why rebasing will merge in the requested branch master or develop and apply the commits that you have made locally to the top of the history without creating a merge commit assuming there were no conflicts resulting in a nice and clean history read more resolve potential conflicts while rebasing and before making a pull request delete local and remote feature branches after merging why it will clutter up your list of branches with dead branches it ensures you only ever merge the branch back into master or develop once feature branches should only exist while the work is still in progress before making a pull request make sure your feature branch builds successfully and passes all tests including code style checks why you are about to add your code to a stable branch if your feature branch tests fail there is a high chance that your destination branch build will fail too additionally you need to apply code style check before making a pull request it aids readability and reduces the chance of formatting fixes being mingled in with actual changes use this gitignore file why it already has a list of system files that should not be sent with your code into a remote repository in addition it excludes setting folders and files for most used editors as well as most common dependency folders protect your develop and master branch why it protects your production ready branches from receiving unexpected and irreversible changes read more github bitbucket and gitlab 1 2 git workflow because of most of the reasons above we use feature branch workflow with interactive rebasing and some elements of gitflow naming and having a develop branch the main steps are as follows for a new project initialize a git repository in the project directory for subsequent features changes this step should be ignored sh cd project directory git init checkout a new feature bug fix branch sh git checkout b branchname make changes sh git add git commit a why git commit a will start an editor which lets you separate the subject from the body read more about it in section 1 3 sync with remote to get changes youve missed sh git checkout develop git pull why this will give you a chance to deal with conflicts on your machine while rebasing later rather than creating a pull request that contains conflicts update your feature branch with latest changes from develop by interactive rebase sh git checkout branchname git rebase i autosquash develop why you can use autosquash to squash all your commits to a single commit nobody wants many commits for a single feature in develop branch read more if you dont have conflicts skip this step if you have conflicts resolve them and continue rebase sh git add file1 file2 git rebase continue push your branch rebase will change history so youll have to use f to force changes into the remote branch if someone else is working on your branch use the less destructive force with lease sh git push f why when you do a rebase you are changing the history on your feature branch as a result git will reject normal git push instead youll need to use the f or force flag read more make a pull request pull request will be accepted merged and close by a reviewer remove your local feature branch if youre done sh git branch d branchname to remove all branches which are no longer on remote sh git fetch p for branch in git branch vv no color grep gone awk print 1 do git branch d branch done 1 3 writing good commit messages having a good guideline for creating commits and sticking to it makes working with git and collaborating with others a lot easier here are some rules of thumb source separate the subject from the body with a newline between the two why git is smart enough to distinguish the first line of your commit message as your summary in fact if you try git shortlog instead of git log you will see a long list of commit messages consisting of the id of the commit and the summary only limit the subject line to 50 characters and wrap the body at 72 characters why commits should be as fine grained and focused as possible it is not the place to be verbose read more capitalize the subject line do not end the subject line with a period use imperative mood in the subject line why rather than writing messages that say what a committer has done its better to consider these messages as the instructions for what is going to be done after the commit is applied on the repository read more use the body to explain what and why as opposed to how 2 documentation use this template for readme md feel free to add uncovered sections for projects with more than one repository provide links to them in their respective readme md files keep readme md updated as a project evolves comment your code try to make it as clear as possible what you are intending with each major section if there is an open discussion on github or stackoverflow about the code or approach youre using include the link in your comment dont use comments as an excuse for a bad code keep your code clean dont use clean code as an excuse to not comment at all keep comments relevant as your code evolves 3 environments define separate development test and production environments if needed why different data tokens apis ports etc might be needed in different environments you may want an isolated development mode that calls fake api which returns predictable data making both automated and manual testing much easier or you may want to enable google analytics only on production and so on read more load your deployment specific configurations from environment variables and never add them to the codebase as constants look at this sample why you have tokens passwords and other valuable information in there your config should be correctly separated from the app internals as if the codebase could be made public at any moment how env files to store your variables and add them to gitignore to be excluded instead commit a env example which serves as a guide for developers for production you should still set your environment variables in the standard way read more its recommended to validate environment variables before your app starts look at this sample using joi to validate provided values why it may save others from hours of troubleshooting 3 1 consistent dev environments set your node version in engines in package json why it lets others know the version of node the project works on read more additionally use nvm and create a nvmrc in your project root dont forget to mention it in the documentation why any one who uses nvm can simply use nvm use to switch to the suitable node version read more its a good idea to setup a preinstall script that checks node and npm versions why some dependencies may fail when installed by newer versions of npm use docker image if you can why it can give you a consistent environment across the entire workflow without much need to fiddle with dependencies or configs read more use local modules instead of using globally installed modules why lets you share your tooling with your colleague instead of expecting them to have it globally on their systems 3 2 consistent dependencies make sure your team members get the exact same dependencies as you why because you want the code to behave as expected and identical in any development machine read more how use package lock json on npm 5 or higher i dont have npm 5 alternatively you can use yarn and make sure to mention it in readme md your lock file and package json should have the same versions after each dependency update read more i dont like the name yarn too bad for older versions of npm use —save save exact when installing a new dependency and create npm shrinkwrap json before publishing read more 4 dependencies keep track of your currently available packages e g npm ls depth 0 read more see if any of your packages have become unused or irrelevant depcheck read more why you may include an unused library in your code and increase the production bundle size find unused dependencies and get rid of them before using a dependency check its download statistics to see if it is heavily used by the community npm stat read more why more usage mostly means more contributors which usually means better maintenance and all of these result in quickly discovered bugs and quickly developed fixes before using a dependency check to see if it has a good mature version release frequency with a large number of maintainers e g npm view async read more why having loads of contributors wont be as effective if maintainers dont merge fixes and patches quickly enough if a less known dependency is needed discuss it with the team before using it always make sure your app works with the latest version of its dependencies without breaking npm outdated read more why dependency updates sometimes contain breaking changes always check their release notes when updates show up update your dependencies one by one that makes troubleshooting easier if anything goes wrong use a cool tool such as npm check updates check to see if the package has known security vulnerabilities with e g snyk 5 testing have a test mode environment if needed why while sometimes end to end testing in production mode might seem enough there are some exceptions one example is you may not want to enable analytical information on a production mode and pollute someones dashboard with test data the other example is that your api may have rate limits in production and blocks your test calls after a certain amount of requests place your test files next to the tested modules using test js or spec js naming convention like modulename spec js why you dont want to dig through a folder structure to find a unit test read more put your additional test files into a separate test folder to avoid confusion why some test files dont particularly relate to any specific implementation file you have to put it in a folder that is most likely to be found by other developers test folder this name test is also standard now and gets picked up by most javascript testing frameworks write testable code avoid side effects extract side effects write pure functions why you want to test a business logic as separate units you have to minimize the impact of randomness and nondeterministic processes on the reliability of your code read more a pure function is a function that always returns the same output for the same input conversely an impure function is one that may have side effects or depends on conditions from the outside to produce a value that makes it less predictable read more use a static type checker why sometimes you may need a static type checker it brings a certain level of reliability to your code read more run tests locally before making any pull requests to develop why you dont want to be the one who caused production ready branch build to fail run your tests after your rebase and before pushing your feature branch to a remote repository document your tests including instructions in the relevant section of your readme md file why its a handy note you leave behind for other developers or devops experts or qa or anyone who gets lucky enough to work on your code 6 structure and naming organize your files around product features pages components not roles also place your test files next to their implementation bad ├── controllers ├── product js └── user js ├── models ├── product js └── user js good ├── product ├── index js ├── product js └── product test js ├── user ├── index js ├── user js └── user test js why instead of a long list of files you will create small modules that encapsulate one responsibility including its test and so on it gets much easier to navigate through and things can be found at a glance put your additional test files to a separate test folder to avoid confusion why it is a time saver for other developers or devops experts in your team use a config folder and dont make different config files for different environments why when you break down a config file for different purposes database api and so on putting them in a folder with a very recognizable name such as config makes sense just remember not to make different config files for different environments it doesnt scale cleanly as more deploys of the app are created new environment names are necessary values to be used in config files should be provided by environment variables read more put your scripts in a scripts folder this includes bash and node scripts why its very likely you may end up with more than one script production build development build database feeders database synchronization and so on place your build output in a build folder add build to gitignore why name it what you like dist is also cool but make sure that keep it consistent with your team what gets in there is most likely generated bundled compiled transpiled or moved there what you can generate your teammates should be able to generate too so there is no point committing them into your remote repository unless you specifically want to 7 code style 7 1 some code style guidelines use stage 2 and higher javascript modern syntax for new projects for old project stay consistent with existing syntax unless you intend to modernise the project why this is all up to you we use transpilers to use advantages of new syntax stage 2 is more likely to eventually become part of the spec with only minor revisions include code style check in your build process why breaking your build is one way of enforcing code style to your code it prevents you from taking it less seriously do it for both client and server side code read more use eslint pluggable javascript linter to enforce code style why we simply prefer eslint you dont have to it has more rules supported the ability to configure the rules and ability to add custom rules we use airbnb javascript style guide for javascript read more use the javascript style guide required by the project or your team we use flow type style check rules for eslint when using flowtype why flow introduces few syntaxes that also need to follow certain code style and be checked use eslintignore to exclude files or folders from code style checks why you dont have to pollute your code with eslint disable comments whenever you need to exclude a couple of files from style checking remove any of your eslint disable comments before making a pull request why its normal to disable style check while working on a code block to focus more on the logic just remember to remove those eslint disable comments and follow the rules depending on the size of the task use todo comments or open a ticket why so then you can remind yourself and others about a small task like refactoring a function or updating a comment for larger tasks use todo 3456 which is enforced by a lint rule and the number is an open ticket always comment and keep them relevant as code changes remove commented blocks of code why your code should be as readable as possible you should get rid of anything distracting if you refactored a function dont just comment out the old one remove it avoid irrelevant or funny comments logs or naming why while your build process may should get rid of them sometimes your source code may get handed over to another company client and they may not share the same banter make your names search able with meaningful distinctions avoid shortened names for functions use long descriptive names a function name should be a verb or a verb phrase and it needs to communicate its intention why it makes it more natural to read the source code organize your functions in a file according to the step down rule higher level functions should be on top and lower levels below why it makes it more natural to read the source code 7 2 enforcing code style standards use a editorconfig file which helps developers define and maintain consistent coding styles between different editors and ides on the project why the editorconfig project consists of a file format for defining coding styles and a collection of text editor plugins that enable editors to read the file format and adhere to defined styles editorconfig files are easily readable and they work nicely with version control systems have your editor notify you about code style errors use eslint plugin prettier and eslint config prettier with your existing eslint configuration read more consider using git hooks why git hooks greatly increase a developers productivity make changes commit and push to staging or production environments without the fear of breaking builds read more use prettier with a precommit hook why while prettier itself can be very powerful its not very productive to run it simply as an npm task alone each time to format code this is where lint staged and husky come into play read more on configuring lint staged here and on configuring husky here 8 logging avoid client side console logs in production why even though your build process can should get rid of them make sure that your code style checker warns you about leftover console logs produce readable production logging ideally use logging libraries to be used in production mode such as winston or node bunyan why it makes your troubleshooting less unpleasant with colorization timestamps log to a file in addition to the console or even logging to a file that rotates daily read more 9 api 9 1 api design why because we try to enforce development of sanely constructed restful interfaces which team members and clients can consume simply and consistently why lack of consistency and simplicity can massively increase integration and maintenance costs which is why api design is included in this document we mostly follow resource oriented design it has three main factors resources collection and urls a resource has data gets nested and there are methods that operate against it a group of resources is called a collection url identifies the online location of resource or collection why this is a very well known design to developers your main api consumers apart from readability and ease of use it allows us to write generic libraries and connectors without even knowing what the api is about use kebab case for urls use camelcase for parameters in the query string or resource fields use plural kebab case for resource names in urls always use a plural nouns for naming a url pointing to a collection users why basically it reads better and keeps urls consistent read more in the source code convert plurals to variables and properties with a list suffix why plural is nice in the url but in the source code its just too subtle and error prone always use a singular concept that starts with a collection and ends to an identifier students 245743 airports kjfk avoid urls like this get blogs blogid posts postid summary why this is not pointing to a resource but to a property instead you can pass the property as a parameter to trim your response keep verbs out of your resource urls why because if you use a verb for each resource operation you soon will have a huge list of urls and no consistent pattern which makes it difficult for developers to learn plus we use verbs for something else use verbs for non resources in this case your api doesnt return any resources instead you execute an operation and return the result these are not crud create retrieve update and delete operations translate text hallo why because for crud we use http methods on resource or collection urls the verbs we were talking about are actually controllers you usually dont develop many of these read more the request body or response type is json then please follow camelcase for json property names to maintain the consistency why this is a javascript project guideline where the programming language for generating and parsing json is assumed to be javascript even though a resource is a singular concept that is similar to an object instance or database record you should not use your table name for a resource name and column name resource property why because your intention is to expose resources not your database schema details again only use nouns in your url when naming your resources and dont try to explain their functionality why only use nouns in your resource urls avoid endpoints like addnewuser or updateuser also avoid sending resource operations as a parameter explain the crud functionalities using http methods how get to retrieve a representation of a resource post to create new resources and sub resources put to update existing resources patch to update existing resources it only updates the fields that were supplied leaving the others alone delete to delete existing resources for nested resources use the relation between them in the url for instance using id to relate an employee to a company why this is a natural way to make resources explorable how get schools 2 students should get the list of all students from school 2 get schools 2 students 31 should get the details of student 31 which belongs to school 2 delete schools 2 students 31 should delete student 31 which belongs to school 2 put schools 2 students 31 should update info of student 31 use put on resource url only not collection post schools should create a new school and return the details of the new school created use post on collection urls use a simple ordinal number for a version with a v prefix v1 v2 move it all the way to the left in the url so that it has the highest scope http api domain com v1 schools 3 students why when your apis are public for other third parties upgrading the apis with some breaking change would also lead to breaking the existing products or services using your apis using versions in your url can prevent that from happening read more response messages must be self descriptive a good error message response might look something like this json code 1234 message something bad happened description more details or for validation errors json code 2314 message validation failed errors code 1233 field email message invalid email code 1234 field password message no password provided why developers depend on well designed errors at the critical times when they are troubleshooting and resolving issues after the applications theyve built using your apis are in the hands of their users note keep security exception messages as generic as possible for instance instead of saying ‘incorrect password you can reply back saying ‘invalid username or password so that we dont unknowingly inform user that username was indeed correct and only the password was incorrect use these status codes to send with your response to describe whether everything worked the client app did something wrong or the api did something wrong which ones 200 ok response represents success for get put or post requests 201 created for when a new instance is created creating a new instance using post method returns 201 status code 204 no content response represents success but there is no content to be sent in the response use it when delete operation succeeds 304 not modified response is to minimize information transfer when the recipient already has cached representations 400 bad request for when the request was not processed as the server could not understand what the client is asking for 401 unauthorized for when the request lacks valid credentials and it should re request with the required credentials 403 forbidden means the server understood the request but refuses to authorize it 404 not found indicates that the requested resource was not found 500 internal server error indicates that the request is valid but the server could not fulfill it due to some unexpected condition why most api providers use a small subset http status codes for example the google gdata api uses only 10 status codes netflix uses 9 and digg only 8 of course these responses contain a body with additional information there are over 70 http status codes however most developers dont have all 70 memorized so if you choose status codes that are not very common you will force application developers away from building their apps and over to wikipedia to figure out what youre trying to tell them read more provide total numbers of resources in your response accept limit and offset parameters the amount of data the resource exposes should also be taken into account the api consumer doesnt always need the full representation of a resource use a fields query parameter that takes a comma separated list of fields to include get student fields id name age class pagination filtering and sorting dont need to be supported from start for all resources document those resources that offer filtering and sorting 9 2 api security these are some basic security best practices dont use basic authentication unless over a secure connection https authentication tokens must not be transmitted in the url get users 123 token asdf why because token or user id and password are passed over the network as clear text it is base64 encoded but base64 is a reversible encoding the basic authentication scheme is not secure read more tokens must be transmitted using the authorization header on every request authorization bearer xxxxxx extra yyyyy authorization code should be short lived reject any non tls requests by not responding to any http request to avoid any insecure data exchange respond to http requests by 403 forbidden consider using rate limiting why to protect your apis from bot threats that call your api thousands of times per hour you should consider implementing rate limit early on setting http headers appropriately can help to lock down and secure your web application read more your api should convert the received data to their canonical form or reject them return 400 bad request with details about any errors from bad or missing data all the data exchanged with the rest api must be validated by the api serialize your json why a key concern with json encoders is preventing arbitrary javascript remote code execution within the browser or if youre using node js on the server its vital that you use a proper json serializer to encode user supplied data properly to prevent the execution of user supplied input on the browser validate the content type and mostly use application json content type header why for instance accepting the application x www form urlencoded mime type allows the attacker to create a form and trigger a simple post request the server should never assume the content type a lack of content type header or an unexpected content type header should result in the server rejecting the content with a 4xx response check the api security checklist project read more 9 3 api documentation fill the api reference section in readme md template for api describe api authentication methods with a code sample explaining the url structure path only no root url including the request type method for each endpoint explain url params if url params exist specify them in accordance with name mentioned in url section required id integer optional photo id alphanumeric if the request type is post provide working examples url params rules apply here too separate the section into optional and required success response what should be the status code and is there any return data this is useful when people need to know what their callbacks should expect code 200 content id 12 error response most endpoints have many ways to fail from unauthorized access to wrongful parameters etc all of those should be listed here it might seem repetitive but it helps prevent assumptions from being made for example json code 403 message authentication failed description invalid username or password use api design tools there are lots of open source tools for good documentation such as api blueprint and swagger 10 licensing make sure you use resources that you have the rights to use if you use libraries remember to look for mit apache or bsd but if you modify them then take a look at the license details copyrighted images and videos may cause legal problems sources risingstack engineering mozilla developer network heroku dev center airbnb javascript atlassian git tutorials apigee wishtack icons by icons8