 m cli boom swiss army knife for macos the difference m cli differs from other mac command line tools in that its main purpose is to manage administrative tasks and do it easier it doesnt install 3rd party tools because it doesnt have dependencies the installation is very easy and doesnt require intervention it only uses macos commands installation using homebrew brew install m cli manual installation curl fssl https raw githubusercontent com rgcr m cli master install sh sh you can also install it in a different path install dir home m cli sh curl fssl https raw githubusercontent com rgcr m cli master install sh note you need privileges usage  swiss army knife for macos  usage m options command help options update update m cli to the latest version uninstall uninstall m cli commands help battery bluetooth dir disk display dns dock finder firewall flightmode gatekeeper hostname info itunes lock ntp printer network nosleep notification restart safeboot screensaver service shutdown sleep timezone touchbar trash update user volume vpn wallpaper wifi battery usage m battery status help examples m battery status get the battery status bluetooth usage m bluetooth status enable disable help examples m bluetooth status bluetooth status m bluetooth enable turn on bluetooth m bluetooth disable turn off bluetooth disk usage m disk ls list info fs filesystems ejectall verify repair help examples m disk ls list disks m disk list list disks m disk list dev disk0 list a specific disk m disk fs list available filesystems for formatting m disk filesystems list available filesystems for formatting m disk info dev disk0 display information m disk ejectall eject all mountable volumes m disk verify volume volume myvol verify volume m disk verify disk dev disk0 verify disk m disk repair volume volume myvol repair volume m disk repair disk dev disk0 repair disk m disk format ms dos myname dev disk2 format the entire disk with a windows format ms dos m disk format volume ms dos myname volumes myvol format the volume with a windows format ms dos m disk reformat volumes myvol reformat a volume m disk rename currentname newname rename a volume display usage m display status help example m display status status of displays m display help show usage dns usage m dns flush help examples m dns flush flushes local dns dock usage m dock showdelay autohide magnification position addblankspace addrecentitems prune help examples m dock showdelay x x changes how long the dock takes to show up when auto hide is enabled m dock autohide yes enable docks auto hide feature m dock autohide no disable docks auto hide feature m dock magnification yes turn magnification on m dock magnification no turn magnification off m dock position bottom change docks position to the bottom of the screen m dock position left change docks position to the left of the screen m dock position right change docks position to the right of the screen m dock addblankspace add a blank space separator to the dock m dock addrecentitems add a stack containg your recent items to the dock you can change the stacks type by right clicking on it m dock prune removes all apps from dock dir usage m dir tree size delete help examples m dir tree tree view of folders in the current path m dir tree path tree view of folders in a specific path m dir delete empty delete empty folders recursively in the current path m dir delete empty path delete empty folders recursively in a specific path m dir delete dsfiles delete ds store files recursively in the current path m dir delete dsfiles path delete ds store files recursively in a specific path m dir size calculate current folder size m dir size path calculate folder size in a specific path finder usage m finder showhiddenfiles showfileextensions showdesktop showpath help examples m finder showhiddenfiles get the current status m finder showhiddenfiles yes show hidden files m finder showhiddenfiles no no show hidden files m finder showextensions get the current status m finder showextensions yes show all file extensions m finder showextensions no dont show all file extensions m finder showdesktop get the current desktop status m finder showdesktop yes enable the desktop m finder showdesktop no disable the desktop m finder showpath yes show the current opened folder path on the top bar of the finder window m finder showpath no show the current opened folder name on the top bar of the finder window firewall usage m firewall status enable disable list add remove help examples m firewall status show status m firewall enable enable firewall m firewall disable disable firewall m firewall list list applications handled by firewall m firewall add path to file add app to firewall m firewall remove path to file remove app from firewall flightmode usage m flightmode on off help examples m flightmode on turn flightmode on m flightmode off turn flightmode off gatekeeper usage m gatekeeper status list ls enable disable create help examples m gatekeeper status gatekeeper status m gatekeeper list list rules m gatekeeper enable enable gatekeeper m gatekeeper disable disable gatekeeper m gatekeeper enable myrule enable rule m gatekeeper disable myrule disable rule m gatekeeper create rulename path to program create a rule for the application group usage m group list ls info adduser removeuser ismember help examples m group list get list of groups m group info mygroup display group information m group adduser myuser mygroup add an user to a specific group m group removeuser myuser mygroup remove an user from a specific group m group ismember myuser mygroup show if the user is a member of a specific group hostname usage m hostname help examples m hostname get the current hostname information computername hostname localhostname and netbiosname m hostname newhostname set a new hostname computername hostname localhostname netbiosname m hostname help only shows this help info usage m info help examples m info print macos operating system version information itunes usage m itunes status play pause next prev mute unmute vol up vol down vol stop quit help examples m itunes status show status m itunes play play track m itunes pause pause track m itunes next play next track m itunes prev play previous track m itunes mute mute itunes m itunes unmute unmute itunes m itunes vol up volume up m itunes vol down volume down m itunes vol set volume level m itunes stop stop track m itunes quit quit itunes lock usage m lock help examples m lock lock session ntp usage m ntp status enable disable set help examples m ntp status status of the network time service m ntp enable enable clock to use network time m ntp disable disable clock to use network time m ntp set timehost1 net sap corp set network time server printer usage m printer settings name queue drivers web help examples m printer settings printer settings m printer name display printer names on system m printer queue display items in printer queue on system m printer drivers display all printer drivers m printer web enable and show web interface network usage m network ls list location help examples m network ls list network interfaces m network location get current location m network location ls list locations m network location create xyz create a location m network location delete xyz delete a location m network location switch xyz switch location nosleep usage m nosleep until help examples m nosleep until 3600 no sleep until 3600 seconds m nosleep until my script sh no sleep until the script ends m nosleep until pid 64377 no sleep until the process id ends notification usage m notification showcenter help examples m notification showcenter get the current status m notification showcenter yes enable the notification center m notification showcenter no disable the notification center restart usage m restart f force help examples m restart restart computer needs confirmation m restart f restart computer without confirmation safeboot usage m safeboot status enable disable help examples m safeboot status get the boot args m safeboot enable enable safe boot m safeboot disable disable safeboot screensaver usage m screensaver status askforpassword help examples m screensaver launch screensaver m screensaver status get the current status m screensaver askforpassword get password requirement to unlock m screensaver askforpassword yes enable password requirement to unlock m screensaver askforpassword no disable password requirement to unlock service usage m service status all list ls start stop load unload help examples m service status all list all services m service list list all services m service ls list all services m service ls com apple sessionlogoutd show information about a specific service m service start com apple sessionlogoutd start a service m service stop com apple sessionlogoutd stop a service m service load com apple sessionlogoutd load a service m service unload com apple sessionlogoutd unload a service shutdown usage m shutdown f force help examples m shutdown shutdown computer needs confirmation m shutdown f shutdown computer without confirmation sleep usage m sleep help examples m sleep put the mac to sleep timezone usage m timezone list ls set help examples m timezone get current timezone m timezone ls list available timezones m timezone set europe berlin set timezone trash usage m trash status clean help examples m trash status get trash info m trash clean clean trash update usage m update list install help examples m update list list available updates m update install all install all the available updates m update install itunesx 12 4 1 rawcameraupdate6 20 6 20 install specific updates user usage m user list ls info create delete help examples m user ls list users m user info demouser display user information m user create create a user it will ask you the below information username full name shell bin bash password m user delete demouser delete user volume usage m volume level 0 100 change n n up down mute unmute ismute examples m volume 70 set the volume to 70 m volume 5 increase the volume by 5 up to 100 m volume 10 decrease the volume by 5 down to 0 m volume up increase the volume by 6 25 m volume down decrease the volume by 6 25 m volume get the volume level m volume mute set mute m volume unmute unset mute m volume ismute check the volume status vpn usage m vpn ls list start stop status help examples m vpn ls list vpn connections m vpn start interactive mode m vpn start vpn start vpn connection named vpn m vpn start vpn user start a vpn connection with a given user m vpn start vpn user pass start a vpn connection with a given user and password m vpn start vpn user pass secret start a vpn connection with a given user password and secret m vpn stop vpn stop vpn connection named vpn m vpn status vpn status vpn connection named vpn wallpaper usage m wallpaper path to file jpg help examples m wallpaper wallpapers tree jpg set wallpaper wifi usage m wifi scan off on connect help examples m wifi status wifi status m wifi scan scan wifi m wifi showpassword essid show wifi network password default current m wifi history wifi connection history m wifi off turn off your wifi m wifi on turn on your wifi m wifi connect essid password join a wifi network m wifi connect essid join a wifi network prompt for password contributing fork it create your feature branch git checkout b my new feature commit your changes git commit m add some feature push to the branch git push origin my new feature submit a pull request metal todo add more plugins improve the help improve the installation script thanks guarinogabriel mac cli was a great source of inspiration mit license © rogelio cedillo