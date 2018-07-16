ramda a practical functional library for javascript programmers why ramda there are already several excellent libraries with a functional flavor typically they are meant to be general purpose toolkits suitable for working in multiple paradigms ramda has a more focused goal we wanted a library designed specifically for a functional programming style one that makes it easy to create functional pipelines one that never mutates user data whats different the primary distinguishing features of ramda are ramda emphasizes a purer functional style immutability and side effect free functions are at the heart of its design philosophy this can help you get the job done with simple elegant code ramda functions are automatically curried this allows you to easily build up new functions from old ones simply by not supplying the final parameters the parameters to ramda functions are arranged to make it convenient for currying the data to be operated on is generally supplied last the last two points together make it very easy to build functions as sequences of simpler functions each of which transforms the data and passes it along to the next ramda is designed to support this style of coding introductions introducing ramda by buzz de cafe why ramda by scott sauyet favoring curry by scott sauyet why curry helps by hugh jackson hey underscore youre doing it wrong by brian lonsdorf thinking in ramda by randy coulman philosophy using ramda should feel much like just using javascript it is practical functional javascript were not introducing lambda expressions in strings were not borrowing consed lists were not porting over all of the clojure functions our basic data structures are plain javascript objects and our usual collections are javascript arrays we also keep other native features of javascript such as functions as objects with properties functional programming is in good part about immutable objects and side effect free functions while ramda does not enforce this it enables such style to be as frictionless as possible we aim for an implementation both clean and elegant but the api is king we sacrifice a great deal of implementation elegance for even a slightly cleaner api last but not least ramda strives for performance a reliable and quick implementation wins over any notions of functional purity installation to use with node bash npm install ramda then in the console javascript const r require ramda to use directly in the browser html script src path to yourcopyof ramda js script or the minified version html script src path to yourcopyof ramda min js script or from a cdn either cdnjs html script src cdnjs cloudflare com ajax libs ramda 0 25 0 ramda min js script or one of the below links from jsdelivr html script src cdn jsdelivr net npm ramda 0 25 0 dist ramda min js script script src cdn jsdelivr net npm ramda 0 25 dist ramda min js script script src cdn jsdelivr net npm ramda latest dist ramda min js script note that using latest is taking a significant risk that ramda api changes could break your code these script tags add the variable r on the browsers global scope or you can inject ramda into virtually any unsuspecting website using the bookmarklet note for versions 0 25 ramda versions 0 25 dont have a default export so instead of import r from ramda one has to use import as r from ramda or better yet import only the required functions via import functionname from ramda build npm run build creates es src directories and updates both dist ramda js and dist ramda min js partial builds it is possible to build ramda with a subset of the functionality to reduce its file size ramdas build system supports this with command line flags for example if youre using r compose r reduce and r filter you can create a partial build with npm run silent partial build compose reduce filter dist ramda custom js this requires having node io js installed and ramdas dependencies installed just use npm install before running partial build documentation please review the api documentation also available is our cookbook of functions built from ramda that you may find useful the name ok so we like sheep thats all its a short name not already taken it could as easily have been eweda but then we would be forced to say eweda lamb and no one wants that for non english speakers lambs are baby sheep ewes are female sheep and rams are male sheep so perhaps ramda is a grown up lambda but probably not running the test suite console to run the test suite from the console you need to have mocha installed npm install g mocha then from the root of the project you can just call mocha alternately if youve installed the dependencies via npm install then you can run the tests and get detailed output by running npm test browser you can use testem to test across different browsers or even headlessly with livereloading of tests install testem npm install g testem and run testem open the link provided in your browser and you will see the results in your terminal if you have phantomjs installed you can run testem l phantomjs to run the tests completely headlessly usage for v0 25 and up import the whole library or pick es modules directly from the library js import as r from ramda const identity r r map identity 1 2 3 destructuring imports from ramda does not necessarily prevent importing the entire library you can manually cherry pick methods like the following which would only grab the parts necessary for identity to work js import identity from ramda src identity identity manually cherry picking methods is cumbersome however most bundlers like webpack and rollup offer tree shaking as a way to drop unused ramda code and reduce bundle size but their performance varies discussed here here is a summary of the optimal setup based on what technology you are using webpack babel use babel plugin ramda to automatically cherry pick methods discussion here example here webpack only use uglifyjs plugin for treeshaking along with the moduleconcatenationplugin discussion here with an example setup here rollup does a fine job properly treeshaking no special work needed example here typings typescript flow translations chinese 中文 ukrainian українська acknowledgements thanks to j c phillipps for the ramda logo ramda logo artwork © 2014 j c phillipps licensed creative commons cc by nc sa 3 0