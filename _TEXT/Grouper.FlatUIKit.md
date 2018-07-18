background flatuikit was originally written by jack flintermann in march of 2013 before ios7 had even come out the idea was to give a nice flat look to some of the native ios components then ios7 came along and introduced a decent api to do most of these tasks however for backwards compatability we will be attempting to maintain ios6 compatability as long as feasabilty possible if we find a reason to move to ios7 only support we will leave a branch for remaining ios6 support and move forward flatuikit flatuikit is a collection of ios components styled with the flat ui aesthetic that we created while building grouper for iphone its design inspiration comes from flat ui and kyle miller styling is implemented via categories on drop in replacements for existing uikit components so integrating it into your project is very straightforward installation flatuikit can be installed via cocoapods simply add ruby pod flatuikit to your podfile if you dont use cocoapods youre welcome to use git submodules or simply download it and include it in your project manually note that flatuikit requires the coretext framework as well as ios 6 0 the components buttons fuibutton is a drop in subclass of uibutton that exposes the additional properties buttoncolor shadowcolor cornerradius and shadowheight note that if you set any of these you have to set all of them objective c mybutton buttoncolor uicolor turquoisecolor mybutton shadowcolor uicolor greenseacolor mybutton shadowheight 3 0f mybutton cornerradius 6 0f mybutton titlelabel font uifont boldflatfontofsize 16 mybutton settitlecolor uicolor cloudscolor forstate uicontrolstatenormal mybutton settitlecolor uicolor cloudscolor forstate uicontrolstatehighlighted textfields fuitextfield is a drop in subclass of uitextfield that exposes the additional properties edgeinsets textfieldcolor bordercolor borderwidth and cornerradius note that if you set any of these you have to set all of them objective c mytextfield font uifont flatfontofsize 16 mytextfield backgroundcolor uicolor clearcolor mytextfield edgeinsets uiedgeinsetsmake 4 0f 15 0f 4 0f 15 0f mytextfield textfieldcolor uicolor whitecolor mytextfield bordercolor uicolor turquoisecolor mytextfield borderwidth 2 0f mytextfield cornerradius 3 0f segmentedcontrols fuisegmentedcontrol is a drop in subclass of uisegmentedcontrol that exposes the additional properties selectedcolor deselectedcolor selectedfont deselectedfont selectedfontcolor deselectedfontcolor dividercolor and cornerradius note that if you set any of these it is recommended that you set all of them objective c mysegmentedcontrol selectedfont uifont boldflatfontofsize 16 mysegmentedcontrol selectedfontcolor uicolor cloudscolor mysegmentedcontrol deselectedfont uifont flatfontofsize 16 mysegmentedcontrol deselectedfontcolor uicolor cloudscolor mysegmentedcontrol selectedcolor uicolor amethystcolor mysegmentedcontrol deselectedcolor uicolor silvercolor mysegmentedcontrol dividercolor uicolor midnightbluecolor mysegmentedcontrol cornerradius 5 0 switches fuiswitch is not a subclass of uiswitch uiswitch is too inflexible to subclass but rather a reimplementation that exposes all of the methods of uiswitch in addition it also provides access to its underlying on off uilabels and other subviews objective c myswitch oncolor uicolor turquoisecolor myswitch offcolor uicolor cloudscolor myswitch onbackgroundcolor uicolor midnightbluecolor myswitch offbackgroundcolor uicolor silvercolor myswitch offlabel font uifont boldflatfontofsize 14 myswitch onlabel font uifont boldflatfontofsize 14 alert views similar to fuiswitch fuialertview is a reimplemenation of uialertview that exposes all of uialertviews methods and delegate methods with the fuialertviewdelegate protocol but with far greater flexibility in ui customization all of its child uilabels uiviews and fuibuttons can be customized at will objective c fuialertview alertview fuialertview alloc initwithtitle hello message this is an alert view delegate nil cancelbuttontitle dismiss otherbuttontitles do something nil alertview titlelabel textcolor uicolor cloudscolor alertview titlelabel font uifont boldflatfontofsize 16 alertview messagelabel textcolor uicolor cloudscolor alertview messagelabel font uifont flatfontofsize 14 alertview backgroundoverlay backgroundcolor uicolor cloudscolor colorwithalphacomponent 0 8 alertview alertcontainer backgroundcolor uicolor midnightbluecolor alertview defaultbuttoncolor uicolor cloudscolor alertview defaultbuttonshadowcolor uicolor asbestoscolor alertview defaultbuttonfont uifont boldflatfontofsize 16 alertview defaultbuttontitlecolor uicolor asbestoscolor alertview show note to create fuialertview instance in swift please use default initializer s swift let alertview fuialertview sliders steppers progress views to provide flat uisliders uiprogressviews and uisteppers we simply provide categories on uislider progressview uistepper to automatically configure their appearance with appropriate colors corner radii this makes for zero friction integration with your existing project objective c myslider configureflatsliderwithtrackcolor uicolor silvercolor progresscolor uicolor alizarincolor thumbcolor uicolor pomegranatecolor objective c myprogressview configureflatprogressviewwithtrackcolor uicolor silvercolor progresscolor uicolor alizarincolor mystepper configureflatstepperwithcolor uicolor wisteriacolor highlightedcolor uicolor wisteriacolor disabledcolor uicolor amethystcolor iconcolor uicolor cloudscolor bar button items to customize bar button items for your entire application including back buttons uibarbuttonitem flatui provides a class method which leverages the uibarbuttonitem appearance proxy to do this in one step objective c uibarbuttonitem configureflatbuttonswithcolor uicolor peterrivercolor highlightedcolor uicolor belizeholecolor cornerradius 3 however this might cause rendering issues with controllers that are pushed from actionsheets sharesheets or links in webviews to prevent this behavior scope the customized bar buttom items to your controllers objective c uibarbuttonitem configureflatbuttonswithcolor uicolor peterrivercolor highlightedcolor uicolor belizeholecolor cornerradius 3 whencontainedin yourviewcontroller class navigation bars as above we provide a category on uinavigationbar to configure it flatly with a single color objective c self navigationcontroller navigationbar configureflatnavigationbarwithcolor uicolor midnightbluecolor tableview cells you can modify the backgroundcolor and selectedbackgroundcolor of a uitableviewcell without losing the rounded corners the cell will copy the uitableviews separator color the separator height is exposed as separatorheight and the radius as cornerradius objective c uitableviewcell cell cell configureflatcellwithcolor uicolor greenseacolor selectedcolor uicolor cloudscolor roundingcorners corners cell cornerradius 5 0f optional cell separatorheight 2 0f optional popover like some other flat components we simply provide a category to automatically configure a popover appearance for ipad by only having to set a background color objective c popover uipopovercontroller alloc initwithcontentviewcontroller nc popover configureflatpopoverwithbackgroundcolor uicolor midnightbluecolor cornerradius 3 popover delegate self popover presentpopoverfromrect button frame inview self view permittedarrowdirections uipopoverarrowdirectionany animated yes colors for convenience flatuikit includes the colors defined at flat ui colors you can see examples of these colors in the code components above using them is as simple as objective c import uicolor mycolor uicolor turquoisecolor fonts flatuikit comes bundled with lato a clean beautiful open font more info on lato can be found here it is included in flatuikit automatically you can use it as follows objective c import uifont flatui h uifont myfont uifont flatfontofsize 16 icons you can now use the great icons provided by flatuikit in your app the easiest way is to use a label but i will be adding support to use them in buttons imageviews and other conveniences objective c import nsstring icons h uilabel label label font uifont iconfontwithsize 16 label text nsstring iconstringforenum fuiheart the icons follow roughly the same naming scheme as flatui but you can look up the enumeration in nsstring icons h contributions contributions are totally welcome well review all pull requests and if you send us a good one are interested were happy to give you push access to the repo