every site on https serve confidently caddy is a general purpose http 2 web server that serves https by default download · documentation · community caddy is a production ready open source web server that is fast easy to use and makes you more productive available for windows mac linux bsd solaris and android menu features install quick start running in production contributing donors about the project features easy configuration with the caddyfile automatic https on by default via lets encrypt http 2 by default virtual hosting so multiple sites just work experimental quic support for cutting edge transmissions tls session ticket key rotation for more secure connections extensible with plugins because a convenient web server is a helpful one runs anywhere with no external dependencies not even libc see a more complete list of features built into caddy on top of all those caddy does even more with plugins choose which plugins you want at download altogether caddy can do things other web servers simply cannot do its features and plugins save you time and mistakes and will cheer you up your caddy instance takes care of the details for you install caddy binaries have no dependencies and are available for every platform get caddy either of these ways download page recommended allows you to customize your build in the browser latest release for pre built vanilla binaries build to build from source you need git and go 1 9 or newer follow these instruction for fast building get the source with go get github com mholt caddy caddy and then run go get github com caddyserver builds now cd gopath src github com mholt caddy caddy and run go run build go then make sure the caddy binary is in your path to build for other platforms use build go with the goos and goarch flags when building from source telemetry is enabled by default you can disable it by changing enabletelemetry in run go before compiling or use the disabled metrics flag at runtime to disable only certain metrics quick start to serve static files from the current working directory run caddy caddys default port is 2015 so open your browser to http localhost 2015 go from 0 to https in 5 seconds if the caddy binary has permission to bind to low ports and your domain names dns records point to the machine youre on caddy host example com this command serves static files from the current directory over https certificates are automatically obtained and renewed for you caddy is also automatically configuring ports 80 and 443 for you and redirecting http to https cool huh customizing your site to customize how your site is served create a file named caddyfile by your site and paste this into it plain localhost push browse websocket echo cat ext html log var log access log proxy api 127 0 0 1 7005 header api access control allow origin when you run caddy in that directory it will automatically find and use that caddyfile this simple file enables server push via link headers allows directory browsing for folders without an index file hosts a websocket echo server at echo serves clean urls logs requests to an access log proxies all api requests to a backend on port 7005 and adds the coveted access control allow origin header for all responses from the api wow caddy can do a lot with just a few lines doing more with caddy to host multiple sites and do more with the caddyfile please see the caddyfile tutorial sites with qualifying hostnames are served over https by default caddy has a nice little command line interface run caddy h to view basic help or see the cli documentation for details running in production caddy is production ready if you find it to be a good fit for your site and workflow running as root we advise against this you can still listen on ports 1024 on linux using setcap like so sudo setcap cap net bind service ep caddy the caddy project does not officially maintain any system specific integrations nor suggest how to administer your own system but your download file includes unofficial resources contributed by the community that you may find helpful for running caddy in production how you choose to run caddy is up to you many users are satisfied with nohup caddy others use screen users who need caddy to come back up after reboots either do so in the script that caused the reboot add a command to an init script or configure a service with their os if you have questions or concerns about caddy underlying crypto implementations consult gos crypto packages starting with their documentation then issues then the code itself as caddy uses mainly those libraries contributing join our forum where you can chat with other caddy users and developers to get familiar with the code base try caddy code search on sourcegraph please see our contributing guidelines for instructions if you want to write a plugin check out the developer wiki we use github issues and pull requests only for discussing bug reports and the development of specific changes we welcome all other topics on the forum if you want to contribute to the documentation please submit an issue describing the change that should be made thanks for making caddy and the web better donors digitalocean is hosting the caddy project dnsimple provides dns services for caddys sites dns spy keeps an eye on caddys dns properties we thank them for their services if you want to help keep caddy free please become a sponsor about the project caddy was born out of the need for a batteries included web server that runs anywhere and doesnt have to take its configuration with it caddy took inspiration from spark nginx lighttpd websocketd and vagrant which provides a pleasant mixture of features from each of them the name caddy is trademarked the name of the software is caddy not caddy server or caddyserver please call it caddy or if you wish to clarify the caddy web server see brand guidelines caddy is a registered trademark of light code labs llc author on twitter mholt6