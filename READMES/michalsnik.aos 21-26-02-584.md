small library to animate elements on your page as you scroll you may say its like wowjs yeah youre right effect is similar to wowjs but i had a different idea how to make such a plugin so here it is css3 driven scroll animation library aos allows you to animate elements as you scroll down and up if you scroll back to top elements will animate to its previous state and are ready to animate again if you scroll down 👉 to get a better understanding how this actually works i encourage you to check my post on css tricks 🚀 demo 🌟 codepen examples different build in animations with anchor setting in use with anchor placement and different easing with simple custom animations ❗ attention from version 2 0 0 attributes aos are no longer supported always use data aos ⚙ setup install aos using bower bash bower install aos save using npm bash npm install aos save direct download click here link styles html link rel stylesheet href bower components aos dist aos css add scripts html script src bower components aos dist aos js script aos from version 1 2 0 is available as umd module so you can use it as amd global node or es6 module init aos javascript script aos init script 🤔 how to use it basic usage all you have to do is to add data aos attribute to html element like so html div data aos animation name script will trigger animation name animation on this element if you scroll to it down below is a list of all available animations for now 🔥 advanced settings these settings can be set both on certain elements or as default while initializing script in options object without data part attribute description example value default value data aos offset change offset to trigger animations sooner or later px 200 120 data aos duration duration of animation ms 600 400 data aos easing choose timing function to ease elements in different ways ease in sine ease data aos delay delay animation ms 300 0 data aos anchor anchor element whose offset will be counted to trigger animation instead of actual elements offset selector null data aos anchor placement anchor placement which one position of element on the screen should trigger animation top center top bottom data aos once choose wheter animation should fire once or every time you scroll up down to element true false duration accept values from 50 to 3000 with step 50ms its because duration of animation is handled by css and to not make css longer than it is already i created implementations only in this range i think this should be good for almost all cases if not you may write simple css on your page that will add another duration option value available for example css body data aos duration 4000 data aos data aos data aos data aos duration 4000 transition duration 4000ms this code will add 4000ms duration available for you to set on aos elements or to set as global duration while initializing aos script notice that double data aos data aos its not a mistake it is a trick to make individual settings more important than global without need to write ugly important there data aos anchor placement you can set different placement option on each element the principle is pretty simple each anchor placement option contains two words i e top center this means that animation will be triggered when top of element will reach center of the window bottom top means that animation will be triggered when bottom of an element reach top of the window and so on down below you can find list of all anchor placement options examples html div data aos fade zoom in data aos offset 200 data aos easing ease in sine data aos duration 600 html div data aos flip left data aos delay 100 data aos anchor example selector html div data aos fade up data aos anchor placement top center api aos object is exposed as a global variable for now there are three methods available init initialize aos refresh recalculate all offsets and positions of elements called on window resize refreshhard reinit array with aos elements and trigger refresh called on dom changes that are related to aos elements example execution javascript aos refresh by default aos is watching for dom changes and if there are any new elements loaded asynchronously or when something is removed from dom it calls refreshhard automatically in browsers that dont support mutationobserver like ie you might need to call aos refreshhard by yourself refresh method is called on window resize and so on as it doesnt require to build new store with aos elements and should be as light as possible global settings if you dont want to change setting for each element separately you can change it globally to do this pass options object to init function like so javascript script aos init offset 200 duration 600 easing ease in sine delay 100 script additional configuration these settings can be set only in options object while initializing aos setting description example value default value disable condition when aos should be disabled mobile false startevent name of event on which aos should be initialized exampleevent domcontentloaded disabling aos if you want to disable aos on certain device or under any statement you can set disable option like so javascript script aos init disable mobile script there are several options that you can use to fit aos perfectly into your project you can pass one of three device types mobile phones and tablets phone or tablet this will disable aos on those certains devices but if you want make your own condition simple type your statement instead of device type name javascript disable window innerwidth 1024 there is also posibility to pass a function which should at the end return true or false javascript disable function var maxwidth 1024 return window innerwidth maxwidth start event if you dont want to initialize aos on domcontentloaded event you can pass your own event name and trigger it whenever you want aos is listening for this event on document element javascript script aos init startevent somecoolevent script important note if you set startevent load it will add event listener on window instead of document 👻 animations there are serveral predefined animations you can use already fade animations fade fade up fade down fade left fade right fade up right fade up left fade down right fade down left flip animations flip up flip down flip left flip right slide animations slide up slide down slide left slide right zoom animations zoom in zoom in up zoom in down zoom in left zoom in right zoom out zoom out up zoom out down zoom out left zoom out right anchor placement top bottom top center top top center bottom center center center top bottom bottom bottom center bottom top easing functions you can choose one of these timing function to animate elements nicely linear ease ease in ease out ease in out ease in back ease out back ease in out back ease in sine ease out sine ease in out sine ease in quad ease out quad ease in out quad ease in cubic ease out cubic ease in out cubic ease in quart ease out quart ease in out quart ✌️ contributing 📝 changelog ❔questions if you have any questions ideas or whatsoever please check aos contribution guide and dont hesitate to create new issues