One file. Any browser. Same UI. Author: John Dyer http://j.hn/ Website: http://mediaelementjs.com/ License: MIT Meaning: Use everywhere, keep copyright, itd be swell if youd link back here. Thanks: my employer, Dallas Theological Seminary Contributors: all contributors Table of Contents Introduction Migrating from 2.x to 4.x version Installation and Usage API and Configuration Guidelines for Contributors Change Log TODO list Introduction MediaElementPlayer: HTML5 <video> and <audio> player A complete HTML/CSS audio/video player built on top MediaElement.js. Many great HTML5 players have a completely separate Flash UI in fallback mode, but MediaElementPlayer.js uses the same HTML/CSS for all players. MediaElement.js is a set of custom Flash plugins that mimic the HTML5 MediaElement API for browsers that dont support HTML5 or dont support the media codecs youre using. Instead of using Flash as a fallback, Flash is used to make the browser seem HTML5 compliant and enable codecs like H.264 (via Flash) on all browsers. In general, MediaElement.js supports IE11+, MS Edge, Chrome, Firefox, Safari, iOS 8+ and Android 4.0+. It is strongly recommended to read the entire documentation and check the demo folder to get the most out of this package. Visit here to start. * IMPORTANT NOTE for Safari users (Jun 8, 2017) Since Sierra version, autoplay policies have changed. You may experience an error if you try to execute play programatically or via autoplay attribute with MediaElement, unless muted attribute is specified. For more information, read https://webkit.org/blog/7734/auto-play-policy-changes-for-macos/ * IMPORTANT CHANGES on 4.2.0 version As part of the continuous improvements the player, we have decided to drop completely support for IE9 and IE10, since market share of those browsers together is 0.4%, according to http://caniuse.com/usage-table. This change is for MediaElement and MediaElement Plugins repositories. * IMPORTANT: Migrating from 2.x to 4.x version NOTE: 3.x version has jQuery in the code base, and 4.x is framework-agnostic. So for either 3.x or 4.x versions, the following steps are valid, but it is highly recommended to upgrade to 4.x. In order to successfully install 4.x in an existing setup, you must consider the following guidelines: If your installation relies on the legacy player classes (i.e., mejs-player, mejs-container, etc.), you must set up the proper namespace. In 2.x, the default namespace is mejs- but now is mejs__. In order to set up a new namespace (or the legacy one), use the classPrefix configuration, and make sure you use the mediaelementplayer-legacy stylesheet provided in the /build/ folder. By default, MediaElement has bundled native renderers, such as HLS, M(PEG)-DASH and FLV, as well as YouTube and Flash shims. If you want to use any other renderer, you MUST refer to the build/renderers folder and add as many as you want. Check demo/index.html for a better reference. You must set up now the path for the Flash shims if they are not in the same folder as the JS files. To do this, set the path via the pluginPath configuration. In the same topic, if you need to support browsers with Javascript disabled, you must reference the correct Flash shim, since in 2.x there was only a single Flash shim and in 3.x it was split to target specific media types. Check the Browsers with JavaScript disabled section for more details. If you want to use Flash shims from a CDN, do the change related to pluginPath setting the CDNs URL, and also setting shimScriptAccess configuration as always. If you need to force the Flash shim, the way to do it in 3.x version is to use the renderers configuration and list them in an array. pluginType was removed to favor rendererName. If you rely on that element, just create conditionals based on the renderer ID (all listed here). For example: ```javascript $(video, audio).mediaelementplayer({ // Configuration success: function(media) { var isNative = /html5|native/i.test(media.rendererName); var isYoutube = ~media.rendererName.indexOf(youtube); // etc. } }); ``` Installation and Usage The full documentation on how to install MediaElement.js is available at Installation. A brief guide on how to create and use instances of MediaElement available at Usage. Additional features can be found at https://github.com/mediaelement/mediaelement-plugins. API and Configuration MediaElement.js has many options that you can take advantage from. Visit API and Configuration for more details. Also, a Utilities/Features guide is available for development. Visit Utilities/Features for more details. Guidelines for Contributors If you want to contribute to improve this package, please read Guidelines. NOTE: If you would like to contribute with translations, make sure that you also check https://github.com/mediaelement/mediaelement-plugins, and perform the translations for the files suffixed as -i18n. Useful resources A compilation of useful articles can be found here. Change Log Changes available at Change Log. TODO list IMPORTANT: Before posting an issue, it is strongly encouraged to read the whole documentation since it covers the majority of scenarios exposed in prior issues. New features and pending bugs can be found at TODO list.